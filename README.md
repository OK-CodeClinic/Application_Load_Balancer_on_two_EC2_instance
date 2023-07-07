# Setting Up Application Load Balancer on two EC2 server.

## DESCRIPTION: 
This project covers how i launced an EC2 instance, launch another EC2 instance from the previous one created via AMI image and attaching a load balancer to both instance through target groups. Then, deploy a statics website on the instances.

## ARCHITECTURE:
![AWS-Acrchitecture (1)](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/eb6aca62-66a3-4963-8a60-d6abcfd6c5f4)



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
  
![AMI-Createdss](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/612a434c-5e34-406f-8084-5f3ef1d23062)

  
- Launched template from the AMI image created
  
![Template](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/30d7fab6-675b-4128-9d18-0c7ee1f23909)


- Launch an EC2 instance from the template created.
- Boom! 2nd EC2 instance launched, up and running.


#### Server outcomes
- Now, website from both EC2 instance are running perfectly on port 80.

![Both-Instances](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/aaa72323-690d-473d-be9f-dde0fbc17d11)


![Server1](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/36dd180e-e671-4f21-b743-a8fc8146a6f0)

![Server2](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/f4693faa-428a-4486-801f-e26a94840f29)


#### Target group
- To create a Load Balancer there is a need to create a target group.

![Reg_Targets](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/b66034e8-6ac6-48c9-a665-2f27f14cf232)

#### Load Balancer
- Add Tags
- Select scheme - In my case case, i slecet internet face.
- Mapping; in my case i selected all zones in my regions.
- Create a Load Balancer Security Group.

![ELB-SG-created](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/c44bb7ff-d5e3-42ed-9e96-3eb8646187d8)

- Add listener. ```Frontend - HTTP port 80``` ```Backend - HTTP```




###
- Websites will not be accessible using the DNS name of the Load balancer because the target group is not heathy.


![unheathy-TG](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/a4800fa9-72f4-4b3e-9fd4-ca265b967151)



- Why is the target5 group unhealthy????? The Security Group has stands firm as a firewall that it is against any unwanted traffic. In this case, there is a need to edit the inbound security group to allow the instances to be accessible via the security group of the load balanacer.

![Allow-ELB-in-SG](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/5bc6adf1-9c14-478c-93bb-c1556bf508aa)


###
###
###


## OUTCOME

- Healthy target group
  
![healthy](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/1e1e8b51-3b08-4636-a55f-3075fe15f8e8)


- Load Balancer working.

![ELB-working](https://github.com/OK-CodeClinic/Application_Load_Balancer_on_two_EC2_instance/assets/100064229/48721283-1a3d-4763-ac36-6161249b1b37)



## Author

- [Kehinde Omokungbe](https://www.github.com/OK-CodeClinic)
- Email: kehindefranklin@gmail.com

## Purpose
This is for leaning purpose only.
