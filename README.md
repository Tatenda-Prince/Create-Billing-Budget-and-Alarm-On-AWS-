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

You are a Cloud SysOps Administrator working for UP THE CHELS TECH. Your manager has informed you of a $10.00 AWS resource monthly spending limit she wants to place on your team’s account. She has tasked you to monitor the spending by tracking costs and has required that she be notified when it reaches a certain threshold before and when the spending limit is hit. You decided to use AWS Budgets, Amazon CloudWatch and Amazon SNS to accomplish this task.

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

![image alt]()

Now that we’ve enabled billing access for IAM users and updated billing preferences, we can proceed to actually creating the billing budgets and billing alarms.













