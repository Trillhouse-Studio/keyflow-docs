---
title: "Schedule Triggers"
description: "Run your flows automatically at specific times using cron scheduling"
---

# Schedule Triggers

Schedule triggers run your flows at specific times and intervals using cron expressions. They're perfect for predictable, recurring processes that need to happen on a regular schedule.

Think of schedule triggers as your automation's clock - they ensure important workflows happen consistently without anyone having to remember to run them manually.

## When to Use Schedule Triggers

Schedule triggers work best for workflows that should run at predictable times, regardless of external events:

- **Daily reports**: Generate sales summaries every morning at 9 AM
- **Data synchronization**: Update your CRM with new leads every 2 hours
- **Cleanup processes**: Archive old files every Sunday at midnight
- **Monitoring workflows**: Check system health every 15 minutes
- **Weekly summaries**: Compile team metrics every Friday at 5 PM
- **Monthly tasks**: Process invoices on the 1st of each month

<Frame>
 <img src="/images/triggers/schedule-use-cases.png" alt="Examples of different schedule trigger patterns for various business workflows" />
</Frame>

## How Schedule Triggers Work

Schedule triggers use cron expressions to define exactly when your flows should run. Cron is a time-based scheduling system that lets you specify everything from simple daily schedules to complex patterns.

When you set up a schedule trigger, Keyflow monitors the clock and automatically runs your flow at the specified times. Each scheduled run appears in your workflow history just like manual runs.

## Scheduling Options

### Fixed Times

Run your flow at specific times each day, week, or month:

- **Daily at 9 AM**: Perfect for morning reports or data updates
- **Every Monday at 10 AM**: Great for weekly planning workflows
- **1st of every month at midnight**: Ideal for monthly cleanup or billing processes

### Regular Intervals

Run your flow at consistent intervals throughout the day:

- **Every 30 minutes**: For frequent monitoring or data syncing
- **Every 2 hours during business hours**: Balanced automation that respects work schedules
- **Every 6 hours**: For workflows that need regular but not constant attention

### Custom Patterns

Create complex schedules that match your business needs:

- **Weekdays only**: Monday through Friday automation
- **Multiple times per day**: 9 AM, 1 PM, and 5 PM
- **Seasonal schedules**: Different patterns for busy vs. quiet periods

<Frame>
 <img src="/images/triggers/cron-examples.png" alt="Cron expression examples showing different scheduling patterns" />
</Frame>

## Setting Up Schedule Triggers

### 1. Choose Your Flow

Start with a flow that you currently run manually on a regular basis. Weekly reports, daily data syncing, and recurring cleanup tasks are perfect candidates.

### 2. Define the Schedule

Think about when this workflow should run:

- What time of day makes the most sense?
- How often does it need to happen?
- Should it run on weekends?
- Do you need multiple runs per day?

### 3. Configure the Cron Expression

Keyflow provides both a visual scheduler and direct cron expression editing:

**Visual scheduler**: Use dropdowns and checkboxes to build your schedule
**Cron editor**: Write expressions directly for maximum flexibility  
**Schedule preview**: See exactly when your next few runs will happen

### 4. Test and Monitor

Start with a conservative schedule and adjust based on results. You can always change the timing later as you learn what works best for your workflow.

<Frame>
 <img src="/images/triggers/schedule-setup-interface.png" alt="Schedule trigger configuration interface showing visual scheduler and cron expression options" />
</Frame>

## Common Cron Patterns

Here are some frequently used cron expressions to get you started:

**Every day at 9 AM**
`0 9 \* \* \*`

**Every 2 hours during business hours (9 AM to 5 PM)**
`0 9-17/2 \* \* 1-5`

**Every 30 minutes**
`_/30 _ \* \* \*`

**Every Monday at 10 AM**
`0 10 \* \* 1`

**First day of every month at midnight**
`0 0 1 \* \* `

**Every weekday at 9 AM and 5 PM**
`0 9,17 \* \* 1-5`

## Best Practices

### Start Simple

Begin with basic schedules like "daily at 9 AM" before moving to complex patterns. It's easier to understand what's working and adjust accordingly.

### Consider Time Zones

Make sure your scheduled times make sense for your team's location and work hours. Keyflow respects your account's time zone settings.

### Plan for Failures

If a scheduled run fails, it won't automatically retry. Build error handling into your flows or plan to monitor and manually rerun when needed.

### Avoid Over-Scheduling

More frequent isn't always better. Consider the actual business need and the resources required. A workflow that runs every 5 minutes might create unnecessary load.

### Test Thoroughly

Run your flow manually a few times before scheduling it. Make sure it handles edge cases and produces the results you expect.

<Frame>
  <img src="/images/triggers/schedule-monitoring.png" alt="Schedule trigger monitoring dashboard showing run history and upcoming executions" />
</Frame>

## Monitoring Scheduled Flows

Once your schedule trigger is active, you can monitor its performance:

- **Upcoming runs**: See when your flow will execute next
- **Run history**: Track success rates and identify patterns
- **Execution time**: Monitor how long runs take and optimize if needed
- **Failure alerts**: Get notified when scheduled runs encounter problems

## Common Use Cases

### Daily Operations

- **Morning data sync**: Update your CRM with overnight leads every day at 8 AM
- **Daily reporting**: Generate yesterday's metrics every morning for team review
- **Inventory checks**: Monitor stock levels every day at closing time

### Weekly Routines

- **Team summaries**: Compile weekly progress reports every Friday afternoon
- **Data cleanup**: Archive completed projects every Sunday night
- **Planning workflows**: Prepare next week's priorities every Monday morning

### Monthly Processes

- **Billing automation**: Process subscriptions and invoices on the 1st of each month
- **Performance reviews**: Compile monthly metrics for management review
- **System maintenance**: Run cleanup and optimization tasks monthly

## Troubleshooting

**Flow not running at scheduled time?**

- Check your cron expression syntax
- Verify your account time zone settings
- Ensure the flow itself is working when run manually

**Scheduled runs failing?**

- Review the error logs from recent runs
- Test the flow manually with similar data
- Check if external services are available during scheduled times

**Too many or too few runs?**

- Double-check your cron expression
- Use the schedule preview to verify timing
- Consider if the frequency matches your actual needs

## Next Steps

Ready to set up your first schedule trigger? The process is straightforward once you know what schedule pattern you need.

<CardGroup cols={2}>
  <Card
    title="Setting Up Triggers"
    icon="play"
    href="/app/triggers/setup"
  >
    Complete guide to creating any trigger type
  </Card>
  
  <Card
    title="Monitoring Triggers"
    icon="chart-line"
    href="/app/triggers/monitoring"
  >
    Track performance and troubleshoot issues
  </Card>
</CardGroup>
