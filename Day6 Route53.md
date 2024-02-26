# Route53
# Why we need Route53?
- Route53 is used for DNS(Domain Name System) as a service in AWS.
- EC2-> compute as a service, EKS -> Elastic Kubernetes as a Service similiarly DNS purpose we use Route53.
- Example amazon.com or flipkart.com domain name is mapped to some ip address for simplifying the access to applications.
- For this domain name conversion to IP address we need a service called Route53 in AWS.The IP address keeps changing and we cant remember many times it keeps updating.So we make it simple by mapping the IP to domain name.
  ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/50499b2d-381d-4abd-b10b-e0fb5468c7b2)

1, 2, 3 are different applications
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/50961e1d-fa6f-45be-b936-9eafe23d4eb0)
In general we buy the domain names from godaddy, hostinger.Instead of that AWS is providing itself as DNS service Route53.<br>
The records table will keep the domain name and ip mappings.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/1863e85e-ae61-401e-90e8-aa874e810a9f)

In general the request process by comming to Route53 then to Load Balancer then to applications
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/f6c87e5d-6606-482c-bd4d-b5855721f499)

Even you buy the domain name by third party or in Route53 there need to register in  hosted zones of DNS records.
It is pay as a service for domain names.There will be routing policies included need to configure so many things.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/6a7bf872-92fe-4707-818d-f894421094bd)

Route53 supports
1. Domain Registration
2. Hosted Zones
3. Health Checks -> for the server is health check to route the traffic to the Load Balancer.



