# lambda node template

*note: must use NPM to install!*

## local development
* run `npm start` 

## deploy

### build
- run `make upload`

### new function
- go to Lambda service on AWS
- node 16
- advanced permissions
	- role: lambda-node

### code source
- upload from (load zip file)

### configuration tab 
- general configuration
	- memory: default (1024 or higher for large data processing)
	- timeout: 1m (10m for long running processing)
- environmental variables (if needed)

### test tab
- event name: test
- event json: {}
- run a test

### add trigger
- eventbridge (cloudwatch events)
	- rule name: "cloudwatch-" + lambda function name
	- schedule expression
		- example: every 10 minutes `cron(0/10 * * * ? *)`
		- [https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html](docs)

