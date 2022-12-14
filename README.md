# Deploy to AWS Amplify

## Deployed Url:
https://dev.dz3btwpjryh1f.amplifyapp.com

## Preparing for deployment:
Run the following command to create tezjs project:
  - `npm create tez@latest`
  - `cd [projectName]`
  - `npm install` - for installing the required dependencies
  - `npm run build` - for build the project
  - `npm run dev` - for run the project

## Pre-requisites:
Make sure you have:
  - AWS account.
  - create a zip of dist folder.
  - keep that zip in local or push that zip on any s3 bucket.

## Deployment to AWS Amplify using Console
Go to https://aws.amazon.com/amplify/console/ to get started.
1. Create a hosting web app on amplify.
2. Choose any mention method you want for uploading the zip on amplify.
3. Provide the App name and Environment Name 
4. Click on save and deploy.

## Deployment to AWS Amplify using aws-cli
Install the cli from here as per respective os https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html and need to configure aws using aws configure command
1. Create a hosting web app on amplify:
  ```
  aws amplify create-app --name <projectName>
  ```
2. Create a environment name on that created app:
  ```
  aws amplify create-branch --app-id [appId] --branch-name [branchName]
  ```
3. Deploy created zip on amplify using aws cli:
  ```
  aws amplify start-deployment --app-id [appId] --branch-name [branchName] --source-url [s3bucket url]
  ```
  
## References:
 - [Manual deploy to Amplify](https://docs.aws.amazon.com/amplify/latest/userguide/manual-deploys.html)
 
