# Travel Itinerary Generator

An AI-powered web application that creates personalized travel itineraries based on user preferences.

## Setup Instructions

### Frontend
1. The frontend consists of the following files:
   index.html, style.css, and script.js.
2. You can host these on **GitHub Pages**:
   - Upload the frontend files to a GitHub repository
   - Navigate to Settings → Page.
   - Choose the main branch as the deployment source


### Automation (n8n)
1. Import workflow.json into your n8n environment

2. Set up credentials:

   In the OpenAI Node, add your OpenAI API key

   In the Gmail Node (or any alternative email service), configure your email credentials

3.Enable the webhook:

   Open the Webhook Node

   Copy the Production URL

4.Connect the frontend:

   Open script.js

   Replace const WEBHOOK_URL = '...' with your copied n8n Production URL

## AI Usage Documentation

### Frontend Development (Cursor AI)
- **Role**: Development assistant.
- **Usage**:
    - Creating the glassmorphism UI styling in CSS.
    - Structuring semantic HTML5 form elements.
    - Implementing the initial POST request logic in script.js.

### Automation Logic (LLM in n8n)
- **Node**: OpenAI Chat Model (GPT-4)
- **System Prompt**: Expert travel consultant.
- **Input Processing**: Receives structured JSON input from the frontend (destination, budget, duration, etc.). Converts input into a detailed travel prompt
- **Output**: Produces an HTML-formatted itinerary. Sends the output directly through the Email node

## Design Decisions
- **No Backend**: All processing is handled through client-side logic and n8n workflows to meet project constraints.
- **Privacy**: Data is transmitted only to the n8n workflow and is not stored locally or persistently.
