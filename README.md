### Instructions for [AWS Account Setup](https://aws.amazon.com/pm/ec2/) (12 Months Free Tier) 

## Amazon EC2 on the Free Tier

**12 MONTHS FREE**

AWS helps new customers get started for free. Each calendar month, the Amazon EC2 Free Tier allows you to use:

- 750 hours per month of Linux, RHEL, SLES, or Windows t2.micro or t3.micro instance dependent on region


## CREATING THE AWS ACCOUNT.

![img](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/5174c7bc-8566-4162-9717-79dccb89fbfd)




Given that certain pieces of this information are confidential, they have been suppressed and retained [here](https://gist.github.com/sndpchatterjee07/b45776d5c863a8432e41df387685990e).


## STEPS FOR SETTING UP AND LAUNCHING AN EC2 INSTANCE:

1. ***Choose an Application and OS Image (Amazon Machine Image)***

    ![Screenshot from 2023-09-24 15-18-33](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/5ab2968f-6667-4701-9121-f0a8452d8e53)


2. ***Choose an Instance Type***

    ![Screenshot from 2023-09-24 15-19-55](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/975a4ca3-a3b7-488e-9b63-2cc7e42531d4)




3. ***Create a Key Pair `My-EC2-KeyPair.pem`***
    
      ![Screenshot from 2023-09-24 15-23-00](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/16c0fbc3-e29a-47f0-ae8a-dff80a025f76)
  

    
4. ***Network Settings***

    ![Screenshot from 2023-09-24 15-28-50](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/d501e1e2-170d-45c5-9037-f6c72e251c53)



5. ***Configure Storage*** - Default Values

6. ***Advanced Details*** - Default Values


## CONNECTING TO THE EC2 INSTANCE:

1. Connect to your Linux instance using an SSH client or from a terminal
  
 - `ssh -i "/path/my-key-pair.pem" ubuntu@ec2-XXX-XXX-XXX-XXX.XXX-XXX-XXX.compute.amazonaws.com`
 - `ssh -i "/path/my-key-pair.pem" ubuntu@XXX-XXX-XXX-XXX`


## SOFTWARE INSTALLATIONS


