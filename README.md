# SECURE AUTHENTICATION TO AWS API.
## This project will demonstarte how to setup secure authentication in AWS.


### Create IAM Role.

1. On your AWS IAM dashboard select 'Roles'(left side bar)

![](./img/Pasted%20image%20(7).png)

2. Click 'Create role' on the following window(top right)

![](./img/Pasted%20image%20(8).png)

3. Select 'AWS service', EC2 use case.

![](./img/Pasted%20image%20(9).png)

4. Scroll down and click 'next'

![](./img/Pasted%20image%20(10).png)

5. Type 'ec2' on the permission search bar and select 'AmazonEC2FullAccess'

![](./img/Pasted%20image%20(11).png)

6. Search for s3 and select 'AmazonS3FullAccess', scroll down and click 'Next'

![](./img/Pasted%20image%20(13).png)

7. Add a name and description for the role.

![](./img/Pasted%20image%20(14).png)

8. Review permisions and click 'Create role'

![](./img/Pasted%20image%20(15).png)

9. You should a confirmation page indicating success.

![](./img/Pasted%20image%20(16).png)


### Create IAM Policy.

1. On your IAM dashboard click 'Policies'.

![](./img/Pasted%20image%20(18).png)

2. Towards the top right of the policies window, click 'Create policy'

![](./img/Pasted%20image%20(19).png)

3. Select 'EC2'on the 'select a service' option;

![](./img/Pasted%20image%20(20).png)

4. Scroll down to add services and select 'S3'

![](./img/Pasted%20image%20(21).png)

5. Scroll down and click 'Next'

![](./img/Pasted%20image%20(22).png)

6. Add a name and description to the policy.

![alt text](./img/Pasted%20image%20(23).png)

7. Scroll down and click 'Create policy'

![](./img/Pasted%20image%20(24).png)

8. You should a success page confirming policy creation.

![](./img/Pasted%20image%20(25).png)




### Create an IAM User.

1. On you AWS account click IAM or search IAM form the search bar and click.

![](./img/Pasted%20image%20(3).png)

2. On the left side bar click 'Users'

![](./img/Pasted%20image%20(4).png)

3. On the following window screen click 'Create user'(Top right).

![](./img/Pasted%20image%20(5).png)

4. Add a name for the user,check 'Provide user access to the AWS Management Console', Choose creation format and click 'Next'

![](./img/Pasted%20image%20(26).png)

5. On 'Permisions' click 'Attach policies directly'. Select the 'API-demo-policy' you created previously, then click 'Next'.

![](./img/Pasted%20image%20(27).png)


6. Review to check if all desired settings are correct, then click 'Create user'


![](./img/Pasted%20image%20(28).png)

7. You should see a success page, implying user have been successfully. Download the user credentials.

![](./img/Pasted%20image%20(29).png)


### Attach user to IAM Role

1. Select users on the IAM dashboard, then click on the user you created earlier.

![](./img/Pasted%20image%20(30).png)

2. As seen, the role is already added to the user directly. Click 'Add permission'.

![](./img/Pasted%20image%20(31).png)

3. Select json for the policy editor. On the statement object, change the value of the 'Actions' key to 'sts:AssumeRole', and value of resource to the arn of the role you created. Click Next to finish.

![](./img/Pasted%20image%20(36).png)

### Link the role to Policy

1. Go to 'Roles', click on the role you created.

![](./img/Pasted%20image%20(37).png)

2. Check the two AWS managed permission,(ec2 and s3) and click add permissions.

![](./img/Pasted%20image%20(38).png)

3. Search the policy name or filter by type "Customer managed". Select the policy and click 'Add permission'

![](./img/Pasted%20image%20(39).png)

4. A success page pops up indicating success in role policy link.

![](./img/Pasted%20image%20(40).png)

5. Verify by clicking on the role to see permissions.

![](./img/Pasted%20image%20(41).png)

### Downloading and Installing AWS CLI(Linux).

1. Download awscli. Run `curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
`
2. Run `unzip awslive2.zip` to unzip the file.

3. Run the installer, `sudo ./aws/install`

### Configure AWS CLI.

1. get hold of the IAM user details you created earlier.

2. On your terminal run `aws configure` to beigin aws cli configuration.

![](./img/Pasted%20image%20(42).png)

3. Enter IAM user AWS access key.

![](./img/Pasted%20image%20(43).png)

4. Enter IAM user AWS Secret Access key.

![](./img/Pasted%20image%20(44).png)

5. Specify Default AWS region

![](./img/Pasted%20image%20(45).png)

6. Type json as output format.

![](./img/Pasted%20image%20(46).png)

### Now your configuration is done.

![](./img/Pasted%20image%20(47).png)

7. To test aws cli configuration run `aws sts get-caller-idenditity`. The out put should match the details of the IAM user you created earlier.

![](./img/Pasted%20image%20(49).png)

8. To further test the configuration, run `aws ec2 describe-regions --output table`

![](./img/Pasted%20image%20(48).png)


## Summary

*  AWS CLI:
The AWS Command Line Interface (CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts. The AWS CLI provides direct access to the public APIs of AWS services. You can use the AWS CLI to perform all the same tasks that you can do with the AWS Management Console, but in a programmatic way.
 
* AWS APIs:
AWS APIs are the application programming interfaces provided by AWS for its services. These APIs are HTTP endpoints that allow you to programmatically interact with AWS services. Each AWS service has its own API, and these APIs are what the AWS Management Console, AWS CLI, and AWS SDKs use under the hood to perform operations. The most common type of AWS API is the REST API, which uses HTTP methods (like GET, POST, PUT, DELETE) and JSON or XML for data exchange.

* Authenticating to AWS API from terminal:
When using the terminal to interact with AWS (either via the AWS CLI or by making direct HTTP requests to the AWS APIs), you need to authenticate your requests. AWS requires that every request to its API is signed with AWS credentials. These credentials are used to verify your identity and permissions. The primary way to authenticate from the terminal is by using the AWS CLI, which handles the signing process for you. You first need to configure the AWS CLI with your credentials. These credentials can be:
  
  - An IAM user's access key ID and secret access key.
  - Temporary security tokens (like those from assuming an IAM role) that include an access key ID, secret access key, and a session token