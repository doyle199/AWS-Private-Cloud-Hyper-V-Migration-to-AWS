# AWS-Private-Cloud-Hyper-V-Migration-to-AWS
AWS Private Cloud (Hyper-V) Migration to AWS

To do a private cloud (Hyper-V) migration to AWS we must create an SMS role for the migration. In the AWS management console make sure you’re in the US East (N. Virginia) region. Navigate to the IAM console and click on roles in the left menu. Then click the create role button.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/role1.png)

With the AWS service selected, click on SMS for the use case. Then click next: permissions.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/aws_service.png)

Click next: tags. Click next: review. Click create role.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/serviceRole.png)

Next, we must create and complete a replication job with the Server Migration Service (SMS). Navigate to the AWS SMS console and click on the one running connector. 

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/status.png)

Click the import server catalog button.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/connectors.png)

Click on the import button. Check the box next to cent OS server and then click on the create replication job (1) button.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/rep_job.png)

Click on the next button. Select the circle next to one-time migration and make sure the circle is selected for immediately. Then click next.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/config.png)

Click on the create button. Click on the show replication job button to see the status of the job.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/status.png)

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/rep_active.png)

After the replication job finishes, navigate to the AWS EC2 console. Click on instances in the left menu and then the create instance button. 

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/instance_run.png)

Click on My AMIs in the left menu and then the select button for the AMI that was just created.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/My_AMI.png)

Choose the correct instance size and click next until you get to the configure security group tab. 

In the configure security group section add the following rules all with “anywhere” for the source:	TCP port 20-21,	TCP port 10090-10100, UDP port 10090-10100, TCP port 80. Click review and launch. Click the launch button. Select proceed without a key pair and check the acknowledgement box. Then click on the launch instances button. You can SSH into the system using the username and password.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/without.png)

Find the public DNS address and go to it in a browser to see if the webpage is running.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/DNS.png)

Find the IP address and type it into the browser with ftp:// in front of it. Then enter the username and password.

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/signin.png)

![alt text](https://github.com/doyle199/AWS-Private-Cloud-Hyper-V-Migration-to-AWS/blob/master/index.png)



