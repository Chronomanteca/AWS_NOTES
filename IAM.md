
# Introduction

**IAM** stands for Identity and Access Management. It is a service built with the intent to control access to AWS resources as well as manage user and group access to the AWS environment. It is a #Global_Service meaning that it is available across the world so user permissions, groups, roles etc are not bound to a specific region.



---


 **IAM** is composed of the following elements:

- [[Users]]
- [[Groups]]
- [[Policies]]
- [[Account security]]
- [[Access keys]]
- [[Roles]]
- [[Security Tools]]
- [[Shared responsibility model|Shared responsibility model for IAM]]




---

# Hands-on


### Creating an access key


- Go to IAM
-  Select username
-  Security credentials
-  Create access key![[Pasted image 20261026203032.png]]
- For the purpose of this hands-on, CLI was selected
-  Click on Next
-  add a Tag (optional)
-  You are greeted with this screen:
   ![[Pasted image 20261026203307.png]]
- Back to the [[AWS CLI]] 
- Enter the following command:
    
	    aws configure
    
- Enter your access key, secret access key, default region, and output format if preferred
- Now you can use access your AWS services via CLI:
  
  ![[Pasted image 20261026204607.png]]
  



### Using roles

- Go to IAM
- Roles
- Create role
- ([[Exam Cheatsheet|Exam Question]])  Select AWS Service as the trusted entity type
- For the simulation, we will select EC2
  ![[Pasted image 20261026210650.png]]
- Add the permission you want to allow, in this case we select IAMReadOnlyAccess
  ![[Pasted image 20261026210828.png]]
- Select next and edit your trusted entities and verify permissions.
  ![[Pasted image 20261026211010.png]]
- You will see a trust policy Json added, this is stating that the role can be assumed (allow action sts:AssumeRole) on the service EC2 (ec2.amazonaws.com)
- All done, the role is created, it can later be used
  
### Security tools - Credentials report

- Go to IAM
- Access reports > Credential report
- Select Download
- This will download a CSV File with the credential information of your AWS account.

### Security tools - Access Advisor

- IAM
- Users
- Last accessed
- You will see the service access information for the selected user.
  ![[Pasted image 20261026212104.png]]

---

# Best Practices

- Use Root only for AWS account Setup. All else use the personal account
- 1 AWS user = 1 Physical user
- assign users to group > assign permission to gropus
- use strong password + MFA
- Create and use roles to give permissions to  AWS services
- Access keys are used for CLI / SDK
- Audit permissions using Credentials report and access advisor (last accessed)
- _NEVER share any account credentials to anybody (passwords, emails, ids, access keys...)_

---

# Summary

![[Pasted image 20261026212723.png]]

---

# Useful CLI commands



| Command                | Description                                  |
| ---------------------- | -------------------------------------------- |
| **aws iam list-users** | Lists a Json structure with user information |
| aws configure          |                                              |
