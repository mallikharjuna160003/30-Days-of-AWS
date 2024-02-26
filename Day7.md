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
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/d74057b7-f8da-42a8-8728-8d7ab85287eb)





