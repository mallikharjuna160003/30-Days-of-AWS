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
3. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/16a66cca-b60d-4529-9ca1-aaf5402572e7)
4. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/fcc6b1fb-4f1a-4660-a55a-021f07066a46)
5. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/28e7711d-888f-4f67-91a6-cd04218be4c4)
6. We have to configure the Network configuration, Availability zones,subnets,Security etc.
7. After Creating the VPC
   
9. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/75b8f8d0-a43e-4383-99c6-12c327e3151a)
   
10. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/e8012451-fcc4-4d60-a1aa-2e332554b328)

11. ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/3bca9cf6-8427-4ffe-a5d0-931dc79107ce)



