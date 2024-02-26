# Project
## About the project
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/69a2f565-20f2-4e7d-86de-6ee487510b51)

The VPC has public subnets and private subnets in two Availability Zones. Each public subnet contains a NAT gateway and a load balancer node. The servers run in the private subnets, are launched and terminated by using an Auto Scaling group, and receive traffic from the load balancer. The servers can connect to the internet by using the NAT gateway. The servers can connect to Amazon S3 by using a gateway VPC endpoint.

![vpc-example-private-subnets](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/4f7125d2-0bdc-4e55-a1f6-c0c014a3e196)

# Routing

When you create this VPC by using the Amazon VPC console, we create a route table for the public subnets with local routes and routes to the internet gateway. We also create a route table for the private subnets with local routes, and routes to the NAT gateway, egress-only internet gateway, and gateway VPC endpoint.

The following is an example of the route table for the public subnets, with routes for both IPv4 and IPv6. If you create IPv4-only subnets instead of dual stack subnets, your route table includes only the IPv4 routes.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/952a80b0-588e-4b0b-8a61-8d99fa922971)

The following is an example of a route table for one of the private subnets, with routes for both IPv4 and IPv6. If you created IPv4-only subnets, the route table includes only the IPv4 routes. The last route sends traffic destined for Amazon S3 to the gateway VPC endpoint.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/db158e38-f4da-481f-9813-a05903bac50b)

# Security

The following is an example of the rules that you might create for the security group that you associate with your servers. The security group must allow traffic from the load balancer over the listener port and protocol. It must also allow health check traffic.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/179621a0-2ab8-45cc-b608-3f379ac23633)

# To create the VPC
>> Note: If you use the IPs later kill all the resources the Elastic IPs are pay as use. Elastic IPs are totally free, as long as they are being used by an instance. However, Amazon will charge you $0.005/hr for each EIP that you reserve and do not use.

Follow the steps showing in the diagram

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/d74057b7-f8da-42a8-8728-8d7ab85287eb)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/5088f9af-a92a-4517-b79f-66a7d7336f9c)



![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/8a2a998f-285a-4dfb-a301-c758fb48d3e0)



![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/e97966de-542c-4f7d-8946-0f95ffbd2b36)


![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/d8b14231-4a57-4568-b970-becd517c27d9)


![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/26a5a003-b15d-4244-9aa7-c1ad824adea3)




## The following steps describe how to configure a basic launch template:

1. Specify the Amazon Machine Image (AMI) from which to launch the instances.
2. Choose an instance type that is compatible with the AMI that you specify.
3. Specify the key pair to use when connecting to instances, for example, using SSH.
4. Add one or more security groups to allow network access to the instances.
5. Specify whether to attach additional volumes to each instance.
6. Add custom tags (key-value pairs) to the instances and volumes. For now we are not using any volumes.
This is exactly similar to EC2 instance creation

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/b24ee954-12d0-487e-89ac-18ac6c85ed6b)
For the launch template creation few complex steps
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/02cc1f3f-fbed-4c87-848c-f22a909258e4)
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/e8bd550e-0b16-448b-aa3a-4c8ea2b2f7a5)

# To create the Auto Scaling Group diagramatically
- The instances should be created in the private subnet.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/a75cfe22-7ef4-4e32-bf29-80b9886b0ff8)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/40275028-ca89-4a10-97d3-da85550b3147)
Not attaching any load balancer now. We will create in the Public subnet.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/c4393bbe-de4d-418c-885b-b6cec4dbf9ba)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/6d016135-4a74-44eb-9edb-75679b9cea85)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/8ffe6047-4efe-44c7-9c36-6b704205c678)

Finally!!... Goto the EC2 instances we are able to see the 2 instances running. in us-east-1b
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/cd62ca9b-2708-49a9-b2d2-3fe88c5db31f)

# Before setting up the Public subnet lets deploy the application in private subnet via bastion host.
1. Create an Ec2 instance name it as bastion host <bold>t2-micro, key-pair,Security group (ssh),Network settings select the same VPC,select the public subnet,Auto Assign Public IP address</bold> Launch the instance.
2. ssh to the bastion host.Below image to send the .pem file to basition host from local host with .pem file access in local terminal.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/133e3bd8-4fb2-4f00-9e9b-a49bb86e5899)


