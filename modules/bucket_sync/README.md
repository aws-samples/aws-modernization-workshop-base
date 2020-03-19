## Bucket Pipeline Setup

**Purpose:** Instructions for creating a pipeline that copies files from the repo to an 
S3 Bucket. The intent is to make cloudformation templates available to include into nested stacks.

1. Edit and deploy the pipeline in pipeline.yaml.  You will probably want to change the first 4 parameters.  

> Stack completes in about 1-2 minutes  
```
### DO NOT FORGET TO CHANGE THE STACK NAME
aws cloudformation create-stack --stack-name CFN-to-S3-Pipeline --template-body file://pipeline.yaml --capabilities CAPABILITY_NAMED_IAM
```

If you check the Build Pipeline and Build logs you should see files successfully copied to your S3 bucket.  