# VPC
1. VPC is a virtual private cloud provides security to the EC2 instances and groups the instances.
2. VPC size is defined based on the range of IPs allocated to VPC.Each IP can assigned to one EC2 instance.
3. In a vpc based on the projects like Payments,catalogs etc these IPs divides into multiple subnets.
4. Each VPC has this Internet gateway.The request route through this using the public subnet to Load Balancer(assigned with Public subnet) and to the router using route table the target application can be accessible.But here we have the security group check present.It will check the target group has the inboud rules etc.
5. Within a subnet the security group can used by multiple private subnets. So, we have the NACL ( Network Access Control List) service to provide the security (same) to all the EC2 instances(in private subnet).
6. There is another service NAT gateway it will mask the target instances IP address outside the VPC.NAT will mask the EC2 instance IP address with internetgateway IP or router IP address. NAT gateway created in Public Subnet. It is for security purpose not to expose the target(application host IP visible to Internet.

   ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/40f6dde5-5283-4555-8056-f2414eef7014)

