# AWS-GuardDuty-Slack-Auto-Alerts
This project is inspired by the need to automate AWS GuardDuty notifications and is provided as-is for educational purposes.
# AWS GuardDuty Notification Project

This project aims to automate the process of detecting new findings in AWS GuardDuty and sending notifications via email and Slack.

## Features

- Connects to AWS GuardDuty using the Boto3 library.
- Retrieves new findings from GuardDuty.
- Sends email notifications using the `smtplib` library.
- Sends Slack notifications using the `slack_sdk` library.

## Prerequisites

- Python 3.x is installed.
- AWS account with GuardDuty set up.
- Email account for sending notifications.
- Slack workspace for sending Slack notifications.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/guardduty-notification.git

Install the required packages:
pip install boto3 slack_sdk

Configuration
Replace placeholders in the guardduty_notification.py script:

Replace YOUR_DETECTOR_ID with your AWS GuardDuty detector ID.
Replace email-related placeholders with your email server details and credentials.
Replace YOUR_SLACK_TOKEN with your Slack API token.
Replace #your-channel with the appropriate Slack channel.

Usage
Launch a terminal and navigate to the project directory.

Run the script to check for new findings and send notifications:
python guardduty_notification.py
The script will detect new findings and send email and Slack notifications if findings are detected.

Acknowledgements
This project is inspired by the need to automate AWS GuardDuty notifications and is provided as-is for educational purposes.
