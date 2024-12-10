---
title: "Security credentials"
weight: 2
---

# AWS security credentials

When you interact with AWS, you specify your AWS security credentials to verify who you are and whether you have permission to access the resources that you are requesting. AWS uses the security credentials to authenticate and authorize your requests.

There are different types of users in AWS, each with their own security credentials:

- **Account owner (root user)** — The user who created the AWS account and has full access.

- **AWS IAM Identity Center users** — Users managed in AWS IAM Identity Center.

- **Federated users** — Users from external identity providers who are granted temporary access to AWS through federation.

- **IAM users** — Individual users created within the AWS Identity and Access Management (IAM) service.

\
Users have either long-term or temporary (short-terms) security credentials:

- Root user, IAM user, and access keys have _long-term_ security credentials that do not expire. 

- IAM roles, users in AWS IAM Identity Center, and federated users have _short-term_ security credentials.Temporary security credentials expire after a defined period of time or when the user ends their session. 
    Temporary credentials work almost identically to long-term credentials, with the following differences:

    - Temporary security credentials can be configured to last for anywhere from a few minutes to several hours. After the credentials expire, AWS no longer recognizes them or allows any kind of access from API requests made with them.

    - Temporary security credentials are not stored with the user but are generated dynamically and provided to the user when requested. When (or even before) the temporary security credentials expire, the user can request new credentials, as long as the user requesting them still has permissions to do so.

    - For programatic access, temporary security credentials include an access key ID, a secret access key, and a security token that indicates when the credentials expire. After they expire, they're no longer valid.

\
As a result, temporary credentials have the following advantages over long-term credentials:

- You do not have to distribute or embed long-term AWS security credentials with an application.

- You can provide access to your AWS resources to users without having to define an AWS identity for them. Temporary credentials are the basis for roles and identity federation.

- The temporary security credentials have a limited lifetime, so you do not have to update them or explicitly revoke them when they're no longer needed. After temporary security credentials expire, they cannot be reused. You can specify how long the credentials are valid, up to a maximum limit.

# AWS Access Keys

For programatic access, security credentials include an access key ID and a secret access key. When you create a long-term access key, you create the access key ID (for example, `AKIAIOSFODNN7EXAMPLE`) and secret access key (for example, `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`) as a set. The secret access key is available for download only when you create it. If you don't download your secret access key or if you lose it, you must create a new one. Access key IDs beginning with `AKIA` are long-term access keys for an IAM user or an AWS account root user. Access key IDs beginning with `ASIA` are temporary credentials access keys that you create using AWS STS operations.