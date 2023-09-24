### Instructions for [AWS Account Setup](https://aws.amazon.com/pm/ec2/) (12 Months Free Tier) 

## Amazon EC2 on the Free Tier

**12 MONTHS FREE**

AWS helps new customers get started for free. Each calendar month, the Amazon EC2 Free Tier allows you to use:

- 750 hours per month of Linux, RHEL, SLES, or Windows t2.micro or t3.micro instance dependent on region


## CREATING THE AWS ACCOUNT.

1. ***Root user email address:*** `sandeepchatterjee.connect@gmail.com`
2. ***Root user password:*** `RsG/KM3.6nf9`
3. ***AWS account name:*** `sandeep-chatterjee-24-09-2023`
4. ***AWS account type:***  `Personal - for your own projects`
5. ***Payment Information:*** `Credit or Debit card number`
6. ***Primary purpose of account registration:*** `Personal use`
7. ***Ownership type:*** `Individual`
8. ***Select a support plan:*** `Basic support - Free`
9. ***Console Sign In Link:*** [https://console.aws.amazon.com/](https://console.aws.amazon.com/)
10. ***AWS Account ID:*** `1592-2830-3076`


## STEPS FOR SETTING UP AND LAUNCHING AN EC2 INSTANCE:

1. ***Choose an Application and OS Image (Amazon Machine Image)***

    ![Screenshot from 2023-09-24 15-18-33](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/149a470e-284c-4db2-adb4-25a20a3d19b8)

2. ***Choose an Instance Type***

    ![Screenshot from 2023-09-24 15-19-55](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/5d9da543-d762-4e65-8a9e-53226c0e0a5f)


3. ***Create a Key Pair `My-EC2-KeyPair.pem`***
    
    ![Screenshot from 2023-09-24 15-23-00](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/6788cada-2490-4b69-a5ac-7503958688c8)

    
4. ***Network Settings***

    ![Screenshot from 2023-09-24 15-28-50](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/b130b3d8-dfe2-4e84-af35-75af231ec543)


5. ***Configure Storage*** - Default Values

6. ***Advanced Details*** - Default Values


## CONNECTING TO THE EC2 INSTANCE:

1. Connect to your Linux instance using an SSH client or from a terminal
  
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

3. Enabling UFW and setting up the following rules
   ***Tested locally but not tried on EC2***
- `sudo ufw enable`
- `sudo ufw allow 8080`
- `sudo ufw allow proto tcp to 0.0.0.0/0 port 8080`

- Tomcat default access URL: `http://XXX.XXX.XXX.XXX:8080/` (The public IP address could be mapped to the actual domain).
