# End-to-End CI/CD Setup Documentation

This document outlines the setup for an end-to-end CI/CD (Continuous Integration/Continuous Deployment) pipeline using AWS services. The setup includes the creation of roles, pipelines, and associated resources to enable seamless deployment of code changes.

Creating CI/CD setup and deploying an sample java application using CFT templates.

Action item consists of below parameters:

- Sample java code
- buildspec.yaml 
- Dockerfile
- CFT templates
   - iam.yaml 
   - cicd-cft-template-v2.yaml

Upload the source code in AWS code commit:

![code_commit](images/code_commit.png)

Now create stack in AWS cloud formation template console:

stack name should be - "codepipeline-iam-stack"

Upload iam.yaml file first which will create roles for code build, code pipeline and cloud watch 

provide stack name, codeBucket, CodePipelineArtifactBucket and EcrDockerRepository as below:

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/cf35a719-4d71-421c-b5b3-504e977ef22a)

Below resources are created:

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/6fc5eb84-0e18-4303-af30-ecb62db0d8b0)

Upload cicd-cft-template-v2.yaml

provide codecommit name, branch name, ecr repo name as per the requirement for creating the pipeline

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/d863face-5dbc-4197-9c22-f64612749f4e)

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/b003feaa-1419-45c0-99bd-1e675d9b30ab)

Below resources are created:

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/b7463c24-b644-4513-bd9c-0306c0f47395)

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/68fc8945-111c-4436-80ea-ca482e99ca5d)

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/27191887-6331-4952-be57-d0f3c544cb3f)

simultaneously image has been pushed to ECR repo:

![image](https://github.com/vikash123567/End-to-End-CI-CD-Setup-Documentation/assets/96052543/c66f778e-220c-4510-af00-e8f5cb7a28a1)

This document provides a comprehensive guide for setting up a CI/CD pipeline using AWS services. Follow the steps carefully to ensure a successful deployment and integration of your development workflow.
