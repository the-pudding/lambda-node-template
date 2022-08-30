# lambda node template

*note: must use NPM to install!*

## setup

### new function
	* node 16
	* advanced permissions
		* role: lambda-node

### code source
	* upload from (load zip file)

### configuration tab 
	* general configuration
		* memory: can bump up (.e.g, if doing a lot of processing, but default is fine for not loading lots of data into memory (e.g, 1024)
		* timeout: 1-10m (for long running processing apps)
	
	* environmental variables (if needed)

### test tab
	* event name: test
	* event json: {}
	* run a test

### add trigger
	* eventbridge (cloudwatch events)
		* rule name: "cloudwatch-" + lambda function name
		* schedule expression: every 10 minutes `cron(0/10 * * * ? *)`
			* [https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html](docs)

## local development
run `npm start` 