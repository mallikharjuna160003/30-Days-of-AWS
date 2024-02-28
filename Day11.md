# AWS Cloud Formation Template (CFT)
>> https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html
# Cloud Formation:
- It is a cloud resouce automation template tool.
- We can write the templates in YAML/JSON format.
- It is declarative and versioned template tool.
- Alternative tools are Terraform,Cloud Development Tool Kit (CDK).
- For quick resource creation go with AWS CLI.
- For cloud independant automating resource creation go with Terraform.For AWS we can also use Cloud Formation Template.
  
>> Documentation: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html

Basic Overview

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/42bddbdb-b7bb-4409-8521-259ba53003de)

We need to give the script/template in the form of YAML/Json to the Cloud Formation Template it will process to create the resources.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/9f7ed6ac-e13e-4394-866b-ecfa6658f41b)

YAML has more readability. It is based on indentation.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/2e275cf8-afe8-4446-9eb9-7e459c61df26)

Using the cloud formation templates we can detect the drifting. It is where some CFT was written to automate the infrastrucure and manually someone has change the existing.If that CFT developed developer try to run the same template he/she can easily identify the changes using the drift detection.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/6ce3e7c0-6159-4c63-b236-de091fe072bc)

# Infra Creation using CFT via UI
- We can directly go to the UI of  CFT goto stack
- Create Stack
- import the yaml/json template written for automation
- submit to CFT

# Basic Structure and Components of CFT template
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/10f06911-74cd-46a7-92c0-27a77927bc15)

For example, if you created a stack with the following template, CloudFormation provisions an instance with an ami-0ff8a91507f77f867 AMI ID, t2.micro instance type, testkey key pair name, and an Amazon EBS volume.

```json
{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "A sample template",
    "Resources": {
        "MyEC2Instance": {
            "Type": "AWS::EC2::Instance",
            "Properties": {
                "ImageId": "ami-0ff8a91507f77f867",
                "InstanceType": "t2.micro",
                "KeyName": "testkey",
                "BlockDeviceMappings": [
                    {
                        "DeviceName": "/dev/sdm",
                        "Ebs": {
                            "VolumeType": "io1",
                            "Iops": 200,
                            "DeleteOnTermination": false,
                            "VolumeSize": 20
                        }
                    }
                ]
            }
        }
    }
}
```
Same in YAML

```yaml
AWSTemplateFormatVersion: 2010-09-09
Description: A sample template
Resources:
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      ImageId: ami-0ff8a91507f77f867
      InstanceType: t2.micro
      KeyName: testkey
      BlockDeviceMappings:
        - DeviceName: /dev/sdm
          Ebs:
            VolumeType: io1
            Iops: 200
            DeleteOnTermination: false
            VolumeSize: 20

```



