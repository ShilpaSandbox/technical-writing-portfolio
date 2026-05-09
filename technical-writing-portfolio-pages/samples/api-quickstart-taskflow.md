---
layout: default
title: API Quickstart Guide
permalink: /samples/api-quickstart-taskflow/
---

# Quickstart: Getting Started with the TaskFlow API

<div class="meta-box">
<strong>Sample type:</strong> Developer documentation<br>
<strong>Focus:</strong> API onboarding, authentication, first request flow, and troubleshooting<br>
<strong>What this sample demonstrates:</strong> Concise technical explanation, structured steps, and audience-aware developer guidance
</div>

## Overview

The TaskFlow API lets developers create, update, and retrieve tasks programmatically. This quickstart shows how to authenticate, make your first request, and verify a successful response.

## Prerequisites

Before you begin, make sure you have:

- a TaskFlow account
- an API key
- a tool for sending HTTP requests, such as Postman or cURL

## Step 1: Generate an API Key

1. Sign in to the TaskFlow admin portal.
2. Go to **Developer Settings**.
3. Select **Create API Key**.
4. Copy the generated key and store it securely.

## Step 2: Send Your First Request

Use the following cURL command to retrieve a list of tasks:

```bash
curl --request GET \
  --url https://api.taskflow.dev/v1/tasks \
  --header "Authorization: Bearer YOUR_API_KEY" \
  --header "Content-Type: application/json"
```

## Step 3: Review the Response

If the request is successful, the API returns a `200 OK` response and a JSON array of tasks:

```json
{
  "data": [
    {
      "id": "t_1024",
      "title": "Draft onboarding guide",
      "status": "in_progress"
    }
  ]
}
```

## Common Errors

- **401 Unauthorized**: API key is missing, invalid, or expired
- **403 Forbidden**: account does not have access to the endpoint
- **429 Too Many Requests**: rate limit exceeded

## Next Steps

After confirming access, you can:

- create a task
- update task status
- filter tasks by user or project
- integrate TaskFlow into your internal workflow automation
