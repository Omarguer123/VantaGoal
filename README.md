# VantaGoal Auto Live API Dashboard

This version automatically loads football fixtures when the website opens.

## What changed

- No button click is needed after deployment.
- The homepage starts in demo mode, then immediately calls the backend API.
- If the API works, match cards update automatically.
- If the API fails or the key is missing, demo data stays visible.
- It refreshes every 15 minutes to protect free API limits.
- Every API fixture automatically becomes a match card.
- Every match card opens a match center.

## Important security

Your API key is not inside `index.html`.

Add it in Netlify as an environment variable:

`API_FOOTBALL_KEY`

## Netlify setup

1. Upload this folder to GitHub.
2. Connect the repo to Netlify.
3. Go to Site settings > Environment variables.
4. Add `API_FOOTBALL_KEY`.
5. Paste your API key there.
6. Redeploy.

## API routes

- `/.netlify/functions/football?type=fixtures&date=2026-06-22`
- `/.netlify/functions/football?type=live`
- `/.netlify/functions/football?type=standings&league=ID&season=2026`
- `/.netlify/functions/football?type=teams&league=ID&season=2026`

## Refresh time

Inside `index.html`:

`AUTO_REFRESH_MINUTES = 15`

Use 5 minutes only if your API plan allows more calls.
