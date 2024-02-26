
# EC2
Elastic Cloud compute it can increase or decrease the resources storage,cpu,ram etc.

Types of EC2 instances:
1. General Purpose EC2
2. Memory Optimized - high runtime memory required tasks
3. Storage Optimized - Extenal storage required tasks
4. Compute Optimzed - high performance tasks
5. Accelerated Computed optimized instances
etc,..
# Create EC2 instances
We can create EC2 instances using the CLI and UI interface.
1. Select the region and availability zone where the EC2 needs to be create.
2. Regions - India, Asia, US, Australia
   ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/12d19d86-9131-41b7-92ee-af2e45678c64)
3. Zones: In each region there were multiple availability zones whre multiple data centers located.
   for example US there we east,west zones(see the above image).
4. Regions and Zones will be selected where the application need the more reachability.This way we can reduce the latency.
   If the the application went down in one zone then we can try to use AWS remaining availability zones based on the requirement and application UP time.
5. Search EC2 in the search bar and select EC2.
   ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/1b71979f-0e09-46f0-8492-94f752c5b701)
6. EC2 Dashboard 
   ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/0d191368-af33-47df-89fe-37123f5dcc24)
7. Click on Instances and try launch instances.Now select the OS Amazon Linux, Ubuntu, Windows, Solaris etc.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/a6ddaee1-48f8-4988-a9a8-7607f100af80)
8. Select the version of the OS which we called it as AMI and 64bit and instance types t2 micro, t2 large etc.
   ![Screenshot from 2024-02-26 19-58-38](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/cd4d6005-7f7d-4f22-aca8-deb1c5062f69)
10. Create the Key-Pair for accessing the instance. It is combination of Public private key.We share only the Public key not private key for securities purpose.
    ![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/b66acb59-c64f-42fd-8128-d40ba2a09d1b)

11.Keep the Network settings as default for now
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/0dbfd649-5b9e-4c30-b68f-4a24c7459fbb)
12 Configure the storage as per required.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/09b53a10-6573-4a59-bba5-d567c5936b8c)
Finally instance got created.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/e4dcc181-960a-4165-8551-19743797cca7)


