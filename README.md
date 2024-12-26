# Create-Billing-Budget-and-Alarm-On-AWS-
"Tracking Cloud Money"

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/6781aa8b78dc0f379030ea30823c7e478bb2162f/Images/aws%20budget.png)

# Intro

Your journey to becoming a Cloud Engineer most likely would involve experimenting with projects on major public cloud providers like Amazon Web Services (AWS). Fortunately, AWS provides Free Tier Usage for certain resources, however at times, it can be cumbersome to manually track all spending from deployed resources in your account. This may result in the incurring of unintended costs because of forgotten resources left running.

Today, I will show you how we can track your running spendings in your AWS account and be alerted via email once your cost reaches over a desired threshold amount. We will be using two effective services, AWS Budgets and Amazon CloudWatch, which will enable us to set up billing budgets and billing alarms.

# Background

# AWS Budgets

AWS Budgets is a feature in your AWS Account dashboard that is used to set custom billing budgets to track costs based on usage in your account. It can be configured to send alerts to your email using SNS notifications if the thresholds are exceeded so you can quickly respond.

# Amazon CloudWatch

Amazon CloudWatch enables you to monitor applications, infrastructure, network and services and use alarms, logs and events data to take automated actions.

# Amazon SNS

Amazon SNS makes it easy to set up, operate and send notifications from AWS. It provides message delivery from publishers to subscribers.

# Prerequisites

AWS root account

IAM user with administrator privileges

# Use Case

You are a Cloud SysOps Administrator working for UP THE CHELS TECH. Your manager has informed you of a $5.00 AWS resource monthly spending limit she wants to place on your team’s account. She has tasked you to monitor the spending by tracking costs and has required that she be notified when it reaches a certain threshold before and when the spending limit is hit. You decided to use AWS Budgets, Amazon CloudWatch and Amazon SNS to accomplish this task.

# Pre-Steps

# Enable billing access for IAM users and update billing preferences

Log into your AWS root account, click the root account name on the top right of the Management Console, then click “Account”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/4db33f47fac54562ff7c083db271868283587324/Images/Screenshot%202024-12-24%20120213.png)


Scroll down to “IAM User and Role Access to Billing Information”, then click “Edit” on the right side. Select “Activate IAM Access”, then click “Update”.


![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/b4d64bc5279b5b8e3f3944511d59f134e6b0f032/Images/Screenshot%202024-12-24%20120326.png) 

Now let’s proceed to update our billing preferences.

Scroll up and click “Billing preferences” on the left pane.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/04bc426fc7cd4cc33bd2ae4046c53e25ebfc5cef/Images/Screenshot%202024-12-26%20114033.png) 


Select all the boxes, then type the email you wish to receive alerts when usage is approaching or has exceeded the AWS Free Tier Usage limits.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/70bb6e57f5962a0af69c33eb1ab06698c5871afe/Images/Screenshot%202024-12-26%20114149.png)

Now that we’ve enabled billing access for IAM users and updated billing preferences, we can proceed to actually creating the billing budgets and billing alarms.


# Create Billing Budgets with AWS Budgets

Sign into you IAM account, click the IAM account name on the top right of the Management Console, then click “Account”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/866551cfe9d74af8445c4401914ef677afa21e64/Images/Screenshot%202024-12-24%20120213.png)

Navigate to the left pane, click “Budgets”, then click “Create budget”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/c225df46ce187949fcf6d21b72814fb20698d57d/Images/Screenshot%202024-12-24%20120804.png)


For “Budget setup”, we will use a simplified template and select “Monthly cost budget”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/d5aacaa87cacff0a72a0d19392dde14707e04480/Images/Screenshot%202024-12-24%20121011.png)


Give the Budget a name, enter the budget amount, then type in the email address of the recipients to be notified when the threshold is exceeded.

As seen below, the recipients would be notified when spending has reached 85% and also when it reaches 100% or the forecasted spend is expected to reach 100%.

Proceed by clicking “Create budget”.


![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/ebdc4b4a19e9e87fa23fc3ddc96270df10f30e29/Images/Screenshot%202024-12-24%20121019.png)


# Success!
You should now be able to see your newly created billing budget in the Budgets Overview.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/c8b3987a79868b2bbbaee7faa719fc6f62750218/Images/Screenshot%202024-12-24%20121042.png)


# Create Billing Alarm with Amazon CloudWatch

Navigate to Amazon CloudWatch service in the Management Console, click “Billing” on the left pane, then click “Create alarm”.


![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/2ecf03bade1e74d6e8b6516319cead92255b396d/Images/Screenshot%202024-12-26%20120043.png)


Click “Select metric”, then click “Billing”. Click “Total Estimated Charge”, select “USD”, then click “Select metric”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/b8c4dab9066095c95f5cc9bd9c5a08bc183905d0/Images/Screenshot%202024-12-24%20121452.png)


Leave the “Metric” configurations as default, scroll down and choose a static threshold type. Set conditions whenever estimated charges are “Greater/Equal” and the threshold value to 10 USD, then click “Next”.


![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/ac8ea797ad1b4d4647bd27155a6c908b6e870760/Images/Screenshot%202024-12-24%20121539.png) 


For configuration actions, select “In alarm”, then select “Create new topic” to notify us by email when we exceed our threshold. Give it a descriptive name, enter the email recipient endpoint, then click “Create topic”.


![image alt[](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/6462f3259311a6363d386b8f51c8aaf260877227/Images/Screenshot%202024-12-24%20121935.png)

Scroll down, click “Next”, then give the alarm a name and description.


![image alt]()


Click “Next” again, scroll down, then click “Create alarm”.

![image alt](https://github.com/Tatenda-Prince/Create-Billing-Budget-and-Alarm-On-AWS-/blob/49976b5782e65b34e9b3e5d57e94b13d3797b381/Images/Screenshot%202024-12-24%20122105.png)


Note — the SNS subscription is pending confirmation. You need to head to the recipients email inbox, open the email you received, then click on the link to confirm your subscription to the SNS topic.

# Success!

our alarm should now be configured and ready to work!



























