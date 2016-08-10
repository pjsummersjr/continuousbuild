# Azure Continuous Build Example
This is an example of how to build an Azure website from scratch (more or less) and configure your Azure website to run continuous builds
based on check-ins to your GitHub repo.

## Pre-requisites
* This assumes that you already have an account on GitHub and have working knowledge of Git - this will not be a tutorial on Git itself (nor am I qualified to author such a tutorial)
* This assumes you have already initialized your repo

## Create your local website
This example uses a NodeJS and a simple ExpressJS website based on the express yoeman template.
* npm install -g yo
* npm install -g express
* yo express
** Create new directory: y
