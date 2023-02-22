# Cloud-Deployment-Test-Commvault-

## Create VPC and Subnet 2


step 1: In AWS Console, open VPC and click on create VPC
step 2: Give a random name (example:comm_vpc) and enter IPV4 CIDR block for the VPC(example: 10.0.0.0/24)
step 3: click on create VPC
step 4: Now in left side column click on subnets.
step 5: click on create subnet button.
step 6: Enter a name for the subnet (example: comm_subnet)
step 7: select the VPC that was created in step 3 and use same IPVR CIDR as same as of VPC.
step 8: click on create subnet .

### Deploying EC2 instance and connecting it to the subnet 3
step 1: In AWS console search for amazon EC2 and click on "launch instance".
step 2: Select the "Ubuntu Server" for the instances.
step 3: In instance type select "t2.micro" which is available for free tier.
step 4: Go to configuring instance details and select the subnet and VPC that created in step 3, step 8.
step 5: Create new key pair and click on "create new key pair".
step 6: Give a name to the key pair and download it as .pem file(ssh). and click on "launch instance".
step 7: download and open putty , using puttygen convert .pem file to .ppk file.
step 8: load the pem file, select the save private key in ppk formate for putty.
step 9: copy the public IPV4 address of the ec2 instance and paste in the Host Name column of putty.
step 10: follow the step putty > connection > SSH > auth
step 11: Click on browse and select the converted .ppk file
step 12: Run and in terminal window after login as - type "ec2-user"
this successfully connects to the created ec2 instances.


#### create S3 bucket and deploy a static website 4


step 1: In AWS console search for S3 and click on create bucket.(s3sangeebucket)
step 2: Give a bucket name and click on ACL's enabled. 
step 3: untick the option block all public access.
step 4: click on create bucket.
step 5: In the terminal use the following command to install python and pip.
             sudo apt install python3
             sudo apt install python3-pip
step 6: make directory for website.
             mkdir comm_task 
             cd comm_task
step 7: create a html file using following command.
  
step 8: upload the folder in the s3 bucket by clicking the "upload folder".  Select the uploaded file and in the action column select make it public using ACL.
step 9: copy the "Object URL" of the uploaded file. (http://ec2-54-90-62-209.compute-1.amazonaws.com/)

##### Install nginx in the EC2 instance 5

step 1: Connect the ec2 instance by using above steps
step 2: Now open the terminal and type the commands
step 3: install the nginx by using remote execution
step 4: Once all the steps are performed copy the Public IPv4 DNS and open it in the browser.
step 5: You can see the html webpage which shows the nginx is successfully installed on the given ec2 instance.


             



