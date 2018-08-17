# Continuous Deployment
This chapter describes the usefulness of Continuous Deployment and how to setup the system for a new project.

## Philosophy

Continuous deployment is the process of deploying a release directly to staging after every successful pull request. Since it is all automated, there is no human intervention required and less chance of mistakes occurring in deployment, removing issues that arise from mistakes made during deployments.

## Prerequisites
- Microsoft Visual Studio Team Services

## Overview

* Create the project on Visual Studio Team Services
* Create a Git repository for each part of the project (see naming conventions below)
* In the **Build & Release** section, create a Build Definition
* On Azure, create a Web App for the project
* In **Build & Release**, create a Release Definition
* Enable Continuous Deployment option
* Trigger a release
* Confirm that the Azure default landing page appears at the selected URL
* Copy a web.config over from another project into the Azure Web App using KUDU
* Confirm that the website now appears as expected


### Naming Conventions

Project name can be anything, spaces are allowed but discouraged.

Repository names should be projectname-Web and projectname-API where applicable.

Taking *FamousBrandName* as an example:

Project:
* *FamousBrandName*

Repositories:
* *FamousBrandName-Web*
* *FamousBrandName-API*


### Web.config

This file is used to tell IIS that it is managing a NodeJS server, in our case with the filename *app.js*. This is why, before adding it, IIS shows the default Azure landing page. After placing the file, it will correctly forward requests.