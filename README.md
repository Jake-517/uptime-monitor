# Uptime Monitor

Watches **app.leaveitlovely.com** and **forecast.leaveitlovely.com** every ~10 minutes
from GitHub's servers — fully independent of Vercel and of any personal computer —
and posts to Slack the moment either site is down, its SSL certificate is broken,
or a certificate is about to expire without renewing (the cause of the July 14, 2026
outage).

- Checks & alert rules: `.github/workflows/monitor.yml`
- The Slack webhook lives only in this repo's **Actions secrets** (never in code).
- This repo is public solely so the checks run on GitHub's free unlimited Actions
  minutes for public repos; it contains no credentials or private information.
- A monthly keepalive commit stops GitHub from auto-disabling the schedule.

**To test the alerting:** Actions → "Uptime & SSL Monitor" → Run workflow → set
`test_alert` to `true` → a test message appears in Slack.
