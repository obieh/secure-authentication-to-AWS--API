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
