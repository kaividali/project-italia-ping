# project-italia-ping

Wakes [Project Italia](https://project-italia-nu.vercel.app)'s watcher every 15 minutes, so its country dashboard keeps
sampling prices and trades when nobody is on the site. Vercel's free plan allows one cron a day; GitHub Actions is free
for public repositories.

- `.github/workflows/ping.yml` calls `/api/cron/watch` with the `CRON_SECRET` repository secret and logs only the HTTP
  status. The watcher only reads the game.
- A weekly run enables the workflow again, because GitHub pauses schedules in public repositories after 60 days
  without activity.
