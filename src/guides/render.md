---
order: 1100
icon: /media/render.svg
label: Render
tags: guides
---

# Setting up Render with an is-a.dev Subdomain

This guide will walk you through the process of setting up a Render deployment and pointing your is-a.dev subdomain towards it.

## Creating a Render Service

First, create a service on Render. Follow the instructions in the [Render Documentation](https://docs.render.com/).

### Creating the Domain File

Create a JSON file inside the `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "your-github-username",
        "email": "me@example.com"
    },
    "records": {
        "A": ["216.24.57.1"]
    }
}
```

**Note:** In the owner section, you can add any social media handle, such as Discord. If you add another social media account, you can omit the email field. However, the GitHub username is mandatory. Don't forget to provide a preview of your website in your pull request.

## Configuring Render

- After your pull request is merged, you may need to configure your Render service to use the new subdomain. Go to your Render service's dashboard.
- Navigate to **Settings > Custom Domains** and add `subdomain.is-a.dev` in the given field.
- Render will provide a verification step, usually requiring you to add a DNS record. This step should be skipped if your subdomain is already pointing to Render's IP address (`216.24.57.1`).

### Final Steps

- Wait for the DNS changes to propagate. This can take from a few minutes to a couple of hours.
- Your Render service should now be accessible at `subdomain.is-a.dev`.
