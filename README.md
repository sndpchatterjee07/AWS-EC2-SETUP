### Instructions for [AWS Account Setup](https://aws.amazon.com/pm/ec2/) (12 Months Free Tier) 

## Amazon EC2 on the Free Tier

**12 MONTHS FREE**

AWS helps new customers get started for free. Each calendar month, the Amazon EC2 Free Tier allows you to use:

- 750 hours per month of Linux, RHEL, SLES, or Windows t2.micro or t3.micro instance dependent on region


## CREATING THE AWS ACCOUNT.

![img](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/5174c7bc-8566-4162-9717-79dccb89fbfd)




Given that certain pieces of this information are confidential, they have been suppressed.


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


***VERY VERY IMPORTANT*** 

- As soon as the AWS EC2 instance is created, allocate an `Elastic IP` and map it to the newly created `instanceid` under `Network & Security`.

   ![Screenshot from 2023-09-25 10-03-28](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/67352af8-2670-4d2b-b4bc-ff2ef47670fe)
 

- Configure `Security Groups` to allow HTTP & HTTPS data under `Network & Security` -> `Security Groups`

   ![Screenshot from 2023-09-25 10-11-09](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/e96b8740-7631-4915-a61f-5715a34efed3)
 



## CONNECTING TO THE EC2 INSTANCE:

***Connect to your Linux instance using an SSH client or from a terminal using Elastic IP Address***
  
 - `ssh -i "/path/my-key-pair.pem" ubuntu@XXX.XXX.XXX.XXX`


## CONFIGURING APACHE SERVER ONCE CONNECTED TO EC2 INSTANCE:

***Login as root and run the following commands one by one***

    apt-get update && apt-get upgrade
    apt-get install apache2
    ufw allow "Apache Full"
    ufw allow 80

***Navigate to the var directory under apache as root and change ownership and assign permissions to www-data***

    root@ip-@@-@@-@@-@@:/var# sudo chown -R www-data:www-data /var/www/
    root@ip-@@-@@-@@-@@:/var# chmod 755 /var/www/html 


## MAPPING THE EC2 INSTANCE TO A [DOMAIN/SUBDOMAIN](https://my.noip.com/):

![Screenshot from 2023-10-01 02-04-39](https://github.com/sndpchatterjee07/AWS-EC2-SETUP/assets/3818950/67a5d263-a3f0-4cc8-a5aa-261d5e472591)


## SECURING THE SITE THROUGH SSL USING [certbot](https://certbot.eff.org/instructions?ws=apache&os=ubuntufocal)

Login as a `root` user.

```
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot

root@ip-@@@-@@@-@@@-@@@:/home/ubuntu# sudo certbot --apache
Saving debug log to /var/log/letsencrypt/letsencrypt.log

Which names would you like to activate HTTPS for?
We recommend selecting either all domains, or all domains in a VirtualHost/server block.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: @@@@@.ddns.net
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate numbers separated by commas and/or spaces, or leave input
blank to select all options shown (Enter 'c' to cancel): 1
Requesting a certificate for @@@@@.ddns.net

Successfully received certificate.
Certificate is saved at: /etc/letsencrypt/live/@@@@@.ddns.net/fullchain.pem
Key is saved at:         /etc/letsencrypt/live/@@@@@.ddns.net/privkey.pem
This certificate expires on 2023-12-30.
These files will be updated when the certificate renews.
Certbot has set up a scheduled task to automatically renew this certificate in the background.

Deploying certificate
Successfully deployed certificate for @@@@@.ddns.net to /etc/apache2/sites-available/000-default-le-ssl.conf
Congratulations! You have successfully enabled HTTPS on https://@@@@@.ddns.net

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
If you like Certbot, please consider supporting our work by:
 * Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
 * Donating to EFF:                    https://eff.org/donate-le
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
root@ip-@@@@@-@@@@@-@@@@@-@@@@@:/home/ubuntu# apachectl -t -D DUMP_VHOSTS
VirtualHost configuration:
*:443                  @@@.@@@.@@@.@@@ (/etc/apache2/sites-enabled/000-default-le-ssl.conf:2)
*:80                   @@@.@@@.@@@.@@@ (/etc/apache2/sites-enabled/000-default.conf:1)
```



The site `https://@@@@@.ddns.net` now runs on SSL. :))







