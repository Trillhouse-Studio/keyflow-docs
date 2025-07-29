---
title: "API Triggers"
description: "Integrate external systems with your flows using API-based triggers"
---

# API Triggers

API triggers let external systems activate your flows by making API calls. Each flow gets a unique API key that other systems can use to trigger workflows instantly, making this perfect for real-time automation and third-party integrations.

Think of API triggers as bridges between your flows and the rest of your tech stack. When something happens in an external system, it can immediately trigger your Keyflow automation.

## When to Use API Triggers

API triggers excel when you need instant response to external events:

- **Form submissions**: Process contact forms, surveys, or registration data immediately
- **Payment processing**: Handle successful payments, refunds, or subscription changes in real-time
- **System notifications**: Respond to alerts from monitoring tools, error tracking, or security systems
- **Third-party integrations**: Connect with any service that can make HTTP requests
- **Mobile app events**: Trigger workflows from user actions in your mobile applications
- **IoT device data**: Process sensor data or device status updates instantly

<Frame>
  <img
    src="/images/triggers/api-trigger-integrations.png"
    alt="Diagram showing various external systems connecting to Keyflow via API triggers"
  />
</Frame>

## How API Triggers Work

When you enable an API trigger on a flow, Keyflow generates a unique API key for that specific workflow. External systems can then make API calls using this key to trigger your flow instantly.

Here's the basic process:

1. Your flow gets a unique API key
2. External systems make POST requests to your flow's endpoint
3. Data from the API call becomes input for your workflow
4. Your flow runs immediately with that data

This creates seamless integration between Keyflow and your existing systems.

## Setting Up API Triggers

### 1. Enable API Trigger

Start with a flow that should respond to external events. In your flow settings, enable the API trigger option.

### 2. Generate API Key

Keyflow automatically creates a unique API key for your flow. This key is what external systems will use to authenticate and trigger your workflow.

### 3. Configure Your Endpoint

You'll get an API endpoint URL and the authentication details needed for external systems to call your flow.

### 4. Test the Integration

Before connecting live systems, test your API trigger with sample data to ensure everything works as expected.

<Frame>
  <img
    src="/images/triggers/api-trigger-setup.png"
    alt="API trigger configuration interface showing API key generation and endpoint details"
  />
</Frame>

## Making API Calls

### Basic Structure

External systems trigger your flow by making POST requests with your API key for authentication. Here's a simple example:

```bash
curl -X POST \
  https://api.keyflow.com/v1/flows/trigger \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "customer_email": "john@example.com",
    "order_total": 299.99,
    "product_id": "widget-123"
  }'
```

### Passing Data to Your Flow

Any JSON data you include in the request body becomes available as input in your flow. This lets you pass customer information, order details, form responses, or any other relevant data.

### Complete API Reference

For detailed information about all available endpoints, authentication methods, request formats, and response codes, see our complete [API Reference](/api) documentation. This includes:

- All trigger endpoints and parameters
- Flow management APIs
- Error handling and status codes
- Rate limiting and best practices
- Advanced authentication options

## Common Integration Patterns

### Website Forms

Connect contact forms, lead capture pages, or survey tools:

```javascript
// When form is submitted
fetch("https://api.keyflow.com/v1/flows/trigger", {
  method: "POST",
  headers: {
    Authorization: "Bearer YOUR_API_KEY",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    name: formData.name,
    email: formData.email,
    message: formData.message,
    source: "contact_form",
  }),
});
```

### Payment Webhooks

Process Stripe, PayPal, or other payment system events:

```python
# Stripe webhook handler
import requests

def handle_payment_success(payment_data):
    requests.post('https://api.keyflow.com/v1/flows/trigger',
        headers={'Authorization': 'Bearer YOUR_API_KEY'},
        json={
            'customer_id': payment_data['customer'],
            'amount': payment_data['amount'],
            'currency': payment_data['currency'],
            'event_type': 'payment_success'
        }
    )
```

### System Alerts

Connect monitoring tools or error tracking systems:

```bash
# From monitoring system
curl -X POST \
  https://api.keyflow.com/v1/flows/trigger \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "alert_type": "server_down",
    "server_name": "web-01",
    "timestamp": "2024-01-15T10:30:00Z",
    "severity": "critical"
  }'
```

<Frame>
  <img src="/images/triggers/api-integration-examples.png" alt="Code examples showing different API integration patterns" />
</Frame>

## Data Handling

### JSON Payload Structure

Your flow receives all API call data as structured input. Design your flows to expect specific data fields, and handle cases where optional fields might be missing.

### Data Validation

Build validation into your flows to handle unexpected data formats or missing required fields gracefully.

### Error Responses

If your flow can't process the incoming data, the API call will return error details that the calling system can use for troubleshooting.

## Security and Best Practices

### API Key Management

- Keep API keys secure and never expose them in client-side code
- Rotate keys periodically for enhanced security
- Use different keys for different environments (development, staging, production)

### Input Validation

- Always validate incoming data in your flows
- Handle unexpected or malformed requests gracefully
- Log important events for debugging and monitoring

### Error Handling

- Build retry logic into external systems for temporary failures
- Monitor API call success rates and investigate patterns
- Provide meaningful error messages for debugging

<Frame>
  <img src="/images/triggers/api-security-dashboard.png" alt="API security monitoring dashboard showing key usage and access patterns" />
</Frame>

## Monitoring API Triggers

Track the performance and reliability of your API integrations:

### Call History

- View all API calls made to your flows
- See success and failure rates over time
- Identify patterns in usage and errors

### Performance Metrics

- Monitor response times and throughput
- Track which external systems are most active
- Identify bottlenecks or scaling needs

### Debugging Tools

- Inspect failed requests with full error details
- Test API calls directly from the Keyflow interface
- View request/response data for troubleshooting

## Troubleshooting

### Authentication Issues

- Verify API key is correct and active
- Check that authorization header is properly formatted
- Ensure the API key has permission to trigger the specific flow

### Data Format Problems

- Confirm JSON payload is valid and properly structured
- Check that required fields are included
- Verify data types match what your flow expects

### Network and Timing Issues

- Test API endpoints from different networks
- Implement retry logic for temporary failures
- Monitor for rate limiting or timeout errors

### Integration Debugging

- Use API testing tools like Postman to isolate issues
- Check external system logs for request/response details
- Verify that webhook URLs and endpoints are correctly configured

## Next Steps

API triggers work best when combined with proper monitoring and error handling. Once your integration is running, focus on observability and optimization.

<CardGroup cols={2}>
  <Card
    title="API Reference"
    icon="code"
    href="/api"
  >
    Complete documentation for all Keyflow APIs and endpoints
  </Card>

<Card
title="Monitoring Triggers"
icon="chart-line"
href="/app/triggers/monitoring"

>

    Track performance and troubleshoot integration issues

  </Card>
</CardGroup>

<Card
title="Setting Up Triggers"
icon="play"
href="/app/triggers/setup"

> General guide to creating and configuring any trigger type
> </Card>
