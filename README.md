# ci-bitrise-deploy-step
This step deploys multiple apk's (android) or ipa's (IOS) to hockey app. It expects to find information about the builds in an ENV called HOCKEYBUILDSJSON
generated by the gradle plugin (insert url to gradle plugin github project here)

The build information format is:
```
[
	{
		"build": "app-first.apk",
		"hockeyId": "11111111111111111111111111111",
		"appId": "dk.nodes.citestflavors.firstskin","mappingFile": "null"
	},
	{
		"build": "app-second.apk",
		"hockeyId": "11111111111111111111111111111",
		"appId": "dk.nodes.citestflavors.secondskin","mappingFile": "null"
	}
]
```

##  Inputs

Following inputs are needed. Project slack channel are where the builds are announced and error slack channel are where the errors get posted
	- PROJECT_SLACK_CHANNEL: "#bitrise"
  	- ERROR_SLACK_CHANNEL: "#bitrise"

## Secrets

In order to post to slack and deploy to hockey to secret values are defined in .bitrise.secret.yml:
	- HOCKEY_TOKEN: 11111111111111111111111
	- SLACK_WEBHOOK_URL: ttps://hooks.slack.com/services/SOMETHING/SOMETHING
