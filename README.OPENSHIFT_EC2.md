#Openshift Origin on redhat ec2
 
## Prerequisites
 * anisble
 * An ec2 account (and ssh key)
 * A DNS zone

## Setup
 
### Environment variables:
 ```bash
 BOTO_CONFIG=<path to botoconfig file>
 ```
### Boto config
 
 ```ini
[Credentials]
aws_access_key_id=<your access key>
aws_secret_access_key=<your access key secret>
 ```
 
#Execution
 ```bash
 ansible-playbook -i ec2hosts ansible-examples/openshift/openshift_ec2/ec2.yml -e id=XXXXXX
 ```
 
 Will create ec2 images with tags:
    * id=XXXXX
    * type= dns | broker | mq | nodes
 

