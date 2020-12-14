# Project Information
Infrastructure Setup: Jenkins server with SSL using Let's Encrypt

# Team information

| Team Members        | Github Id            | NUID      |
| ------------------- |:--------------------:|:---------:|
| Suhas Pasricha      | suhas1602            | 001434745 |
| Puneet Tanwar       | puneetneu            | 001409671 |
| Cyril Sebastian     | cyrilsebastian1811   | 001448384 |
| Shubham Sharma      | shubh1646            | 001447366 |

# Infrastructure Instructions

### Setup
```
AWS_PROFILE=<profile_name> AWS_REGION=<region> ansible-playbook -i development  aws_vpc_ec2_setup.yml --extra-var "ec2_instance_size=<instance_size> key_pair=<ec2_key_pair> elastic_ip=<elastic_ip_address> route53_zone_name=<domain_name> route53_record_name=<jenkins.domain_name> letsencrypt_email=<your_email_id> domain_name=<jenkins.domain_name> staging_cert=false"  -vvv
```

### Teardown
```
AWS_PROFILE=<profile_name> AWS_REGION=<region> ansible-playbook -i development aws_vpc_ec2_teardown.yml --extra-var "key=app value=jenkins elastic_ip=<elastic_ip_address>"
```
