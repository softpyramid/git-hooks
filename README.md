# Git Activity Tracking Hook

A Git hook implementation that automatically tracks developer activity and sends it to a centralized monitoring system.

## Overview

This repository contains a post-commit hook that tracks developer activities and reports them to a Laravel-based API endpoint. The hook captures essential information about commits and pushes them to a centralized monitoring system.

## Setup

1. Ensure the post-commit hook is executable:
   ```bash
   chmod +x .git/hooks/post-commit
   ```

2. Configure your MIS credentials in the post-commit hook:
   ```bash
   AUTH_USER="your.email@softpyramid.com"
   AUTH_PASS="your-mis-password"
   ```

## Tracked Information

The hook tracks the following information:
- Developer name and email
- Repository URL
- Branch name
- Commit URL
- Commit message
- Activity type

## Requirements

- Git
- curl
- jq (for JSON processing)

## API Endpoint

The hook sends data to:

https://mis.softpyramid.com.pk/api/log-activity

## Using with Husky

1. Install Husky in your project:
   ```bash
   npm install husky --save-dev
   ```

2. Initialize Husky:
   ```bash
   npx husky install
   ```

3. Add the post-commit hook using Husky:
   ```bash
   npx husky add .husky/post-commit "bash post-commit"
   ```

4. Make sure the post-commit script is in your project root and is executable:
   ```bash
   chmod +x post-commit
   ```

## Security

- Uses Basic Authentication
- Requires valid MIS credentials
- Communicates over HTTPS

## Support

For any issues or questions, please contact SOFT PYRAMID LLC.

---
Developed by SOFT PYRAMID LLC
