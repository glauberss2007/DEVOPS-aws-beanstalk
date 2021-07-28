# aws-CI-CD

AWS DevOps Continuous Integration and Delivery CI/CD for NodeJS using AWS CodePipeline, AWS Elastic Beanstalk and Mocha.
![image](https://user-images.githubusercontent.com/22028539/127194861-b2c03563-51e7-4fe2-8595-4654645a30c8.png)

## AWS CodePipeline tools options
![image](https://user-images.githubusercontent.com/22028539/127194900-ba6446c1-b06a-4552-88e7-0b1345ce040a.png)

## Continuous Integration and Delivery (CI/CD) with AWS CodePiline - Steps
1. [Creating an Elastic Beanstalk environment](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.environments.html) for Node.js app and check High Availability at "configure more options"

- [Optional - Create the repository with you node.js web app](https://kbroman.org/github_tutorial/pages/init.html)

2. [Create AWS pipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/pipelines-create.html)

- [Optional - Configure jenkins build script compile and test](https://docs.aws.amazon.com/codebuild/latest/userguide/jenkins-plugin.html)
- [Optional - Configure AWSCodeBuild script for test and compile](https://docs.aws.amazon.com/pt_br/codebuild/latest/userguide/how-to-create-pipeline.html)

- At deployment provider select "AWS Elastik Beanstalk" seting up the ENV and APP names.

- [Optional - Create a role that allows AWS codePipeline to access the resource](https://docs.aws.amazon.com/codepipeline/latest/userguide/pipelines-create-service-role.html#:~:text=When%20you%20create%20a%20pipeline,associated%20to%20that%20service%20role.)

Review the pipeline and click on crete to see pipline stages runing status. Go to Elastick beanstalk, click on refresh and them to backspaceintro-env to view the web app page. 

PS: Now you can change the nodejs code and them it will automaticaly start the AWS pipeline to expose the changes.

## Integrating CI/CD Build and Test Processes with CodeBuild & Mocha - Steps
![image](https://user-images.githubusercontent.com/22028539/127392357-6bad0ec8-0b75-4d43-9c82-a9ffcd984fb3.png)

### Macro view
![image](https://user-images.githubusercontent.com/22028539/127392748-0b8d5cdb-80f5-4d7f-a162-529f3ce2c591.png)

1. Take a look on the .yml buld files example at this repository.
2. Create AWS CodePipeline configuring the step 2 related to SOURCE with your git provider, repository name and branch.
3. Configure step 3 related to build as below:
  ```
  - Build provider: AWS CodeBuild
  - Create a new build project
  - Environment: Use ubuntu image managed by AWS CodeBuild in a node.js runtime at your version (in thic case 7.0.0)
  - Select buildspec.yml file as source build specification
  ```
4. Save and build.

PS: Other steps can be the same as previous troubleshooting.
  
