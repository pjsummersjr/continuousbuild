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
* yo express (feel free to choose the settings that are most comfortable to you)

## Create and configure your Azure website using the Azure CLI
* Create your website: azure site create <site name>
* Link your website to your remote GitHub repo: azure site deployment github <site name>
    * The CLI will ask you for a username and password for your GitHub account. If you use a standard basic authorization, just enter your normal username and password. If you have multi-factor authorization (MFA) enabled, you'll need to generate a Personal Access Token on the GitHub site and use that token as your password.
    * The CLI will then ask you to choose a repo to link to

## NOTES!
* Enable logging with the Azure log streaming service to detect issues: azure site log tail <site name?
* I ended up copying the contents of bin/www to ./server.js and modifying package.json to call node server.js instead. I was getting an error in the Azure website related to relative paths from bin/www and I am more familiar with the server.js approach.

## Resources
https://blogs.msdn.microsoft.com/microsoftimagine/2015/09/01/using-continuous-integration-with-azure-github/
https://azure.microsoft.com/en-us/documentation/videos/create-a-nodejs-site-deploy-from-github/
https://azure.microsoft.com/en-us/search/?q=github
    

