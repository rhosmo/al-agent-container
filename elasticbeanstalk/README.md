## Deploy the Alert Logic Agent Container for AWS Elastic Beanstalk Multicontainer Docker Platform

## Before You Begin
To deploy the Alert Logic Agent Container for AWS Elastic Beanstalk, you need your unique registration key.

**To find your unique registration key:**

1. In the Alert Logic console, click the Support Information icon.
2. Click "Details."
3. Copy your unique registration key.

## Deploy the Alert Logic Agent Container Definition
**To deploy the Agent Container for Elastic Beanstalk:**
1. Merge the example container definition file from this repository into your own Elastic Beanstalk container configuration file (`Dockerrun.aws.json`). The Agent Container runs as sidecar container with your application container.
2. Merge the example `.ebextensions` configuration into your own Elastic Beanstalk application source bundle.


**To merge and edit the task definition file:**
1. Download the `Dockerrun.aws.json` task definition file from this [directory](Dockerrun.aws.json).

2. In the task definition file, update the `value` variable with your unique registration key.
   ```
   "environment": [
     {
       "name": "KEY",
       "value": "your_registration_key_here"
     }
   ]
   ```
3. Merge the content into your existing `Dockerrun.aws.json` file from the application source bundle that you plan to deploy in Elastic Beanstalk.

<!-- Merge what content? -->

For more info about `Dockerrun.aws.json` formatting, see the [AWS documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html#create_deploy_docker_v2config_dockerrun).

**To merge the ebextensions file:**
1. Download the [`99-al-agent-syslog.config` file](.ebextensions/99-al-agent-syslog.config)

2. Save the file to the `.ebextensions` directory from the application source bundle packages that you plan to deploy in EB

For more info about `ebextensions` formatting, please refer to the [AWS documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/ebextensions.html)
