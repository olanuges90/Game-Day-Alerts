# Developing a Serverless NBA Game-Day Alert System with AWS Lambda, Amazon SNS, Amazon EventBridge and External API
# Project Overview
This Project is a Game-Day Alert system built with Python Programming language that delivers real-time NBA game-day alerts to subscribed users via Email. It leverages various AWS Serveless services like AWS Lambda, Amazon SNS, and Amazon EventBridge using an External NBA APIs to keep sports fans informed with the latest game updates. The project showcases cloud computing concepts and efficient notification strategies.


# Architectural Diagram
![image](https://github.com/user-attachments/assets/e0f74cbf-52fc-4a15-8637-1e905d96b2e0)

 # Objectives
 - Uses an External API to retrieve real-time NBA game scores.
 - Sends Real-time updates to subscribers via email through Amazon SNS.
 - Schedules Automation based on a Schedule Rule using Amazon EventBridge.
 - Security Driven system adhering to the principle of least privilege for IAM roles.

# Prerequisites
- A basic understanding of Python programming with version 3 or greater installed
- Free Subscription to External API (Sportsdata.io)

# Technologies
- Cloud Platform: Amazon Web Services
- AWS Services: AWS Lambda, Amazon SNS, Amazon Eventbridge
- Programming Language: Python 3.x
- External API (Sportsdata.io)
- IAM Security
- GitHub

#Project Structure
  
    game-day-alerts/
     ├── src/
     │   ├── gd_notifications.py          # Main Lambda function code
     ├── policies/
     │   ├── gb_sns_policy.json           # SNS publishing permissions
     │   ├── gd_eventbridge_policy.json   # EventBridge to Lambda permissions
     │   └── gd_lambda_policy.json        # Lambda execution role permissions
     ├── .gitignore
     └── README.md                        # Project Overview

  # Set up Instructions
  To begin, clone the repository to your local machine:
         
         git clone https://github.com/olanuges90/Game-Day-Alerts.git
         cd Game-Day-Alerts
  ## Create SNS Topic
 - In the AWS management console, search for SNS service.
 - In Create a topic bar, give the topic a name (i.e game_alerts) and Click Next step.
 - Select Standard as topic type.
 -  Create Topic.
 ## Create Subscription
 - Navigate and Click on the Subscription Tab and select the Topic name from the drop down in the Topic ARN.
 - Select a Protocol.
 - In the Endpoint, Enter a valid email.
 - Click Subscription.
## Confirm Subscription
- Go to the Inbox of the email address provided.
- Confirm the subscription via the confirmation link.
- Verify the subscription in the subscription Panel in the AWS management console.
## Create SNS Publish Policy
- Nagivate to AWS management console. Search for IAM and Click IAM.
- In the IAM Dashboard, click on Policies and Create Policy.
- In the Select service list, choose SNS.
- Click on JSON.
- Copy the JSON Policy from the JSON file in the repository and Paste the JSON policy in the policy editor.
- In the Resource tag in the code, replace REGION and ACCOUNT_ID with the AWS region and account ID of your AWS account.
- Click Next.
- In review and tags, Give the Policy a name (i.e gd_sns_policy) and Create Policy.
### Create IAM Role for Lambda
- In the AWS Dashboard, click on Roles and Create Role.
- Select AWS Service.
- In the Use case list, Select Lambda and Click Next.
- Add the polices created earlier to the role (i.e gd_sns_policy and Lambda Basic Execution Role) and Click Next.
- Enter a Name for the Role (i.e gd_lambda_role) and Create Role.
- Copy and Save the Role ARN.
## Deploy the Lambda Function
- In AWS Management Console, Search and Select Lambda.
- Click Create Function.
- Select Author from scratch.
- Enter a Function Name.
- In the Runtime list, Select Python 3.13.
- Select Use an existing role and choose an existing role (i.e gd_lamda_role).
- Click on Create Function.
- Nagivate to Code and Copy the python code from the src/game_notifications.py file and Paste it in the Inline code editor.
- Nagivate to Configuration and Edit Environment variables.
  - Copy the API Key generated from the sportsdata.io website, Type the NBA_API_KEY as Key and the API Key as Value. Click on Add Environment Variable.
  - Copy the SNS TOPIC ARN. Type the SNS_TOPIC_ARN as Key and the SNS TOPIC ARN as Value. Click Save.
 ## Configure EventBridge for Automation
 - In the AWS Management Console, Search and Select Amazon EventBridge.
 - Select Rules and Click Rules.
 - Give the Rule a name and Select Schedule as Rule Type.
 - Click on Continue in EventBridge Scheduler.
 - Select Cron-based schedule as Schedule type.
 - Define a Cron expression and Click Next.
 - In Target detail, Select AWS Lambda Invoke.
 - In Lambda Function list, Select the Lambda Function (gd_notifications) and Click Next.
 - In the Permissions, Select Create New role for this schedule, click Next.
 - Create Schedule.
  ## Test the System
 - Open the Lambda Function Created In the AWS management console.
 - Select Create a New Event. Name your event (i.e Test Function).
 - Save the Event and Test.
 - Check Cloudwatch log for errors.
 - Verify the Email Notification is being sent to the subscribed email user.
## Conclusion
In this project, I built a serverless NBA Game-Day Alert System using AWS Lambda, Amazon SNS, Amazon EventBridge, and an external sports API. This system provides real-time game updates and sends notifications to subscribed user email. By leveraging AWS serverless services, I have created an efficient, scalable, secure and cost-effective solution for delivering personalized alerts. 
Future enhancements could include adding more detailed notifications, expanding to additional sports leagues, implementing a Web UI or integrating with other communication channels like push notifications or messaging platforms.
    
  
