These CloudFormation templates are super basic and just for demonstration purposes. IRL you'll also need to set up IAM users, roles, etc, API methods, and probably a bunch of other stuff.

# In This Repo

## CloudFormation commands

### Create Stack

`aws cloudformation create-stack --stack-name test-gateway --template-url https://s3-us-west-2.amazonaws.com/aws-bucket-head/testapigateway.yaml`

### Update Stack
`aws cloudformation update-stack --stack-name test-gateway --template-url https://s3-us-west-2.amazonaws.com/aws-bucket-head/testapigateway.yaml`

### Set up CodeBuild project
Coming soon


## CodeBuild template

### buildspec.yml

If you create a CodeBuild project (manually or via CloudFormation) which calls the buildspec.yml file in theis repo, it'll set up a build server (just installs git), which checks out this repo, copies the test-api-gateway.yaml cloudformation template to S3, and then makes the cli call to run the template, thus creating an API Gateway.
Via API, docs here: http://docs.aws.amazon.com/codebuild/latest/userguide/create-project.html#create-project-cli



# AWS Code Services

## CloudFormation
Templates to define, create, and update AWS services.

## CodeCommit
AWS hosted git repos, similar to Github circa 2012. Rest of Code* services also integrate with GitHub.

## CodeBuild
AWS hosted build server, similar to Jenkins or CircleCI.

## CodeDeploy
If you want deploy anything built with CodeBuild, CodeDeploy can do that.

## CodePipeline
If you want to set up a pipeline that will, for instance, do a build, test it, then deploy it, CodePipeline is your friend.
