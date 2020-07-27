### Instructions for AWS Account Setup(12 Months Free Tier) 

## CREATING THE AWS ACCOUNT.

1. Email address:
2. Password:
3. AWS account name:
4. AWS account type:
5. Payment Information:

## ACCOUNT AUTH INFO.
1. `https://pastebin.com/JGGvSjjm`


## STEPS FOR SETTING UP AN EC2 INSTANCE:

1. Choose an Amazon Machine Image (AMI)
2. Choose an Instance Type
3. Configure Instance Details(Default Values)
4. Add Storage
5. Add Tags
6. Configure Security Group
7. Review
8. Create a Key-Value pair
    > A key pair consists of a public key that AWS stores, and a private key file that you store.
    > Together, they allow you to connect to your instance securely.

## CONNECTING TO THE EC2 INSTANCE:

1. Connect to your Linux instance using an SSH client or from terminal
  
 - `ssh -i "/path/my-key-pair.pem" ubuntu@ec2-XXX-XXX-XXX-XXX.XXX-XXX-XXX.compute.amazonaws.com`
 - `ssh -i "/path/my-key-pair.pem" ubuntu@XXX-XXX-XXX-XXX`


## IAM CONSOLE URL AND LOGIN DETAILS

 - `https://***12-digitaccountid***.signin.aws.amazon.com/console`

## SOFTWARE INSTALLATIONS

1. Installing default JDK

 - `sudo apt install default-jdk`

2. Installing Tomcat 9

- `sudo apt-get install tomcat9`
- `sudo apt-get install tomcat9-admin`
- `sudo apt-get install tomcat9-docs`
- `sudo apt-get install tomcat9-examples`

3. Enabling UFW and setting up following rules
   ***Tested locally but not tried on EC2***
- `sudo ufw enable`
- `sudo ufw allow 8080`
- `sudo ufw allow proto tcp to 0.0.0.0/0 port 8080`

- Tomcat default access URL: `http://XXX.XXX.XXX.XXX:8080/` (The public IP address could be mapped to the actual domain).
