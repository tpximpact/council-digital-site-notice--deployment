# council-digital-site-notice--deployment

Repo to manage deployment of the various DSN sites

- `DEPLOYMENT_TARGET_OWNER` - name of the owner of the repo you're sending the event to
- `DEPLOYMENT_TARGET_REPO` - name of the repo you're sending the event to

## Camden

## Lambeth

- environment: `production - lambeth`
- `heroku stack:set container --app=hn-dsn-lambeth`
- `heroku git:remote --remote heroku-hn-dsn-lambeth --app=hn-dsn-lambeth`
- `git push heroku-hn-dsn-lambeth DSNPI-45-sort-hosting-out-for-lambeth-dsn:main`
- `heroku git:remote --remote heroku-dsn-lambeth-production --app=dsn-lambeth-production`
- `git push heroku-dsn-lambeth-production DSNPI-45-sort-hosting-out-for-lambeth-dsn:main`
