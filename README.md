# Lead Capture & Email Notification Automation

An automated lead management workflow built with **n8n, Google Sheets, and Gmail** to capture client inquiries, store lead information, and send email notifications automatically.

## Overview

Managing client inquiries manually can be time-consuming. This project automates the lead collection process by connecting an online form with Google Sheets and Gmail.

Whenever a client submits the form, the workflow records their details in a spreadsheet and sends an email notification containing the submitted information.

## Features

- **Automated Form Submission:** Collects client names and service preferences through an n8n form.
- **Google Sheets Integration:** Automatically appends lead details to a spreadsheet.
- **Gmail Notifications:** Sends an email notification whenever a new lead is submitted.
- **Timestamp Tracking:** Records the form submission time.
- **Service Selection:** Supports Consultancy, Training, and Repair inquiries.
- **No Manual Data Entry:** Connects the entire process into a single automated workflow.

## Workflow Architecture

```text
Client Submits Form
        |
        v
   n8n Form Trigger
        |
        v
  Google Sheets
  Append Lead Details
        |
        v
   Gmail Notification
        |
        v
  Lead Notification Received
```


flowchart LR
  ```mermaid
flowchart TD
    A["Client submits form"]
    B["n8n Form Trigger"]
    C["Google Sheets: Append Row"]
    D["Gmail: Send Notification"]
    E["Lead captured successfully"]

    A --> B
    B --> C
    C --> D
    D --> E
```


## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| n8n Forms | Collecting client inquiries |
| Google Sheets | Storing lead information |
| Gmail | Sending email notifications |
| JSON | Workflow export and portability |

## Data Collected

The current workflow captures the following information:

| Field | Description |
|---|---|
| Name | Name submitted by the client |
| Service | Selected service: Consultancy, Training, or Repair |
| Time | Form submission timestamp |

## How It Works

1. A client opens the online form and enters their name.
2. The client selects a service from the dropdown menu.
3. The form submission triggers the n8n workflow.
4. n8n appends the name, selected service, and timestamp to Google Sheets.
5. Gmail sends an email notification containing the lead information.
6. The lead is recorded in the spreadsheet for future reference.

## Setup Instructions

### Prerequisites

- An n8n account or local n8n installation
- A Google account with access to Google Sheets
- A Gmail account
- A Google spreadsheet prepared with the required columns

### Step 1: Import the Workflow

1. Download the workflow JSON file from this repository.
2. Open your n8n workspace.
3. Select the option to import a workflow from a file.
4. Upload the downloaded JSON file.

### Step 2: Configure Google Sheets

1. Open the Google Sheets node.
2. Connect your Google account using the supported OAuth authentication.
3. Select your destination spreadsheet and worksheet.
4. Ensure the sheet has these column headers:

```text
Name | Services | Time
```

### Step 3: Configure Gmail

1. Open the Gmail node.
2. Connect your Gmail account using OAuth authentication.
3. Set the recipient email address to your preferred notification inbox.
4. Review the email subject and message template.

### Step 4: Test the Workflow

1. Open the n8n form and submit sample information.
2. Verify that a new row appears in Google Sheets.
3. Check your inbox for the corresponding email notification.
4. Review the workflow execution to identify any errors.

### Step 5: Activate the Workflow

After successful testing, activate or publish the workflow as supported by your n8n version and deployment.

**Note:** The workflow depends on valid Google Sheets and Gmail credentials. Imported credentials may need to be configured again in your own n8n workspace.

## Example Email Notification

```text
Subject: Form Lead Update

A new lead has been submitted.

Name: [Client Name]
Service: [Selected Service]
Time: [Submission Timestamp]

Source: [Workflow ID]
```

## Use Cases

- AI and technology training inquiries
- Consultancy lead collection
- Small business client inquiries
- Service request management
- Basic customer onboarding workflows

## Security Considerations

- Never upload OAuth credentials, access tokens, API keys, or other secrets to a public repository.
- Use n8n's credential management system to store authentication details securely.
- Review workflow exports before publishing because they may contain account identifiers, email addresses, spreadsheet IDs, or other configuration details.
- Restrict access to the connected spreadsheet and email account.
- Avoid storing unnecessary personal information in submitted forms.

## Current Limitations

- The workflow currently captures only a name and selected service.
- Lead notifications are sent to a configured email recipient.
- There is no duplicate-lead detection or retry and recovery mechanism explicitly configured in the current workflow.
- The workflow does not currently include CRM integration, advanced analytics, or automated follow-up emails.

## Future Enhancements

- Collect email addresses and phone numbers.
- Add input validation and duplicate-lead detection.
- Send automatic confirmation emails to clients.
- Integrate with a CRM platform.
- Add error handling and failure notifications.
- Create a lead analytics dashboard.
- Implement follow-up reminders and lead status tracking.

## Learning Outcomes

This project demonstrates practical experience with:

- No-code and low-code workflow automation
- Event-driven workflow design
- API-connected application integrations
- Spreadsheet-based data management
- Automated email notifications
- Workflow testing and deployment

## Author

**Ayush Gupta**

B.Tech — Computer Science and Engineering (Artificial Intelligence and Machine Learning)

GitHub: [Ayushh890](https://github.com/Ayushh890)

---

If you find this project useful, consider giving the repository a star!

