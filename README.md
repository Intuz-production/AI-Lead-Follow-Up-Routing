*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [Workflow Automation](https://www.intuz.com/workflow-automation-services/) · [AI Consulting Company](https://www.intuz.com/company/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Route lead reply follow-up tasks by intent with Gmail, OpenAI, Pipedrive, and Slack

## Quick overview

This workflow monitors a Gmail inbox for lead replies, looks up the sender in Pipedrive, uses OpenAI to classify the lead’s intent and urgency, then creates the appropriate Pipedrive follow-up activity, logs an AI analysis note, and notifies the deal owner via Slack and Gmail.

## How it works

1. Triggers every minute when a new email arrives in the Gmail inbox.
2. Extracts and cleans the sender name/email, subject, and message snippet for analysis.
3. Searches Pipedrive for a matching person using the sender’s email address and emails an internal reviewer if no match is found.
4. Sends the email details to OpenAI (GPT-4o) to classify intent, buying stage, sentiment, urgency, and recommended next action as JSON.
5. Normalizes the AI intent and routes the reply to the correct path (Meeting Request, Pricing Inquiry, Follow Up Later, or Not Interested).
6. Creates a corresponding Pipedrive activity (meeting, call, or mail) or marks the deal as lost for “Not Interested,” then adds a Pipedrive note with the full AI analysis.
7. Sends a Slack message to the deal owner with the AI summary and recommendation, then emails an internal summary with the same details.

## Setup

1. Connect Gmail OAuth2 credentials for both the Gmail Trigger (inbox monitoring) and Gmail nodes (sending the internal emails).
2. Connect a Pipedrive credential with permission to search persons, create activities, update deals, and create notes, and confirm your activity types (Meeting/Call/Mail) match your Pipedrive configuration.
3. Add an OpenAI credential (LangChain OpenAI node) and ensure the selected model (gpt-4o) is available in your account.
4. Connect Slack OAuth2 credentials and set the target Slack user (or adjust the node to post to a channel) for deal-owner notifications.
5. Update environment-specific fields such as the “lead not found” alert recipient email address and any variables used in the internal summary email (for example owner email/person/org fields if you want them populated from Pipedrive).

## Requirements

- ## AI Analysis Requirements
- Interested
- Meeting Request
- Pricing Inquiry
- Information Request
- Follow Up Later
- Not Interested
- Wrong Contact
- Competitor Mention
- Budget Constraint
- Project Delayed

## FAQ

**What triggers this workflow?**  
The workflow triggers every minute when a new email arrives in the connected Gmail inbox.

**How does the workflow classify lead replies?**  
It sends email details to OpenAI (GPT-4o) to classify the lead’s intent, buying stage, sentiment, urgency, and recommended next action as JSON.

**What actions does the workflow perform after classification?**  
It creates corresponding Pipedrive activities or updates deals, adds AI analysis notes, and notifies the deal owner via Slack and Gmail.

## Related n8n templates from Intuz

- [iCloudSyncManager for iOS](https://github.com/Intuz-production/iCloudSyncManager-iOS)
- [Backbone bits from Intuz](https://github.com/Intuz-production/Backbone-bits-iOS)
- [ev battery usage behavior](https://github.com/Intuz-production/ev-battery-usage-behavior)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
