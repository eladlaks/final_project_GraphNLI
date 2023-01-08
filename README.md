# final project

link to the colab notebook 
{https://drive.google.com/file/d/19l-EeaonCjSV2iajzYFCMypWmkRZ1YzV/view?usp=sharing}

link to the full paper we wrote about the project{https://github.com/eladlaks/final_project_GraphNLI/blob/main/graphNLI_report.pdf}

## About The Project

## the dataset
The data set contains 324373 posts and replies, each one of them is a part of the ”conversation tree”. we split the data into train(80%) and test (20%). each conversation tree
represents the global context, of the local context between 2 sentences in the tree.


## the results
we achieved 82.97% Accuracy compared to 82.41% of the orginal paper result.

## using the same methon to detect hate-speech
we achieved 92.6% Accuracy on "A Benchmark Dataset for Learning to Intervene
in Online Hate Speech”.




<p align="center"><img width=20% src="./images/logo.png"></p>
<p align="center"><img width=40% src="./images/title.png"></p>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
[![Build Status](https://travis-ci.org/anfederico/clairvoyant.svg?branch=master)](https://travis-ci.org/tomp332/Lazy-Wifi)
![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)
[![GitHub Issues](https://img.shields.io/github/issues/tomp332/Lazy-Wifi.svg)](https://github.com/tomp332/Lazy-Wifi/issues)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)



# Table of contents
- [Table of contents](#table-of-contents)
- [About The Project](#about-the-project)
- [Installation and Configuration](#installation-and-configuration)
    - [Mailgun](#mailgun)
    - [AWS](#aws)
    - [Lazy-Wifi](#lazy-wifi)
      - [Docker](#docker)
      - [Local](#local)
- [Usage](#usage)
- [Contact](#contact)
- [Disclaimer](#disclaimer)
  
<br><br>

# About The Project

<div>
  <img src="./images/wifi_logo.svg" alt="Wifi logo" width=130 height=60>
  <img src="./images/aws_logo.png" alt="Aws logo" width=100 height=80>    
  <img src="./images/mailgun_logo.png" alt="Mailgun logo" width=150 height=60>
  <img src="./images/docker_logo.png" alt="Docker logo" width=100 height=80>
</div>
  <br></br>
  In this project we took a published paper(GraphNLI) restored the outcome by building the model and training it. 
  then we improved the model and used the new model archicture for diffrent problem - hate-speech detector. 

   ## Introduction to the orginal paper
   The "GraphNLI" paper addresses part of the problem of hate or misinformative posts in public discussions on forums. It presents a method called "GraphNLI" which takes into account the context of all replies in a discussion, not just the reply and its corresponding post, to classify whether a reply is supporting or attacking the post it is replying to. This method was found to be the most effective at classifying the polarity of replies when compared to other NLP models and methods. It is based on SBERT using RoBERTa and combines pooling and aggregation of results to create the final embedding vector that is fed into a Softmax classifier.


  <br><br>

  
  The following happens when running this automation:
  
- Scans for surrounding access points.
- Deauth optional/all clients assosiated to access points.
- Capture handshakes after deauth
- Send handshakes to brute force AWS EC2 instance or any remote machine of your choice
- Send email after finishing cracking password
 
<br><br>
<br><br>

# Installation and Configuration

### Mailgun
- Create a Mailgun account, https://www.mailgun.com
- Get an API key and sandboxed domain (or a domain of your choice).
- Save the key and domain for the next AWS step.
<br><br>

### AWS

- Create an AWS [account](https://aws.amazon.com) and configure an EC2 instance.
- Setup a private key or password for your EC2 SSH connection, you will be needing them for the Lazy-Wifi configuration.
- Upload `remote_automation.py.py` script to remote machine, and configure the following const variables:
```
# Files settings
    _DICTIONARY_FILE = '<Main dictionary file to load for brute force>'
    _PCAP_FILES_DIRECTORY = '<Directory that handshakes are loaded to>'

# Email settings
  _MAILGUN_EMAIL = '<Mailgun account email address>'
  _MAILGUN_API_KEY = '<API key>'
  _MAILGUN_DOMAIN = '<sandbox domain or your domain>'
  _DESTINATION_EMAIL = '<Destination address>'

```
- Give execution permissions to file:
```
chmod +x crack.py
```
- Install pip libraries
```
pip install requests
```

### Lazy-Wifi 

For both types of installations
- Edit configuration file located in lazy_wifi/config/config.ini
```
[BASIC_CONF]

# Main wifi interface to use
interface_name =

[LOGS]

# Log level for application
log_level = INFO

[RECON]

# Time to scan for all networks
recon_scan_time = 30

[ATTACK]

# Number of deauthentication packets to send to each target
num_deauth_packets = 30

# SSID names to target, if blank all targets will be attacked must be list format
# Structure: ['..', '..']
target_ssid_list = []

[HANDSHAKES]

# Time in seconds to scan for handshakes after deauthentication
handshake_scan_time = 35

[REMOTE_CONNECTION]

# SSH hostname
remote_ssh_hostname =

# SSH username
remote_ssh_username =

# SSH password, if a private key was not specified
remote_ssh_password =

# SSH private key, if none leave blank
private_key_path =

# SSH port, default is 22
remote_connection_port =

# Path to upload all pcap files for cracking default is /home/<remote username>/wifi_uploads
remote_upload_dir =

# Path for the remote automation python script, default is /home/<remote username>/remote_automation.py
remote_automation_script_path =

[AWS]

# Specific machine ID in order to get status and interact with it
instance_id =

# AWS EC2 user key id to control service
aws_access_key_id =

# AWS EC2 user api key
aws_secret_access_key =

# AWS EC2 region where the instance is located for example (eu-central-1)
main_region_zone = eu-central-1

# Option to shut down the instance after finishing the attack
shut_down_on_finish = True
```

- Create virtual enviornment:
```
python3 -m venv lazy_venv
```

- Activate the venv:
```
source lazy_venv/bin/activate
```

- Install requirements:
```
pip install -r lazy-wifi/requirements.txt
```
<br><br>


# Usage

Docker option

- This is needed in order to bridge your wifi interface to the docker container:
```
docker run -it --net="host" --privileged lazy-wifi
```

Local option

- As simple as (with virtual python environment activated, run the interpreter with sudo):
```
sudo lazy_venv/bin/python -m lazy_wifi
```
<br><br>

# Contact

Feel free to open issues and contact me with any question :+1:

<p align="center">

  [![Email](https://img.shields.io/badge/ProtonMail-8B89CC?style=for-the-badge&logo=protonmail&logoColor=white)](mailto:eladlakss@gmail.com)
  [![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/elad-laks/)
  [![Github](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/eladlaks)
</p>

<br><br>

# Credits

[orginal paper](https://paperswithcode.com/paper/graphnli-a-graph-based-natural-language)

[orginal github page](https://github.com/socsys/graphnli)


Enjoy :metal:



