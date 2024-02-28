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

# Basic Structure of YAML

```yaml
---
AWSTemplateFormatVersion: "version date"

Description:
  String

Metadata:
  template metadata

Parameters:
  set of parameters

Rules:
  set of rules

Mappings:
  set of mappings

Conditions:
  set of conditions

Transform:
  set of transforms

Resources:
  set of resources

Outputs:
  set of outputs

```


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

# Creating Stack

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/43ae0c71-b3fa-413c-aa93-535471bb546b)

Writting the template via UI

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/02601db1-3f52-4652-98fa-6e72e964097c)


![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/7c125e22-a67c-4c5e-a556-f6ebe21ed5e2)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/08c5155b-0d37-44e8-b663-aaf990c7a618)

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/fa6e1df6-4c38-4f9a-9192-91aacbd0cc37)

After deleting the S3 bucket
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/700dca43-2f98-4eef-b0d2-d2f42b389b3e)


To check the drift here Drift Status telling something went wrong as we deleted the s3 bucket via manual entry.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/855a4f8a-34a3-4404-aa78-d73afa02ac30)

Now in the template update the directive enabling the versioning

Follow the steps again uploading the template and submitting to Cloud Formation.Do the same manual task. Now we can easily see the drift detection
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/20b568ab-f24e-46d7-8241-cb4fbed2d701)

Drifted changes

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/a640eb41-92de-4cb9-9ca7-7518774c1e6a)


