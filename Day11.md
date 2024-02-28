# AWS Cloud Formation Template (CFT)
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
  
