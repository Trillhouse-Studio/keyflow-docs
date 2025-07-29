---
title: "Gmail Triggers"
description: "Automate workflows based on Gmail events like new emails, labels, and folder changes"
---

# Gmail Triggers

Gmail triggers let you automate workflows based on what happens in your Gmail account. Whether it's processing new emails as they arrive, responding to label changes, or handling specific types of messages, Gmail triggers turn your inbox into a powerful automation hub.

Think of Gmail triggers as your email-based workflow engine. Every email event becomes an opportunity to kick off intelligent automation.

## When to Use Gmail Triggers

Gmail triggers excel when your work involves email processing or when email serves as an input channel for your business processes:

- **Customer support automation**: Convert emails to support tickets with proper categorization
- **Lead processing**: Extract contact information from forwarded sales emails and add to CRM
- **Document workflows**: Process attachments like invoices, contracts, or reports automatically
- **Task assignment**: Apply labels to emails to trigger customer support or project workflows
- **Email routing**: Automatically categorize and distribute emails to appropriate team members
- **Notification processing**: Handle alerts sent via email from various business systems

<Frame>
 <img src="/images/triggers/gmail-automation-examples.png" alt="Examples of Gmail-based automation workflows for different business scenarios" />
</Frame>

## How Gmail Triggers Work

Once you connect your Gmail account to Keyflow, our system monitors your inbox in real-time for specific events. When those events occur, your connected flows run automatically with the email data as input.

Gmail triggers respond to four main types of events:

- Emails being added to folders/labels
- Emails being removed from folders/labels
- Labels being applied to emails
- Labels being removed from emails

This gives you flexibility to create automation that responds to both incoming mail and how you organize it.

## Types of Gmail Events

### Email Added to Inbox/Folder

Triggers when new emails arrive in your inbox or specific folders. Perfect for processing incoming requests, leads, or notifications as they happen.

**Common uses:**

- Process all incoming emails for lead extraction
- Monitor specific folders for customer inquiries
- Handle forwarded emails from team members

### Email Removed from Inbox/Folder

Triggers when emails are deleted, archived, or moved out of monitored folders. Useful for cleanup workflows or tracking email lifecycle.

**Common uses:**

- Log resolved support tickets when emails are archived
- Track email processing completion
- Cleanup related records when emails are deleted

### Label Added to Email

Triggers when you or your team apply specific labels to emails. This is powerful for manual workflow initiation - apply a label to trigger automation.

**Common uses:**

- Apply "Process Invoice" label to trigger accounting workflows
- Use "Assign to Support" label to create support tickets
- Tag emails with "High Priority" to trigger escalation processes

### Label Removed from Email

Triggers when labels are removed from emails. Useful for tracking status changes or cleanup processes.

**Common uses:**

- Remove "Pending" labels when tasks are completed
- Track workflow state changes
- Clean up temporary processing labels

<Frame>
 <img src="/images/triggers/gmail-event-types.png" alt="Visual representation of different Gmail events that can trigger workflows" />
</Frame>

## Setting Up Gmail Triggers

### 1. Connect Your Gmail Account

First, authorize Keyflow to access your Gmail account. This creates a secure connection that lets us monitor for email events without storing your email content.

### 2. Choose Your Event Type

Select which Gmail events should trigger your flow:

- New emails arriving
- Label changes
- Folder/inbox changes
- Specific combinations of the above

### 3. Configure Filters

Define which emails should trigger your workflow:

- **All emails**: Process everything that comes to your account
- **Specific folders**: Only monitor designated Gmail folders/labels
- **Sender filters**: Only trigger for emails from specific addresses or domains
- **Subject patterns**: Trigger based on keywords in email subjects

### 4. Set Up Label-Based Triggers

For label-based automation, choose which labels will trigger your flows. This is particularly powerful for creating manual workflow triggers - just apply the right label to any email to kick off automation.

<Frame>
 <img src="/images/triggers/gmail-trigger-setup.png" alt="Gmail trigger configuration interface showing event selection and filtering options" />
</Frame>

## Common Use Cases & Patterns

### Customer Support Automation

Create a "Support Ticket" label in Gmail. When you apply this label to any email, it triggers a flow that:

- Extracts customer information and issue details
- Creates a ticket in your support system
- Assigns it to the appropriate team member
- Sends an acknowledgment email to the customer

### Lead Processing Pipeline

Monitor your sales inbox for new emails. When leads are forwarded or arrive directly:

- Extract contact information and company details
- Research the company using web scraping or database lookups
- Score the lead based on predefined criteria
- Add qualified leads to your CRM with enriched data
- Notify the appropriate sales representative

### Invoice Processing Workflow

Create an "Invoice Processing" label. When applied to emails with invoice attachments:

- Extract invoice data from PDF attachments
- Validate invoice details against purchase orders
- Route to appropriate approvers based on amount
- Update accounting systems when approved
- Archive processed invoices with proper categorization

### Document Review Process

Monitor a shared inbox for document submissions:

- Download and analyze attached documents
- Extract key information and metadata
- Route to appropriate reviewers based on document type
- Track review status and send reminders
- Archive completed reviews with searchable summaries

<Frame>
 <img src="/images/triggers/gmail-workflow-examples.png" alt="Detailed workflow diagrams showing common Gmail automation patterns" />
</Frame>

## Data Available to Your Flow

When Gmail triggers activate your flow, you get access to comprehensive email data:

### Email Content

- Full email body (text and HTML versions)
- Email subject line
- Thread information for email conversations
- Original message for replies and forwards

### Sender Information

- Sender email address and display name
- Reply-to address if different from sender
- Recipient information (to, cc, bcc)

### Attachments

- File names and types
- File content for processing
- Attachment metadata and sizes

### Gmail Metadata

- Labels applied to the email
- Folder/inbox location
- Message ID and thread ID
- Timestamp and delivery information
- Priority and importance markers

### Event Context

- Which event triggered the flow (new email, label added, etc.)
- Previous state information for label/folder changes
- User who triggered manual label changes

## Best Practices

### Label Organization Strategy

- Create clear, descriptive labels for different workflow triggers
- Use consistent naming conventions (e.g., "Flow: Invoice Processing")
- Document which labels trigger which workflows for team clarity
- Regularly review and clean up unused labels

### Avoiding Processing Loops

- Be careful when flows modify the same emails that triggered them
- Use specific filters to avoid re-triggering on your own changes
- Consider using temporary labels that get removed after processing
- Test thoroughly to ensure flows don't create infinite loops

### High-Volume Email Handling

- Use specific filters rather than processing all emails
- Consider batching for accounts that receive many emails
- Monitor processing times and optimize flows for performance
- Set up error handling for temporary Gmail API limits

### Security and Privacy

- Only grant necessary permissions to your Gmail account
- Regularly review which flows have Gmail access
- Be mindful of sensitive email content in your automation
- Use secure storage for any extracted email data

<Frame>
 <img src="/images/triggers/gmail-best-practices.png" alt="Best practices dashboard showing label organization and security settings" />
</Frame>

## Next Steps

Gmail triggers work best when combined with other Keyflow features. Consider how email automation fits into your broader workflow strategy.

<CardGroup cols={2}>
 <Card
   title="Airtable Triggers"
   icon="table"
   href="/app/triggers/airtable"
 >
   Respond to database changes and new records
 </Card>
 
 <Card
   title="Google Drive Triggers"
   icon="folder"
   href="/app/triggers/google-drive"
 >
   Monitor file uploads and folder changes
 </Card>
</CardGroup>

</CardGroup>
