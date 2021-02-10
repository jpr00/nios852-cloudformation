# AWS CloudFormation Templates for Infoblox vNIOS Deployment

## Requirements
* [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)
* AWS S3 Bucket to upload Templates

## Upload Templates to S3
* Clone the repository to your workstation
```
git clone https://github.com/jpr00/nios852-cloudformation
cd nios852-cloudformation/templates/
```
* Package local paths referenced by template and upload artifacts to S3 [cloudformation package](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/cloudformation/package.html)
```aws cloudformation package --template-file ./vNIOS_existingVPC_master.json --s3-bucket <Name-of-your-S3-bucket> --output-template-file packaged-vNIOS_master.json --use-json --region <Select_region>```
* To deploy vNIOS with a new VPC, replace ```--template-file ./vNIOS_existingVPC_master.json``` with ```--template-file ./vNIOS_NewVPC_master.json```

## Deploy in CloudFormation
* In the AWS console, navigate to CloudFormation service in your desired region
* Create new stack
* Use the Upload template file option to select your packaged template