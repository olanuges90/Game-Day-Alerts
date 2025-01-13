# Developing a Serverless NBA Game-Day Alert System with AWS Lambda, SNS, EventBridgeand External API
# Project Overview
This Project is a Game-DayAlert system built with Python Programming language that delivers real-time NBA game-day alerts to subscribed users via Email. It leverages various AWS Serveless services like AWS Lambda, Amazon SNS, and Amazon EventBridge using an External NBA APIs to keep sports fans informed with the latest game updates. The project showcases cloud computing concepts and efficient notification strategies.


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
         
         git clone 
    
    
  
