
# Install Ambience 2020

## Table of Contents

1. [Requirements](#1-requirements)
2. [Steps](#2-steps)

   2.1 [Install Docker/ Docker Compose](#21-install-docker-or-docker-compose)
   
      * [Ubuntu](#ubuntu)
      
      * [MacOS](#macos)

      * [Windows](#windows)

   2.2 [Access Token](#22-access-token)

   2.3 [Run Installation Script](#23-run-installation-script)

3. [Deploy Elixir Ambience Licence](#3-deploy-elixir-ambience-license)
4. [Demo video](#4-demo-video)

## 1. Requirements

Ambience has to be installed on a Unix OS, including MacOS, Linux and Windows with WSL2.


What you need:

• UnixOS as Ubuntu, OSx, Windows with WSL2

• Docker Desktop/ Docker Engine and Docker compose

• Access token and Elixir Ambience License, which can be requested from sales@elixirtech.com


## 2. Steps

### 2.1 Install Docker or Docker Compose

###  Ubuntu

Click on this [link](https://linuxconfig.org/how-to-install-docker-on-ubuntu-20-04-lts-focal-fossa) for more information.

`sudo apt-get update`

`sudo apt-get install docker.io`

`sudo systemctl enable --now docker`

`sudo usermod -a -G docker ubuntu`

`sudo apt install docker-compose`

Remember to start docker after installation.


###  MacOS

Click on this [link](https://docs.docker.com/docker-for-mac/install/) for more information on Docker installation on MacOS.


###  Windows

Windows WSL2 with docker integration

Click on this [link](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers) for wsl tools installation, and this [link](https://docs.docker.com/docker-for-windows/install/) for docker installation on windows.


### 2.2 Access Token

An access token is required to start the process. You may obtain the token [here](https://drive.google.com/file/d/100cjveaPgcUAZJ5gL8j_aFHcm_PHmau1/view?usp=sharing).


### 2.3 Run Installation Script


 You can run script to complete Ambience docker deployment and run docker-compose.

 This script is designed to install Ambience and Mongodb on a clean system. If you have Mongodb running locally on port 27017 already running you may like to stop the db service first.

`wget http://www.ambience.cloud/docker/setup-ambience-compose.sh`

`chmod 775 ./setup-ambience-compose.sh`

run setup-ambience-compose.sh script and an optional parameter as "aws" for an EC2 instance or "local" for running on your system.

`./setup-ambience-compose.sh` [optional local or aws]

The Ambience server will be started. You access the Web UI at http://localhost:1740 or AWS http://[public aws dns host]:1740. On AWS, please ensure that 1740 port is accessible to you.


## 3. Deploy Elixir Ambience Licence


After Ambience has started. The next step is to deploy the licence file, ElixirAmbience.licence. At Web UI, "Service Chooser" and select the licence deploy module to deploy the licence then logout.

Ambience server has to be restarted. Go the console and at ambience folder and run the command below.

`docker-compose restart elx-ambience`
