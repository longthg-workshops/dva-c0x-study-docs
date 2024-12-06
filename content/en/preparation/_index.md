---
title: "Prepare your environment"
weight: 1
---

You can't just learn about the cloud platform without creating an account and use the platform yourself, right ?

That's why we have a few steps to go through here.

> [!note] Note
>
> Some images contains older AWS UI due to being taken from others' videos or block. This is unwanted and inevitable due to my accounts having been set up and some processes can't be reversed.

# Prepare your AWS Account
## Create an AWS Account

> [!note] Note
>
> If you already have an AWS account, skip to [Sign in to your AWS root Account](#sign-in-to-your-aws-root-account).
>
> If you also have an IAM user already, skip to [Sign in to your IAM user](#sign-in-to-your-iam-user).

> [!info] Info
>
> You are required to have either a credit or a debit card with international payment support, issued by one of the following: Visa, Mastercard, American Express. Consider applying to have your card issued before creating an AWS Account.

Go to the [AWS Homepage](https://aws.amazon.com/).

Click on the **Create an AWS Account** button.

![AWS-Home](/images/preparation/01-0001.png)

At the **Sign up for AWS** screen, enter your information and click **Verify email address**.

![AWS-Signup](/images/preparation/01-0002.png)

Find the e-mail with the verification code.

![AWS-Vericode-Mail](/images/preparation/01-0004.png)

Enter the verification code.

![AWS-Verification](/images/preparation/01-0003.png)

At the **Contact information** page:

- Check **Personal - For your own projects**
- Enter your contact information

![Contact Information](/images/preparation/01-0005.png)

At **Billing information**, enter your card number and other informations on your card.

![Billing information](/images/preparation/01-0006.png)

For the final step, you're required to confirm your identity. Choose your confirmation method and enter your country code.

![confirm your identity](/images/preparation/01-0007.png)

![confirm your identity](/images/preparation/01-0008.png)

Choose a support plan. As a learner, I would just choose the free Basic plan. You can always change your support plan later.

![support plan](/images/preparation/01-0009.png)

Okay, at this point, the account creation process is done. Now you'll have to sign in to your account.

## Sign in to your AWS root Account

Enter [this link](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin) to sign in to your account.

Alternatively, you can sign in from the AWS home page.

![sign in](/images/preparation/01-1001.png)

On the sign in page, click the **Sign in using root user email** button.

![sign in](/images/preparation/01-1002.png)

Enter your e-mail address on the next page.

![root sign in](/images/preparation/01-1003.png)

Enter the captcha for human verification.

![root sign in captcha](/images/preparation/01-1004.png)

Enter the password, then sign in.

![password](/images/preparation/01-1005.png)

Now you're in, but we're not there yet.

![AWS Console](/images/preparation/01-1006.png)

## Secure your AWS Root Account with MFA

Enter the [Identity & Access Management (IAM) Console](console.aws.amazon.com/iam/home)

You'll be prompted to add MFA for your Root user. Click **Add MFA**

![IAM Console](/images/preparation/01-1007.png)

On the **Security Credentials** page, click **Assign MFA**

![IAM Console](/images/preparation/01-1008.png)

Proceed with the MFA Creation

![MFA](/images/preparation/01-1009.png)

> [!note] Note
>
> You can either use a browser extension, or an app on your phone for authentification.

After assigning MFA to your root account, the prompt at the main IAM console will look like this:

![IAM Dash](/images/preparation/01-1010.png)

## Create an IAM administrative user

Let's create a user with Administrator Access. I'll call it _"administraitor"_ (no typo, let's hope he'll never break bad and turn into a traitor).

![IAM Admin](/images/preparation/01-1011.png)

Proceed through all steps with the orange button (or whatever non-white button).

![IAM Admin](/images/preparation/01-1012.png)
![IAM Admin](/images/preparation/01-1013.png)

Oh yes, the group creation dialog. You can add the _**AdministratorAccess**_ policy for convinience, or create a policy yourself.

![IAM Admin](/images/preparation/01-1014.png)
![IAM Admin](/images/preparation/01-1015.png)

Now we're almost done. SAVE YOUR PASSWORD SOMEWHERE ! You're responsible for keeping it.

![IAM Admin](/images/preparation/01-1016.png)

Good ! Now your account is ready for the first cook !

## Sign in to your IAM user

The shortcut link is [here](https://signin.aws.amazon.com/console), for your convinience.

The process is much simpler now, enter what you need and click **Sign in**

![IAM Admin](/images/preparation/01-1017.png)

# Prepare your tools

To proceed with the hands-on labs in the course, it is recommended to have these tools:

- A computer with an operating system and network connection of course (heheh). But hey, for some reasons, Linux is prefered for these kinds of work.

- Any up-to-date browser

- An IDE or code editor. In my illustrations, I'll use Visual Studio Code with the AWS Toolkit installed.

- AWS CLI v2

# Hands-on source code

Get the source code [here](https://github.com/nealdct/aws-dva-code)

You can clone the repository using the Git command:

```bash
git clone https://github.com/nealdct/aws-dva-code.git
```

**Congratulations !** Now you're ready to cook your own knowledge.

![Mr. White](/images/homepage/waltercook.jpg)