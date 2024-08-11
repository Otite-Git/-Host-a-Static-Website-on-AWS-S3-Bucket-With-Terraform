# 💻Host a Static Website on AWS S3 Bucket with Terraform☁️

Hi! Welcome to my repository containing my AWS Project I've have undertaken as a Cloud Engineer and Cloud architect enthusiast⚡️:

In this repository you will see a description of the project, low and high level architecture, scripting files and information on other key assets that I have used to develop this project as part of my portfolio and progressive development.

## **Website Page**


## **Project Overview** 

This project demonstrates how to host a Static Website on AWS, utilising AWS services for a scalable, simple, storage soluton and highly available architecture. The key components include the usage of S3 Bucket, HTML Scripting, IAM User Management, Terraform scripting and Bash Scripting and many more. The setup ensures cost effectiveness as hosting the website is cheap due to the non-existence of any other components. simplicity as it holds fixed content, where each page is coded in HTML and displays the same information to every visitor. Lastly, Terraform supports a number of cloud providers including AWS so it can be packaged and reuse the code in form of modules

![Low Level Architectural Diagram](https://github.com/user-attachments/assets/f0eb3f39-5be1-4e78-9e27-c0fc83eb2cdd)



- - - 
## **Architecture**

1. **S3 Bucket:** Enables environmental file storage.
2. **Application Load Balancer:** Distributes web traffic across an Auto Scaling Group of EC2 instances in two availability zones for high availability and fault tolerance.
3. **Route 53:** Used for domain name registration and DNS record management.
4. **GitHub:** Used for version control and collaboration, storing web files.
5. **IAM Roles:** Used to allow for the secret access key and access key ID to authenticate with AWS in order to push the container image to ECR.


## **Deployment Steps**

### Visual Studio Code Setup
1.Go to the Visual Studio Code website and install Visual Studio Code: Depending on what type of OS is being used, Visual Studio Code can be installed downloading the binary files for Windows or macOS.

### Terraform Setup
1. Go to the Terraform website and install Terraform: Depending on what type of OS is being used, Terraform can be installed downloading the binary files for Windows or macOS

### Folder and File Creation
1. Create a folder in you computer directory called s3_static_website. Note that this folder will be the host directory when using Terminal or command line
2. Created a file called main.tf in Visual Studio Code and save it in the host directory file created above

### Terraform File Configuration
1. Set up the main.tf Terraform file inputting the relevant information such as bucket name. For the purpose of this project a main.tf file template has been created and inlcuded in this repository.
2. Within the main.tf Template file included in this repository, ensure to replace the bucket name defined in the file so it’s completely unique for you

### Terminal Navigation
1. Use your terminal to navigate to s3_static_website
2. Run this in terminal:
```bash
terraform init
terraform apply
```
The output should look like this below:
<img width="1138" alt="terraform init" src="https://github.com/user-attachments/assets/d9a53d7d-afd9-4712-a914-0395f48c1407">  <img width="1025" alt="terraform apply" src="https://github.com/user-attachments/assets/15e193e8-a934-4b8c-81b4-325128a440d1">

### S3 Bucket configuration
1. Once you have successfully completed the terminal navigation steps above
2. Log into your AWS account and head to the Bucket section with S3. Your Bucket should have been created and look like this below:
![Inside the created S3 bucket](https://github.com/user-attachments/assets/b8b4c4df-9834-4c0c-a9d4-759a21e0e818)


### Upload website content to your bucket
1. Upload the files (index.html and NextWork - Everyone...love_files.zip) files into your bucket (right click on each link, and select Save link as..) These files can be located in this repository.
2. Unzip the zip file you've downloaded.
Return to the Amazon S3 console with your bucket page open. Choose the Object tab.
- Choose Upload
- Choose Add files
- Choose index.html
- Choose add folder
- Choose the unzipped folder - NOT the zip file itself!
You might get a popup that tells you that all files in that folder will be uploaded.
- Choose Upload
- S3 will then get to work

## **How to Use**

1. Clone this repository to your local machine.
2. Follow the AWS documentation to create the required resources (S3 Bucket IAM Management) as outlined in the architecture overview.
3. Use the provided scripts to set up the reosurce and applications.
4. Configure the reosurces assets as per the architecture.
5. Access the Website website through the endpoint URL for your bucket.

## **Additional Resources**

- **AWS Documentation:** Refer to the [AWS documentation](https://aws.amazon.com/documentation/) for detailed guides on setting up S3 Bucket, IAM roles and other services such as VPC, EC2, Auto Scaling, and Load Balancer.
- **GitHub Repository Files:** Refer to [Otite-Git/-Host-a-Static-Website-on-AWS-S3-Bucket-With-Terraform](https://github.com/Otite-Git/Host-a-Static-Website-on-AWS-S3-Bucket-With-Terraform.git) to access the repository files for scripts, architectural diagrams, and configuration files necessary for deploying the website.

## **Contributing**

Contributions to this project are welcome! Please fork the repository and submit a pull request with your enhancements.

## **License**

This project is licensed under the MIT License - see the LICENSE file for details.

## **What problems did I solve by completing this project?**

1. **Scalability:** I was able to effectively Handle varying levels of web traffic efficiently through using AWS services like Auto Scaling and Elastic Load Balancing to automatically adjust the number of running instances based on traffic demand.
 
2. **Performance Optimisation:** I solved the problem of slow loading times and handling varying levels of web traffic effciently using AWS services like Auto Scaling and Elastic Load Balancing to automatically adjust the number of running instances based on traffic demand.

3. **Database Management:** Using AWS to host WordPress enabled me to effectively manage and optimise the database that supports WordPress through using Amazon RDS for managed MySQL a databases, enabling read replicas for load distribution.

4. **High Availability:** I Minimised downtime and ensuring continuous availability by deploying applications across 2 Availability Zones AZ1 & AZ2, using Elastic Load Balancing to distribute traffic, and setting up failover configurations.

5. **Cost Management:** I solved the problem of having high costs by supporting the deployment of a cost effective solution managing and optimising the costs associated with AWS resources. This was achieved through monitoring usage with AWS Cost Explorer, using AWS Budgets to set alerts, and leveraging Reserved Instances and Savings Plans for cost savings.

## **What issues did I face while working on the project and how did I resolve that issue?**
  
- **WordPress credentials issues:** I had faced the issue of my WordPress credentials automatically registering through an auto-fill feature generating a strong passsword which I did not record. I solved this issue by firstly deleting the existing EFS RDS and EC2 Instance and creating new EFS RDS and EC2 Instances. Once created, I then SSH'ed into the instance via Amazon Linux where I was to re-nstall the WordPress script which consisted of setting up the WordPress application on an EC2 instance, including Apache, PHP, MySQL, and mounting the Amazon EFS.

- **Increasing Costs:** The challenge of increasing cost also became a concern which I was able to resolve thorugh by firstly enabalbing MFA (Multi Factor Authentication) to enhance the security access of my root user account and enable best practice. Through this, I reduced the risk of fraudulent access to my account and using it resulting in high usage cost. Furthermore, I used AWS budgets and Cost Explorer to effectively manage costs by settting alerting and identifying which service was a high usage cost through visibility of the cost usage graph.  

 ## **What overall lessons did I learn?**
 
- **AWS Linux and Bash:** This project gave me the ability to increase my skills in AWS Linux and bash as I was required to use the EC2 Instance to install the WordPress script

- **Networking:** I further my knowledge on Networking through inplementation of tools such as the Internet Gateway. This enabled the resources within the VPC Public Subnet to connect to the internet, and resources within the VPC Private Subnet to connect to the internet via the NAT Gateway. The use of the NAT Gateway enables resources like the EC2 Instances on the Private App Subnet to access the internet and download package updates using 'Sudo Yum update' through SSH'ing into the EC2 instance. So there is a requirement for the EC2 Instance to have access to the internet without external users on the internet gaining access to the EC2 Instance.

- **IAM Management and Best Practice:** As part ot IAM Management best practice, I identified that it is not recommended to user a root account for cloud environment creation. Going forward, I increased the acess robustness of my root using account by regularly changing  passwords, using MFA (Mult Factor Authentication), removing access keys to the root account and reducing overall root user account user for sercurity perposes.

-  **IAM User Creation and Best Practice:** Through doing this project, I also identified that going forward, best practice would be to create a new IAM user for myself and only grant required access also setting up a MFA for the new user making this the primary use account going forward. This is not only best practice, but permits the use of defining a boundary of services that I only want to use. For example, am IAM user cannot be charged for a NAT Gateway, if they don't have permissions to configure one in the first place. 
  





