#Openshift Origin on redhat ec2
 
## Prerequisites
 * anisble
 * An ec2 account (and ssh key)
 * A DNS zone

## ToDo
 * Log consolidation
 * DNS zone registration
 
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

To create an environment mapped to XXXXXX.CLOUD.DOMAIN, run the following

 ```bash
 ansible-playbook -i ec2hosts ansible-examples/openshift/openshift_ec2/ec2.yml -e id=XXXXXX -e cloud_domain=CLOUD.DOMAIN
 ```
 
 Will create ec2 images with tags:
    * id=XXXXX
    * type= dns | broker | mq | nodes


#Diagnostics

As root on each box, run the following:
```bash
oo-diagnostics -v
```

or 
```bash
ansible-playbook -i ec2hosts ansible-examples/openshift/openshift_ec2/ec2_diagnostics.yml -e id=XXXXXX


 

