# box-keepalive

GitHub Actions watchdog keeping the instabox `box` machine awake.

- Heartbeat every ~30 min via instabox exec API (resets the 30-min idle auto-suspend)
- If machine is suspended: POST /start to wake it; gateway auto-recovers via systemd linger
- Daily self-commit (.last-beat) keeps the repo active so GitHub never disables the schedule (60-day rule)
- Secret INSTABOX_API_KEY holds the instabox API key

Local backup: Windows scheduled task InstaBoxKeepalive every 15 min on the user's PC.
