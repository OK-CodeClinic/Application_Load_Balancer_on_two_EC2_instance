# Setting Up Application Load Balancer on two EC2 server.

## DESCRIPTION: 
In this project covers how i launced an EC2 instance, launch another EC2 instance from the previous one created via AMI image and attaching a load balancer to both instance through target groups. Then, deploy a statics website on the instances.


## STEPS:
#### 1st EC2 Instance: 
- Choosed an AMI
- Choosed an Instance Type
- Configured the Instance
- Added Storage (default)
- Added Tags
- Configure Security group
- Did all website provisioning to launch apache2 and run website on browser
- Review, then launched.

#### 2nd EC2 Instance:
- I created an AMI image from the 1st Instance
- Launched template from the AMI image created
- Launch an EC2 instance from the template created.
- Boom! 2nd EC2 instance launched, up and running.


#### Server outcomes
- Now, website from both EC2 instance are running perfectly on port 80.


#### Target group
- To create a Load Balancer there is a need to create a target group.

#### Load Balancer
- Add Tags
- Select scheme - In my case case, i slecet internet face.
- Mapping; in my case i selected all zones in my regions.
- Create a Load Balancer Security Group.
- Add listener. ```Frontend - HTTP port 80``` ```Backend - HTTP```


###
- Websites will not be accessible using the DNS name of the Load balancer because the target group is notb heathy.



- Why is the target5 group unhealthy????? The Security Group has stands firm as a firewall that it is against any unwanted traffic. In this case, there is a need to edit the inbound security group to allow the instances to be accessible via the security group of the load balanacer.




## OUTCOME

- Healthy target group

- Load Balancer working.



## Author

- [Kehinde Omokungbe](https://www.github.com/OK-CodeClinic)

## Purpose
This is for leaning purpose only.
