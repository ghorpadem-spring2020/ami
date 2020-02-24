# ami
# This JSON is used to create AMI for EC2 
## Validate Template
packer validate ubuntu-ami.json

## Build AMI
packer build \
    -var 'aws_access_key=REDACTED' \
    -var 'aws_secret_key=REDACTED' \
    -var 'aws_region=us-east-1' \
    -var 'subnet_id=REDACTED' \
    ubuntu-ami.json
     OR
     packer build -var-file=./vars.json ubuntu-ami.json
     

## CircleCi
This Repository is listen by CircleCi build job.
Every time Changes are merged to Master branch, an AMI is created by using packer.
