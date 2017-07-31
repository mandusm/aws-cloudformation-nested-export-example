### CloudFormation Nested Stack Deployment 
This repo includes all the resources you need to launch a CloudFormation stack that makes use of Nested Stack Resources and the exported outputs from a Previously used CloudFormation Template.
The Main Deployment template gets the VPC exported outputs from the VPC created by the AWS [QuickStart VPC Reference Template](https://github.com/aws-quickstart/quickstart-aws-vpc)

### Architecture Diagram
![alt text](https://github.com/mandusm/aws-cloudformation-nested-export-example/blob/master/img/flow-diagram.png?raw=true "Architecture Diagram")

### How To
#### Upload Templates to S3.
First, you need to upload the Templates to a S3 Bucket and path of your choice.
Make sure the objects is publicly downloadable.
```
aws s3 cp --recursive --exclude ".git/*" --exclude "img/*" --exclude "*.md". s3://<your-bucket-name>/<your-bucket-prefix>/ --acl public-read
```

#### Run the VPC Template and Wait until completed. 
Open the AWS Cloudformation Console and Create a new CloudFormation stack using the CFDemoVPC.json.
[How To Create a Stack Using the AWS Console](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html)

#### Create a new Nested Stack
Using the same process as before, create a new stack and reference the Stack name for the VPC Stack you just created. 

