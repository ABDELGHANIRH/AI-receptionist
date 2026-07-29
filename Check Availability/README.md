# Check Availability

## Workflow Purpose
This workflow handles the Check Availability process as part of the AI Receptionist system.

## Triggers & Nodes
- **Trigger**: Executed by another workflow, MCP server, or webhook.
- **Nodes**: Relies on specific integrations depending on the workflow logic (e.g., Google Calendar, Google Sheets).

## Environment Variables / Credentials Required
To run this workflow, you need to configure the following within n8n:
- `<YOUR_EMAIL_ADDRESS>`: Your personal or business email address used for calendar access.
- `<YOUR_GOOGLE_SHEET_ID>`: The ID of your CRM Google Sheet.
- `<YOUR_CREDENTIAL_ID>`: Your n8n credential IDs (e.g., Google Sheets, Google Calendar).
- `<YOUR_WEBHOOK_ID>` (if applicable): The custom path/ID for your webhook.

## Import Instructions
1. Open your n8n instance.
2. Click **Add Workflow** (or go to an existing workflow).
3. Open the top right menu and select **Import from File**.
4. Upload the `workflow.json` file from this directory.
5. Update the credentials and placeholder values as required by your environment.
6. **Save** and **Activate** the workflow.
