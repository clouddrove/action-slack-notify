# Slack Notification- Github Action

This Github Action is use for the <b>slack notification</b> in the github actions CI/CD pipelines. We can just use this action in our CI/CD pipelines in one go, in this doc. we can look into how we can use or call this action in our pipeline.

## Usage

In this below pipeline, we can call or use our <b>Github Action</b> in our steps. We will discuss about it later.

```yml
on: push
name: Slack Notification Demo
jobs:
  slackNotification:
    name: Slack Notification
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2

    - name: Slack Notification
      uses: clouddrove/action-slack-notify@v1
      env:
        SLACK_WEBHOOK: ${{ secrets.SLACK_WEBHOOK }}
```
1. In the Slack Notification step above, we have to use <b>uses</b> keyword for the Github Action calling.

```yml
uses: clouddrove/action-slack-notify@v1
```

2. Second important thing to know or required, we have to provide our <b>Slack Webhook</b> for our actions. For this we are using <b>env</b> keyword.

```yml
env:
  SLACK_WEBHOOK: ${{ secrets.SLACK_WEBHOOK }}
```
