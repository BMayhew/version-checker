# Version Checker

This repo contains a github action that will allow you to stay up to date with the latest changes from github repositories you care about. The version checker is currently configured to monitor [Playwright](https://github.com/microsoft/playwright/releases) releases. To change this, modify the version-checker.yml file with the github repository you intend to watch.

To get the the version checker slack notification working, you should be able to:

* Fork this repository
* Create a Slack Incoming Webhook Url
  * Slack Administration -> Manage Custom Apps
  * Search Directory for `Incoming Webhooks` and Add to Slack.
  * Choose your channel and click Add Incoming Webhook Button
  * Finish configuring saving the Webhook URL `https://hooks.slack.com/services/******/******/*******` was how mine looked.
* Create a Github Actions Secret here `https://github.com/<your_name>/version-checker/settings/secrets/actions` with the name `SLACK_WEBHOOK_URL` and value `https://hooks.slack.com/{Your Webhook URL}`

Now every weekday at 12:05AM the github actions job will run. If there is a new release you will be notified in slack.

For testing purposes you can also browse to your repo -> Actions -> Select `Version Checker` workflow and you should have a Run Workflow dropdown that can be used to manually trigger the job.
