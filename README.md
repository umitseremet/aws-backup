# aws-backup


**Creating:**

*Firstly DR-region(ca-central-1) needs to be created because there is a dependency for primary-region(us-east-1) for DR*

*Run the command below with the specific order*


`aws cloudformation create-stack --stack-name aws-backup --template-body file://aws-backup.yaml` 

*Subscriptions need to be approved via the sent email URLs to be alerted when backup failure happens*



**Cleaning:**

`aws cloudformation delete-stack --stack-name aws-backup`


**Cloud-Custodian Usage**

`custodian  run --output-dir ./LOGS --cache-period 0 -c periodical-prod-backup-tag-checked-for-ec2.yaml`
