# AURUM · Gold Rate Alert

A beautiful static web app that monitors live gold prices and sends SMS alerts when the price changes — hosted free on GitLab Pages.

## Features
- 📊 Live gold price (XAU/USD) with real-time chart
- 📱 SMS alerts via Twilio when price moves beyond your threshold
- ⚙️ Configurable refresh interval and alert sensitivity
- 🔒 Credentials stored locally in your browser only
- 🚀 100% static — zero backend, zero server cost

---

## Deploy to GitHub Pages (Free)

1. **Create a new GitHub repository** at https://github.com/new

2. **Push all files** to the `main` branch (including the `.github/workflows/deploy.yml` file):
   ```
   index.html
   .github/workflows/deploy.yml
   ```

3. **Enable GitHub Pages** in your repo:
   - Go to **Settings → Pages**
   - Under **Source**, select **GitHub Actions**

4. **Push to `main`** — the workflow auto-deploys in ~1 minute.

5. **Your live URL** will be:
   `https://<your-username>.github.io/<repo-name>/`

   Check: **Settings → Pages** for the exact URL.

---

## Twilio Setup (Free SMS)

1. Sign up at https://www.twilio.com/try-twilio (free trial ~$15 credit)
2. From your Console Dashboard, copy:
   - **Account SID** (starts with `AC`)
   - **Auth Token**
3. Get a free Twilio phone number → **Phone Numbers → Manage → Buy a number**
4. Enter these in the app's config panel on the right side

> ⚠️ **Security Note:** Your Twilio credentials are saved in your browser's `localStorage` and sent directly to the Twilio API. This is fine for personal use. For a shared/public deployment, route SMS calls through a backend proxy to protect your credentials.

---

## Gold Price API

The app uses [gold-api.com](https://gold-api.com) (free, no key required) as the primary source. If unavailable, it falls back to `metals.live` and then a simulated random walk for demo purposes.

For higher reliability, sign up for a free key at:
- https://www.goldapi.io (free tier: 100 requests/month)
- https://metals-api.com (free tier: 50 requests/month)

---

## Local Development

Just open `index.html` in any browser — no build step required.

```bash
open index.html
# or
python3 -m http.server 8080
```
