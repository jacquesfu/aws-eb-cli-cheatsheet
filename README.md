# Elastic Beanstalk CLI Cheat Sheet
This cheat sheet is a reference for the EB CLI, which is a commandline interface that is more user-friendly than raw AWS CLI commands for managing Elastic Beanstalk instances.

## Quick Start

Install / Update EB CLI

```
// Linux
$ pip install --upgrade --user awsebcli

// Mac
$ brew install awsebcli
```

Initialize `eb cli` in the working directory. You will need to choose `Application`->`Environment`.

```
$ eb init
```

This will create and deploy the new environment at the same time. Then open in your browser.

    $ eb create
    $ eb open

Subsequent deployments can be made through a simple deploy subcommand. Uncommitted staged files can also be added with the `--staged` flag.

    $ eb deploy
    $ eb deploy --staged

## Basic Configuration

Edit document root

    $ eb config

View and Set Environment variables

```
$ eb printenv
$ eb setenv eb [VAR_NAME=KEY]
```

## Common Tasks

List environments and show current

    $ eb list

Change current environment

    $ eb use [environment]

Browse log files

    $ eb logs

List, get, save locally and update configuration.

```
$ eb config list
$ eb config get [config]
$ eb config save
$ eb config put [config]
```

Apply configuration on current environment.

    $ eb config --cfg [config]

Deploy using saved configuration

    $ eb create [environment] --cfg gateway

Deploy worker environment

    $ eb create [environment] -t worker

## All commands

```
abort       Cancels an environment update or deployment.
clone       Clones an environment.
config      Edits the environment configuration settings or manages saved configurations.
console     Opens the environment in the AWS Elastic Beanstalk Management Console.
create      Creates a new environment.
deploy      Deploys your source code to the environment.
events      Gets recent events.
health      Shows detailed environment health.
init        Initializes your directory with the EB CLI. Creates the application.
labs        Extra experimental commands.
list        Lists all environments.
local       Runs commands on your local machine.
logs        Gets recent logs.
open        Opens the application URL in a browser.
platform    Manages platforms.
printenv    Shows the environment variables.
scale       Changes the number of running instances.
setenv      Sets environment variables.
ssh         Opens the SSH client to connect to an instance.
status      Gets environment information and status.
swap        Swaps two environment CNAMEs with each other.
terminate   Terminates the environment.
upgrade     Updates the environment to the most recent platform version.
use         Sets default environment.
```
