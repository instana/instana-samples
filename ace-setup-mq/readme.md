# Declaration
The following scripts help you to prepare the IBM MQ objects for ACE monitoring. You can modify these scripts on demand for different environments. As an assistant tool, no official support to these scripts are provided.

# Supported OS
Tested on Ubuntu 20.04, RHEL9.4, AIX 7.2. 
# Instructions for prep-mq.sh
## Descriptions 
The script `setup-channel.sh` is used to create resources and set authority properly in QMGR for ACE sensor. 
* The script must be run with a user who belongs to mqm group and run on the machine which hosts the queue manager.
* The AUTH_USER used in the script is the user that you want to grant authority and it doesn't need to be a privileged user. 
## Usage
1. Download the script `prep-mq.sh`
2. Set it executable `chmod +x prep-mq.sh`
3. Go to the directory and execute the script
```sh
    ./prep-mq.sh -q <QMGR_NAME>  -d <MQ_BIN_PATH> -u <AUTH_USER>
```
# Instructions for revert-mq.sh
## Descriptions
The script `revert-mq.sh` is used to revert the authority granted with script `prep-revert.sh` and delete the objects created in QMGR for ACE sensor. 
* The script must be run with a user who belongs to mqm group and run on the machine which hosts the queue manager.
* The AUTH_USER used in the script is the user that you used in `prep-mq.sh`. 
## Usage
1. Download the script `revert-mq.sh`
2. Set it executable `chmod +x revert-mq.sh`
3. Go to the directory and execute the script
```sh
    ./revert-mq.sh -q <QMGR_NAME> -d <MQ_BIN_PATH> [-u AUTH_USER] [-l LISTENER_NAME]  [-c CHANNEL_NAME]  [-t TOPIC_NAME]
```



