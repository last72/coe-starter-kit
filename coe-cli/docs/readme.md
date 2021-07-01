# Overview

Once you have an install of the command line interface and it's [pre-requisites](#prerequisites) you can review the following commands

- [ALM Accelerator for Advanced Makers](./aa4am/readme.md) - Use CLI commands to setup and configure an environment for Advanced Makers to enable them to do more.

## Installation

To install the COE CLI

1. Download zip or clone repository

2. Change to unzipped or cloned repository

3. cd coe-cli

```bash
cd coe-cli
```

Nxt select either [Local Install](#local-install) or [Docker Install](#docker-install)

### Local Install

#### Prerequisites

To run the COE CLI application you will require the following

1. An installation of Node 11+ for versions (12, 14, 16)
   a) https://nodejs.org/en/download/
2. Azure CLI is required for user authentication and Azure Active Directory Integration
   a) https://docs.microsoft.com/en-us/cli/azure/install-azure-cli

#### Checking Prerequisites

To check prerequisites installed at the command prompt

1. Verify node version

```bash
node --version
```

2. Verify Azure CLI Version

```bash
az --version
```

#### Install

1. Install application dependencies

```bash
npm install
```

2. Build the application

```bash
npm run build
```

3. Link to the CLI application

```bash
npm link
```

NOTE:
1. On Windows you may need to add %APPDATA%\npm to your PATH environment variable to access the coe command

4. Install Azure CLI. Follow install instructions for you operating system at https://docs.microsoft.com/en-us/cli/azure/install-azure-cli

### Docker Install

One method of installation is via docker.

#### Prerequisites

To run the COE CLI application you will require the following

1. A local install of [Docker](https://docs.docker.com/get-docker/)

#### Install

NOTE: Note on some operating systems you may need to use sudo before each of the docker commands.

1. Build docker image. 

```bash
cd coe-cli
docker build -t coe-cli . 
```

2. Using the docker image

```bash
docker run -it --rm coe-cli
```

This will start a new interactive console (-it) and remove the docker container (--rm) when the console session exits. Using --rm ensures that any cached credentials are removed when you exit.

## Getting Started

Once installed can use -h argument to see help options

```bash
coe -h
```

Authentication for tasks is managed using the Azure CLI. Using standard az cli commands you can login, logout and select accounts. For example

```bash
az login
coe aa4am install -c add
az logoff
```

## Read More

Further reading

- [COE CLI Upgrade](./upgrade.md) How to upgrade to a new version of the COE install.