# AI Pipeline — Outreach Dashboard

A static dashboard for working through 1,549 qualified Oil & Gas CEO/President/Founder leads. Open each contact's LinkedIn, copy the personalized message, send the DM, then tick them off. Progress is saved in your browser's localStorage.

## Files

- `index.html` — the dashboard UI (single file, no build step)
- `leads.json` — 1,549 qualified leads with personalized AI Pipeline messages (each under 300 chars)
- `vercel.json` — Vercel config (clean URLs, no caching on leads.json)

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
# any static server works — examples:
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Deploy to Vercel

**Option A — Vercel CLI**
```bash
npm i -g vercel
cd dashboard
vercel deploy --prod
```

**Option B — Drag and drop**
Go to https://vercel.com/new, drag this folder onto the page, deploy.

**Option C — Git**
Push the `dashboard/` folder to a GitHub repo, then import the repo in Vercel.

## Notes

- Messaged status is stored in `localStorage` under the key `aipipeline.messaged.v1`. It persists in the browser you're using — switching browsers or devices means starting fresh.
- The "Export sent CSV" button downloads a CSV of contacts you've checked off.
- "Reset" clears all message-sent marks (with confirmation).
- To update the lead list later, regenerate `leads.json` and redeploy — IDs are derived from each LinkedIn URL, so existing checked-off contacts stay marked as long as their LinkedIn URL doesn't change.
