# Resume

I have created this project to demonstarte the use cases of AWS CloudFormation and other features.

Project Agenda - 
1. Create an EC2 instance of your choice, Install Apache/Nginix of your choice using the USERDATA.
2. The EC2 will be created in new S3 Bucket,VPC,Public Route Table, Internet Gateway and a Public Subnet with its association.
3. Basic layout of the website is written in index.html and styling is done via the style.css file. (Extremly Basic since i'm not a developer.)
4. Once you launch the static website you can click on the view resume to view the file.

Steps -
1. Create a new Cloudformation Stack by uploading the cloudformation.yml file.
2. Give the name to the stack and mention the key pair name.
3. Once the cloudformation stack is created cross verify the below resources:-
     a. VPC
     b. S3 Bucket
     c. EC2 Instance
     d. InternetGateway
     e. Public Subnet
4. Login to the EC2 instance and verify if the apache server is correctly installed and its up and running.
5. Configure the AWS CLI(I have not included this step in USERDATA since it requires to add the access key ID and secret key ID)
6. Go to your S3 Bucket and upload the files index.html style.css and resume.pdf to S3 directly via the upload button.
7. Now there are two ways to launch the static website. One is via the S3 URL or the other way is to use the public IP of the EC2 instance.
8. S3 URL will as below format
      http://<bucket-name>.s3-website-<region>.amazonaws.com
9. If you want to access the static website via the Public IP of the EC2 instance you will need to sync the S3 bucket objects to your EC2 instance (in this case to /var/www/html/). To do that use the following command on your EC2 instance
       sudo aws s3 sync s3://<Buce=ket-Name> /var/www/html/
10. You are all set now ! Enjoy :) :D



NOTE - THIS IS AN ONGOING PROJECT. AS THE NEXTPHASE TO THIS PROJECT I WILL TRY TO INTEGRATE JENKINS AND CREATE A CI/CD PIPEPINE TO AUTOMATE THE UPDATION OF THE FILES FROM GITHUB
