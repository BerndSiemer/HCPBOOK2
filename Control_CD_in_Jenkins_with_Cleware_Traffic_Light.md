## Prerequisites
- Raspberry Pi with Raspbian, clewarecontrol and access to the internal network at SAP 
- Cleware Traffic Light
- Jenkins Instance

# Creating a service account
1. Request for a service account [here](https://service-accounts.wdf.sap.corp/) and wait until it is granted.
2. Add the new account to your Jenkins.

# Using the Jenkins Api for checking the pipeline state
1. Install JSON parser jq by entering ```sudo apt-get install jq```.
2. Edit the config file with your properties.
3. Use the bash script. 
