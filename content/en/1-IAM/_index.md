---
weight: 2
title: "Chapter 1: AWS Identity and Access Management"
---

Unless you somehow skip chapter 0 (or at least, a certain part of it), [where you should take a look and follow the instructions]((../0-preparation/#create-an-iam-administrative-user)), you should've heard of the term **_"IAM"_** or **_"IAM account"_**. **IAM** is the short form of **Identity and Access Management** an AWS service which provides the capability of **Authentication** and **Authorisation** (about the spelling, I'm not British, just want to _eff_ around). This chapter provides you with a basic view on certain aspects of the IAM service.

# AWS root account

When you first create an Amazon Web Services (AWS) account, you begin with a single sign-in identity that has complete access to all AWS services and resources in the account. This identity is called the AWS account root user and is accessed by signing in with the email address and password that you used to create the account.

## List of some root-account-specific tasks

The root account allows for several high-privileged tasks that even an IAM account with the highest administrative permissions is not allowed to perform. Here are some of these tasks:

### Account Management Tasks

- Change your account settings (account name, email address, root user password, and root user access keys)
- Restore IAM user permissions (in case of accidental self permission revoking of an IAM user, usually an administrative one)
- Close your AWS account

### Billing Tasks

- Activate IAM access to the **Billing and Cost Management** console
- Certain tasks and invoices might require a root account, even with **IAM access to Billing and Cost Management** enabled.

### AWS GovCloud (US) Tasks

- Sign up for AWS GovCloud (US).
- Request AWS GovCloud (US) account root user access keys from AWS Support.

### Amazon EC2 Task

- Register as a seller in the Reserved Instance Marketplace.

### AWS KMS Task

- In the event that an AWS Key Management Service key becomes unmanageable, an administrator can recover it by contacting AWS Support; however, AWS Support responds to your root user's primary phone number for authorization by confirming the ticket OTP.

### Amazon Mechanical Turk Task

- Link Your AWS account to your MTurk Requester account.

### Amazon Simple Storage Service (S3) Tasks

- Configure an Amazon S3 bucket to enable MFA (multi-factor authentication).

- Edit or delete an Amazon S3 bucket policy that denies all principals.

    You can use privileged actions to unlock an Amazon S3 bucket with a misconfigured bucket policy. 

### Amazon Simple Queue Service Task
- Edit or delete an Amazon SQS resource-based policy that denies all principals.

    You can use privileged actions to unlock an Amazon SQS queue with a misconfigured resource-based policy

## Why not using the root account ?
As the root account can perform specific tasks that can completely change your account, or see and modify the other access priviledges and vital information beyond the normal use. It is required that the root account is locked and secured somewhere out of normal reach. Instead, an administrative IAM user still allows you to access most resources and create other identities with different limited permissions as for your purposes.

After all, you wouldn't want to have your "God Mode" exposed to either see yourself screw up with too much power at the wrong time, or this...

![This place is hijacked](/images/1-IAM/0001.jpg)

# Identity and Access Management (IAM)

AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can manage permissions that control which AWS resources users can access. You use IAM to control who is authenticated (signed in) and authorised (has permissions) to use resources. IAM provides the infrastructure necessary to control authentication and authorisation for your AWS accounts.

## Authentication and Authorisation

To be short:

- To authenticate someone means to allow or deny them from entering based on their identity.

- To authorise someone means to allow or deny them from doing tasked based on their permission. This happens after the authentication is completed and the identity is allowed.

## How does IAM work ?

When a user/application tries to sign-in using the credentials, IAM matches the sign-in credentials to a principal (an IAM user, federated user, IAM role, or application) trusted by the AWS account and authenticates permission to access AWS. During the logged-in session, IAM makes a request to grant the principal access to resources when. IAM verifies that your identity is on the list of authorized principals, determines the policies control the level of access to be granted, and evaluates any other policies that might be in effect. Principals within your AWS account or from another AWS account that you trust can make authorisation requests.

The following paragraph illustrates the authentication and authorisation process with AWS IAM:

![IAM Process](/images/1-IAM/0002.png)

When a principal tries to use the AWS Management Console, the AWS API, or the AWS CLI, that principal sends a request to AWS. The request includes the following information:

- **Actions or operations** – The actions or operations that the principal wants to perform, such as an action in the AWS Management Console, or an operation in the AWS CLI or AWS API.

- **Resources** – The AWS resource object upon which the principal requests to perform an action or operation.

- **Principal** – The person or application that used an entity (user or role) to send the request. Information about the principal includes the permission policies.

- **Environment data** – Information about the IP address, user agent, SSL enabled status, and the timestamp.

- **Resource data** – Data related to the resource requested, such as a DynamoDB table name or a tag on an Amazon EC2 instance.

AWS gathers the request information into a request context, which IAM evaluates to authorize the request.

# Detailed look

 - Components of IAM

 - Security credentials

 - Best practices

 - Identity providers and federation

# Further reading

- https://docs.aws.amazon.com/IAM/latest/UserGuide/
- https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html
