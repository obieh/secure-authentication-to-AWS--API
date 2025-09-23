# SECURE AUTHENTICATION TO AWS API.
## This project will demonstarte how to setup secure authentication in AWS.

### Create IAM Policy.



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

### Create an IAM User.

1. On you AWS account click IAM or search IAM form the search bar and click.

![](./img/Pasted%20image%20(3).png)

2. On the left side bar click 'Users'

![](./img/Pasted%20image%20(4).png)

3. On the following window screen click 'Create user'(Top right).

![](./img/Pasted%20image%20(5).png)

4. Add a name for the user and click 'Next'

![](./img/Pasted%20image%20(6).png)