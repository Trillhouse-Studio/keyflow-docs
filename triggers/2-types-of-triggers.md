---
title: "Types of Triggers"
description: "Choose the right trigger type for your automation needs"
---

# Types of Triggers

Different situations call for different types of triggers. Some workflows should run on predictable schedules, others need to respond immediately to API calls, and some should activate when events happen in your connected apps.

Here's how to choose the right trigger type for your automation.

## Schedule Triggers

Schedule triggers run your flows at specific times using cron scheduling. Perfect for predictable, recurring processes that need to happen at regular intervals.

**Best for:**

- Daily reports at 9 AM
- Data syncing every 2 hours
- Monthly cleanup on the 1st
- Monitoring checks every 15 minutes

**How it works:** Set up cron expressions to define exactly when your flows should run - from simple daily schedules to complex patterns like "every weekday at 10 AM and 3 PM."

<Frame>
 <img src="/images/triggers/schedule-trigger-preview.png" alt="Schedule trigger card showing cron scheduling options" />
</Frame>

## API Triggers

API triggers let external systems activate your flows by making API calls. Each flow gets a unique API key that other systems can use to trigger workflows instantly.

**Best for:**

- Form submissions from your website
- Payment processing webhooks
- System notifications and alerts
- Third-party app integrations

**How it works:** Generate a unique API key for your flow, then configure external systems to call your flow's endpoint when specific events happen. Perfect for real-time automation.

<Frame>
 <img src="/images/triggers/api-trigger-preview.png" alt="API trigger card showing endpoint configuration and API key" />
</Frame>

## Event-Based Triggers

Event-based triggers watch your connected apps and activate flows when specific events occur. Currently supports Gmail, Airtable, and Google Drive.

**Best for:**

- Processing new emails as they arrive
- Responding to database changes
- Monitoring file uploads and modifications
- Automated workflows based on app activity

**How it works:** Connect your apps to Keyflow and define which events should trigger your flows. Runs automatically whenever those events happen in your connected services.

<Frame>
 <img src="/images/triggers/event-trigger-preview.png" alt="Event trigger card showing Gmail, Airtable, and Google Drive integration options" />
</Frame>

## Choosing the Right Trigger Type

**Use Schedule Triggers when:**

- You know exactly when work should happen
- You're processing batches of data at regular intervals
- Timing is more important than immediate response
- You want predictable automation that runs on your schedule

**Use API Triggers when:**

- You need instant response to external events
- Other systems can notify you when something happens
- You're integrating with third-party services
- Speed of response is critical for your workflow

**Use Event-Based Triggers when:**

- You want to respond to changes in Gmail, Airtable, or Google Drive
- Your team's work happens inside these connected apps
- You need reactive automation based on real user activity
- You want seamless integration with existing workflows

## Combining Trigger Types

Advanced automation often uses multiple trigger types for the same flow. For example, a "Process New Leads" flow might use:

- **API trigger**: For leads from your website form
- **Event-based trigger**: For leads added to your Airtable CRM
- **Schedule trigger**: As a backup to process any missed leads every hour

This creates resilient automation that works regardless of how work arrives.

## Explore Each Trigger Type

Ready to dive deeper? Each trigger type has its own setup process and configuration options:

<CardGroup cols={3}>
 <Card
   title="Schedule Triggers"
   icon="clock"
   href="/app/triggers/schedule"
 >
   Set up cron-based scheduling for recurring workflows
 </Card>
 
 <Card
   title="API Triggers"
   icon="code"
   href="/app/triggers/api"
 >
   Create API endpoints for external system integration
 </Card>
 
 <Card
   title="Gmail Triggers"
   icon="envelope"
   href="/app/triggers/gmail"
 >
   Automate email processing and label-based workflows
 </Card>
</CardGroup>

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

## Next Steps

Once you understand the trigger types, you're ready to start setting up automation:

<Card
title="Setting Up Triggers"
icon="play"
href="/app/triggers/setup"

> Step-by-step guide to creating and configuring any trigger type
> </Card>
