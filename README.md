# XI.Forums.AWSDeploy
These are the deployment scripts for the XtremeIdiots.com forums. They deploy the IPS Community platform to AWS.

# Pipeline
Build - [![Build status](https://dev.azure.com/frasermolyneux/XI/_apis/build/status/XI.Forums.Website)](https://dev.azure.com/frasermolyneux/XI/_build/latest?definitionId=64)

https://test.xtremeidiots.com - [![Deployment status](https://vsrm.dev.azure.com/frasermolyneux/_apis/public/Release/badge/9a8cd583-aad3-46f3-a863-a768e462a8fe/1/1)](https://test.xtremeidiots.com)

https://www.xtremeidiots.com - [![Deployment status](https://vsrm.dev.azure.com/frasermolyneux/_apis/public/Release/badge/9a8cd583-aad3-46f3-a863-a768e462a8fe/1/2)](https://www.xtremeidiots.com)

# Workflow
Workflow of the deployment: 
- Ensures that the application exists in AWS, if not creates it
- Ensures that the environment exists and is updated, if not creates it
- Copies the ElasticBeanStalk extensions into the website directory
- Creates a new artifact archive in the working directory
- Ensures that an S3 bucket exists for artifacts
- Uploads the artifact archive to the S3 bucket

# Requirements
The AWSPowerShell module is required to be installed onto the machine running the deployment

# Useful Supporting Commands
`(Get-EBAvailableSolutionStackList).SolutionStackDetails` - This gives a list of the available solution stacks for the ElasticBeanstalk environment.
`Get-AWSRegion` - This gives a list of available regions