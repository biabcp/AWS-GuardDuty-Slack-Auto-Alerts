import boto3
import smtplib
from email.mime.text import MIMEText
from slack_sdk import WebClient

def send_email(subject, message, to_email):
    from_email = "your@email.com"  # Your email address
    msg = MIMEText(message)
    msg["Subject"] = subject
    msg["From"] = from_email
    msg["To"] = to_email

    # Connect to the SMTP server and send the email
    server = smtplib.SMTP("smtp.example.com", 587)  # Replace with your SMTP server details
    server.starttls()
    server.login(from_email, "your-email-password")  # Replace with your email password
    server.sendmail(from_email, to_email, msg.as_string())
    server.quit()

def send_slack_notification(message):
    slack_token = "YOUR_SLACK_TOKEN"
    client = WebClient(token=slack_token)
    response = client.chat_postMessage(channel="#your-channel", text=message)
    return response["ok"]

def main():
    # Initialize the AWS GuardDuty client.
    guardduty_client = boto3.client("guardduty")

    # Get the list of new findings.
    findings = guardduty_client.get_findings(
        DetectorId="YOUR_DETECTOR_ID",
        MaxResults=10
    )

    if findings["Findings"]:
        # Send an email notification.
        email_subject = "GuardDuty Findings Alert"
        email_message = "New GuardDuty findings detected. Check the GuardDuty console for details."
        send_email(email_subject, email_message, "recipient@email.com")

        # Send a Slack notification.
        slack_message = "New GuardDuty findings detected. Check the GuardDuty console for details."
        if send_slack_notification(slack_message):
            print("Slack notification sent successfully.")
        else:
            print("Failed to send Slack notification.")

if __name__ == "__main__":
    main()
