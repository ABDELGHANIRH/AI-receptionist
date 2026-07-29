# AI Receptionist System

## System Overview
The AI Receptionist is a comprehensive suite of n8n automations designed to act as a virtual assistant for your business. It seamlessly manages client inquiries, checks availability, books and updates appointments, and interfaces with your CRM—all through natural language interactions.

## Architecture & Workflow Structure
The system is composed of an orchestrating MCP (Model Context Protocol) Server and several specialized sub-workflows. 

- **Vapi MCP Server**: The central brain that receives inputs from AI platforms (like Vapi) and routes them to the appropriate tool.
- **Client Lookup & New Client CRM**: Interfaces with Google Sheets to retrieve or create client records.
- **Check Availability**: Queries Google Calendar for free time slots.
- **Book, Update, and Delete Appointment**: Manages Google Calendar events.
- **Hercules Receptionist EOC Report**: Generates end-of-call summaries.

## Prerequisites
- **n8n Instance**: Self-hosted or Cloud (version 1.1+ recommended).
- **Google Cloud Console Account**: For setting up Google Sheets and Google Calendar OAuth credentials.
- **Vapi (or similar voice/AI provider)**: To interact with the MCP server.

## Global Setup & Installation Guide
1. **Set Up Credentials**: In n8n, create OAuth2 credentials for both Google Sheets and Google Calendar.
2. **Import Workflows**: Navigate to each folder (e.g., `Book Event`, `Client Lookup`) and import the respective `workflow.json` into your n8n workspace.
3. **Configure Placeholders**: Update the placeholder IDs (like `<YOUR_GOOGLE_SHEET_ID>`) with your actual Google Sheet ID and connect your newly created credentials to the nodes.
4. **Connect MCP Server**: In the `Vapi MCP Server` workflow, ensure all "Call Tool" nodes are pointing to the correct IDs of the sub-workflows you just imported.

## Usage & Testing
1. Activate all imported workflows.
2. Trigger the `Vapi MCP Server` via its designated webhook URL.
3. Send a test payload querying for an appointment.
4. Verify that the system correctly reads from the CRM, checks the calendar, and returns a valid response.
