# AWS CLI
1. Used for infrastructure automation <br>
   Example create 100 buckets,Ec2 instances,50 VPCs etc.
2. Through AWS APIs we can automate via Python boto3, Terraform, Cloud Formation Templates,Cloud Development Tool Kit (CDK)--> Iaac
3. Refer the AWS CLI documentation.
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/5c0513b7-3bd2-47bd-917a-64a356f90ca3)


The following aws configure command example demonstrates user input, replaceable text, and output:

 1. Enter aws configure at the command line, and then press Enter.
 2. The AWS CLI outputs lines of text, prompting you to enter additional information.
 3. Enter each of your access keys in turn, and then press Enter.
 4. Then, enter an AWS Region name in the format shown, press Enter, and then press Enter a final time to skip the output format setting.
 5. The final Enter command is shown as replaceable text because there is no user input for that line.

```sh
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: ENTER
```
# To create Security Group in AWS
```sh
aws ec2 create-security-group --group-name my-sg --description "My security group"
```
