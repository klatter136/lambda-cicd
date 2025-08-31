<h1>GitHub Actions</h1>



<h2>Project Description</h2>

This project uses GitHub Actions to build CICD pipelines for AWS. GitHub Actions is an automation service built into GitHub that lets you run workflows whenever something happens in your repository, like pushing code or opening a pull request. In the first workflow, changes to code trigger a pipeline that installs dependencies, packages the application, and deploys it to a Lambda function. In the second workflow, opening or updating a pull request triggers a pipeline that validates and tests a CloudFormation template by creating a temporary stack in AWS, commenting the results on the PR, and then deleting the test stack after the PR is merged. Together, these examples show how GitHub Actions can automatically handle builds, tests, and deployments in a repeatable and secure way without manual effort.


<h2>CICD for Lambda Function</h2>

<img width="1687" height="687" alt="image" src="https://github.com/user-attachments/assets/245d67b2-5b0f-45aa-a7b5-c29d5cefe9e8" />

A CICD pipeline for Lambda is an automated way to deploy your function whenever you update your code. In this setup, you push changes to GitHub, which triggers a GitHub Actions workflow. The workflow uses GitHub Secrets to securely provide AWS credentials, then a runner checks out your code and sets up the Python environment. Next, dependencies are installed, and your code plus those dependencies are packaged into a Lambda deployment bundle. Finally, the bundle is deployed to AWS Lambda. This makes the process faster, more consistent, and secure compared to uploading code manually.


<h2>CICD for CloudFormation Test Stacks</h2>

<img width="1529" height="955" alt="image" src="https://github.com/user-attachments/assets/5c78c227-7024-4f8e-ac88-daf603ca3861" />

This workflow sets up CICD for testing CloudFormation templates whenever a pull request is opened or updated. When you push code and create a PR, GitHub Actions is triggered. The workflow uses GitHub Secrets to provide AWS credentials, then a runner checks out the code and configures the AWS CLI. From there, the CloudFormation template is validated and deployed as a temporary test stack in AWS. The results are posted back as comments on the PR so you can see right away if the template works. If everything looks good, the PR is merged, and the test stack is automatically deleted. This way, you can safely validate infrastructure changes before they reach production.




