# Council Digital site notice deployment manager

This repository acts as a deployment manager for the [Digital site notice](https://github.com/tpximpact/council-digital-site-notice) application.

[Digital site notice](https://github.com/tpximpact/council-digital-site-notice) is an open source single tenancy self hosted application and as such we don't want environment specific deployment information in the code base.

This repo is responsible for managing the deployment of various instances that are being managed by the project.

## Deployments

🚨 Each deployment should be setup in its own environment within github actions 🚨

## Camden - also acts as the main development site

Deploys to `netlify` via [this repo](https://github.com/tpximpact/camden-digital-site-notice/)

Uses a deploy key.

Github environmental secrets required:

`CAMDEN_GITHUB_DEPLOY_EMAIL`
`CAMDEN_GITHUB_DEPLOY_TOKEN`

### Staging

- environment: `staging - camden`
- url: [staging--camden-digital-site-notice.netlify.app](https://staging--camden-digital-site-notice.netlify.app/)

### Production

- environment: `production - camden`
- url: [camden-digital-site-notice.netlify.app](https://camden-digital-site-notice.netlify.app/)

## Lambeth

- deploys to `heroku`

### Production

- environment: `production - lambeth`

## About this repo

This repo contains a number of workflows to manage deployments to different environments for differnt LAs.

It does this by listening for an event from the main repo and runs the associated actions.

## Connecting this repo to DSN

`send-event.yml` and `send-event-staging.yml` are responsible for sending the events from the [Digital site notice](https://github.com/tpximpact/council-digital-site-notice) repo.

You will need to copy these over to the DSN repo so that they can send the appropriate events, they can also be used inside this repo to test things.

- Copy `send-event-staging.yml` into your `.github/workflows/` folder - 🚨 **dont forget to check the target branches** 🚨
- Copy `send-event.yml` into your `.github/workflows/` folder

You will need too configure the following env vars:

In the [DSN deployment manager](https://github.com/tpximpact/council-digital-site-notice--deployment):

- `DEPLOYMENT_TARGET_OWNER` - name of the owner of the repo you're sending the event to
- `DEPLOYMENT_TARGET_REPO` - name of the repo you're sending the event to
