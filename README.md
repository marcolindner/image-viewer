### Image Viewer Stack
---
````
aws cloudformation create-stack \
  --stack-name ts-image-viewer-stack \
  --template-body file://./cloudformation/vpc-ec2.yaml \
  --parameters ParameterKey=InstanceType,ParameterValue=t3.micro \
  --capabilities CAPABILITY_NAMED_IAM
`````
Bilder in das Bucket kopieren:

`````
aws s3 cp images/ s3://ts-image-viewer-stack-bucket/ --recursive``````
