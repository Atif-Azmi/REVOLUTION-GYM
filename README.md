# Revolution Gym — Vercel Deploy

Pre-built static SPA. Two ways to deploy:

## Option A: Vercel CLI (fastest)

```bash
npm i -g vercel
cd revolution-gym-vercel
vercel --prod
```
Accept all defaults. When asked about build settings, just hit enter — `vercel.json` already configures everything.

## Option B: Vercel Dashboard

1. Go to https://vercel.com/new
2. Drag-and-drop this folder onto Vercel's "Add New Project" page (or use "Deploy without Git").
3. Framework Preset: **Other**
4. Build Command: *(leave blank — already built)*
5. Output Directory: `.`
6. Click **Deploy**.

`vercel.json` rewrites all routes to `index.html` so the SPA router works.

## Razorpay

The build embeds the **test publishable key** (`rzp_test_…`). Override in production
by setting `VITE_RAZORPAY_KEY_ID` in Vercel's Environment Variables and rebuilding.
The Razorpay **secret key** is never bundled — it's only needed if you add a backend
endpoint for order creation and signature verification.
