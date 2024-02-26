# VPC practice
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/f858e722-e371-4ebb-82f5-860de85722e9)
# Secutiry Groups 
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/6d796bc4-f9a3-4ec4-ad7b-cc81dfb92cbf)
In Default VPC the default security group for EC2s the inbound and outbound traffic is denied. We need to configure.

Network Access Control List (NACL):
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/6591e65c-b699-4e15-86d3-8176b54fdfd5)
We can use the Security Group and NACL combination but the NACL only have deny/allow options and SG has only allow option.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/c7cee7e3-991c-48b3-9f14-5eabd49bd61a)
Security is a shared responsibility.
# Creating VPC
1. AWS default create the Internet gate way,NACL default configuration,Route Table,Public and Private subnets.
2. We only required to create the EC2 instances.
   ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/b16ff885-7914-4b21-a760-f477f1a3288f)
