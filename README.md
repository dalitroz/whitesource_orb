WhiteSource-Scan Orb
==============================

### General Information
CircleCi is continuous integration development practice that is used by software teams allowing them to build, test and deploy applications on multiple platforms in an easier and quicker fashion.


### What is an Orb?

Orbs are CircleCI configuration packages that can be shared across projects. Orbs allow you to make a single bundle of jobs, commands, and executors.

### What is WhiteSource Scanner Orb?

The WhiteSource Scanner Orb is a simple tool that extracts descriptive information from the open source libraries located on your file system and integrates them with WhiteSource.

WhiteSource Scanner Orb enables you to check your container images for compliance and security. Make sure to add the orb to your config.yml file in order to start using it.

The scanner itself is a small, easy to implement vulnerability scanning tool.

### Deployment Process
In order to keep your API token secure, WhiteSource creates a ‘context’ in CircleCI. Contexts provide a mechanism for securing and sharing environment variables across projects. The environment variables are defined as name/value pairs and are injected at runtime.

From CircleCI UI, click on 'Settings' → 'Context', and create a new context.


Add a new variable for the WhiteSource API Token (You can find the API token on the ‘Integrate tab’).
Create a configuration file (the full parameter reference can be found here) with the required parameters for the scan, and set the Configuration file name (including the file path) as a value for the ‘config_file_path’ parameter.

You can now add a comma separated list of directories and/or files to scan.

Commit and push to view the scan results.
In order to view the status, go to the CircleCI GUI and click on ‘jobs’. Click on the relevant job and verify that a ‘success’ message is displayed.

### Related Parameters:

| Parameter  | Description | Required | Default | Type |
| -----------| -------------------------------------------------------------------------------------------------------- | ------------- | ------------- | ------------- |
| api_key  |  Unique identifier of the organization. Can be retrieved from the admin page in your WhiteSource account. | Yes | - | String |
| directory  |  Comma separated list of directories and / or files to scan. | - | . | String |
| config_file_path  |  Configuration file name (including file path) | - | ./whitesource-fs-agent.config | String |

For detailed information, please visit - https://whitesource.atlassian.net/wiki/spaces/WD/pages/680034460/WhiteSource-Scan+Orb
