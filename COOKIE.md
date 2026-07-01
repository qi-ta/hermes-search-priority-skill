# 🍪 Cookie Setup Guide

> How to configure cookies so your AI agent can access authenticated platforms.

---

## ❓ Why Cookies?

Some platforms referenced by the Search Priority Skill require authentication:

| Platform | Why Needed |
|:---|:---|
| **X (Twitter)** | Search API locked behind login |
| **GitHub** | Higher rate limits with authenticated sessions |

Without cookies, these platforms return **empty results or login walls**.

---

## 📁 Cookie File Location

Place your exported cookies here:

```
~/.hermes/cookies/
├── x.json           # X/Twitter cookies
└── github.json      # GitHub cookies
```

---

## 🔧 Method 1: Manual Export (Recommended)

### Step 1: Open Chrome DevTools

1. Log in to the target platform (e.g. twitter.com)
2. Press `F12` → **Application** tab
3. Left sidebar: **Storage** → **Cookies** → select the domain

### Step 2: Export to JSON

**Option A — Browser Extension (easiest):**

**🅰️ Get cookies.txt LOCALLY (recommended)**
- Install [**Get cookies.txt LOCALLY**](https://chromewebstore.google.com/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc) (Chrome extension)
- Log in to the target site → Click extension icon → **Export As** → select **Netscape format (.txt)**
- Save as `cookies.txt` — directly usable with curl/wget
- Works with X/Twitter, GitHub, and more

**🅱️ EditThisCookie**
- Install [**EditThisCookie**](https://www.editthiscookie.com/) (Chrome extension)
- Click the cookie icon → **Export**
- Save as `x.json` in `~/.hermes/cookies/`

**Option B — Console (quick):**
```javascript
// Paste in Chrome DevTools Console while on the site
copy(JSON.stringify(
  document.cookie.split('; ').map(c => {
    const [name, ...rest] = c.split('=');
    return { name, value: rest.join('='), domain: location.hostname };
  })
));
// Then paste the clipboard into a .json file
```

### Step 3: Verify

```bash
cat ~/.hermes/cookies/x.json | python3 -c "import sys,json; print(f'{len(json.load(sys.stdin))} cookies loaded')"
```

---

## 🤖 Method 2: Playwright Auto-Injection (Advanced)

Use Playwright to automate login + cookie persistence.

### Install

```bash
pip install playwright
playwright install chromium
```

### Script Template

```python
# save_cookies.py
from playwright.sync_api import sync_playwright
import json

PLATFORM = "x"          # x / github
LOGIN_URL = "https://x.com/login"
SAVE_PATH = f"~/.hermes/cookies/{PLATFORM}.json"

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)  # headless=False for login
    page = browser.new_page()
    page.goto(LOGIN_URL)
    
    print("🔐 Please log in manually in the browser window...")
    input("Press Enter after logging in...")
    
    cookies = page.context.cookies()
    with open(SAVE_PATH, "w") as f:
        json.dump(cookies, f, indent=2)
    
    print(f"✅ {len(cookies)} cookies saved to {SAVE_PATH}")
    browser.close()
```

### Reuse Cookies in Playwright

```python
# use_cookies.py
from playwright.sync_api import sync_playwright
import json

with sync_playwright() as p:
    browser = p.chromium.launch()
    context = browser.new_context()
    
    # Load saved cookies
    with open("~/.hermes/cookies/x.json") as f:
        context.add_cookies(json.load(f))
    
    page = context.new_page()
    page.goto("https://x.com/home")
    # Now you're logged in!
```

---

## 🛡️ Security Notes

⚠️ **NEVER commit cookies to public repos** — add to `.gitignore`:
```
~/.hermes/cookies/
```

⚠️ **Cookies expire** — X/Twitter sessions typically last ~30 days. Re-export when searches start failing.

⚠️ **Do not share** — Cookies grant full account access.

---

## 🔄 Cookie Refresh Flow

```
Search fails with 401/403
  → Re-open manual export (Method 1)
  → Or re-run Playwright script (Method 2)
  → Replace ~/.hermes/cookies/{platform}.json
  → Verify with: python3 -c "import json; print(len(json.load(open('~/.hermes/cookies/x.json'))))"
```

---

## 📞 Troubleshooting

| Symptom | Fix |
|:---|:---|
| "No results" from X search | Cookies expired → re-export |
| GitHub rate limit hit | Add `github.json` cookies |
| Playwright times out | Check proxy settings: `export HTTP_PROXY=http://127.0.0.1:7897` |
