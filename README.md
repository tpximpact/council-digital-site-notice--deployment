# council-digital-site-notice--deployment

Repo to manage deployment of the various DSN sites

- `DEPLOYMENT_TARGET_OWNER` - name of the owner of the repo you're sending the event to
- `DEPLOYMENT_TARGET_REPO` - name of the repo you're sending the event to

## Setup

- Copy `.github/workflows/send-event-staging.yml` into your `.github/workflows/` folder - 🚨 **dont forget to check the target branches** 🚨
- Copy `.github/workflows/send-event.yml` into your `.github/workflows/` folder

## Camden

- environment: `not needed`
- deploys to `netlify` via [this repo](https://github.com/tpximpact/camden-digital-site-notice/)
- requires fine grained personal access token with
  - contents: set to read and write
  - metadata: set tp read only

## Lambeth

- environment: `production - lambeth`
- deploys to `heroku`
