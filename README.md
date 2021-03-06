# Slack - mail DevOps Management

## Overview

The provided sample includes:
- Get a bot user token in Slack
- Post email notifications from Gmail to Slack as messages. The sample Solution sends out emails' summary in formatted messages to Slack from your configured Gmail account. You can post messages to any channel you want to alert containing the information concerning the mails you want to pass on.

This sample shows how Linx automatically reads emails from GMail and post formatted messages to Slack.
Once this Slack integration is active, the sample posts messages to Slack Channel. 

---

### Additional resources
- [Create New App in Slack](https://api.slack.com/apps)
- [Slack API documentation](https://api.slack.com/apis)
- [Test apis from browser](https://api.slack.com/methods/chat.postMessage/test)
- [Slack reference for block kit](https://api.slack.com/reference/block-kit)
- [How to find your Channel Id in Slack](https://stackoverflow.com/questions/40940327/what-is-the-simplest-way-to-find-a-slack-team-id-and-a-channel-id) 
- [How to use the ReadEmail plugin from Linx](https://linx.software/docs/reference/plugins/email/content/reademail/?utm_source=linx&utm_medium=designer&utm_campaign=help)
---

## Dependencies

### Pre-requisites

- Linx Designer
- Slack account
- Gmail account

### Linx Designer

This solution was developed in the Linx Designer `v5.21.0.0`

---
## Setting up the sample
#### Get a bot user token from Slack
1. [Create a new app](https://api.slack.com/apps)
2. Choose from Scratch.  
      - Enter App Name, e.g linx-bot-github
      - Choose a workspace and click on create app

3. Under 'Add features and functionality' 
      - Click on **Bots**

4. Under 'First, assign a scope to your bot token'
      - Click on **Review Scopes to Add** 
5. Go to `Scopes` section
      - Click on **Add an OAuth Scope**
       - Choose the following from the list:
       	- im:history
       	- chat:write
       	- channels:history
       	- im:write
       	- chat:write.public
       	- channels:read  
       	- groups:read  
       	- im:read  
       	- mpim:read 
6. As the above is done, a message `You can now show tabs on App HomeManage which tabs your user sees in your app???s home.??Go to App Home` will appear.
7. Scroll the page up and go to the section `OAuth Tokens for Your Workspace`
8. Click on the button **Install to workspace** and click on **Allow**
9. Once successful, you will be directed to the `OAuth Tokens for Your Workspace` section
10. Click on the **Copy** Button to copy the Bot User OAuth Token. Note that it starts with `xoxb-`

#### Configure the Solution's $.Settings for Slack :
1. `SlackBotUserOAuth`: Paste the **token** copied above
2. `SlackUri` : Slack API Url. 
3. `SlackChannel` : Channel yo post messages
   
#### Configure the Solution's $.Settings with your email details :

> [Linx email configuration](https://linx.software/docs/reference/plugins/email/content/reademail/?utm_source=linx&utm_medium=designer&utm_campaign=help) will help you get started with email plugin in Linx.

> _This sample was setup using a Gmail instance._

1. `GmailUserName:` Username of your email account.
2. `GmailPassword:` App password.

--

## Using the sample

### Authentication for Slack

Requests are authenticated via a Bearer access token included in the `Authorization` header of each request.

When making requests to the GitHub, you must also include the following header:

```
Accept: application/x-www-form-urlencoded , application/json
```
---

## Slack Utilities Samples 
### AuthorizationTest
A function to test if you've entered the right token and the right channel.  Tests the api https://slack.com/api/auth.test.
### BuildSampleBlock
- Parameters:
    - `email`: Linx type. 
- Result: 
    - `blocks`: JSON format as string type. 
### PostMessageAPI 
Calls the Post message API https://api.slack.com/methods/chat.postMessage
- Parameters:
   - `blocks` : JSON format as string type.  
---
## Running the Sample
### PostEmailContentsToSlack
- In the Demo Folder, Click on the function named PostEmailContentsToSlack.


