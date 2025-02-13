# Git Activity Tracking Hook

A cross-platform Git hook implementation that automatically tracks developer activity and sends it to a centralized monitoring system.

## Overview

This repository contains a post-commit hook that tracks developer activities across Windows, macOS, and Linux platforms. The hook captures essential information about commits and reports them to a Laravel-based API endpoint.

## Requirements

- Git (any recent version)
- Either curl or wget installed
- Bash shell (Git Bash on Windows)

## Setup

1. Copy the post-commit hook to your repository's hooks directory:
   ```bash
   cp post-commit .git/hooks/
   ```

2. Set proper permissions (Unix/Linux/macOS):
   ```bash
   chmod +x .git/hooks/post-commit
   ```

3. Configure your MIS credentials in the post-commit hook:
   ```bash
   AUTH_USER="your.email@softpyramid.com"
   AUTH_PASS="your-mis-password"
   ```

## Platform Compatibility

The hook works across:
- Windows (including Git Bash, Cygwin, MSYS2)
- macOS
- Linux
- Unix-like systems

## Tracked Information

The hook tracks:
- Developer name and email
- Repository URL
- Branch name
- Commit URL
- Commit message
- Activity type
- Platform information

## API Endpoint

The hook sends data to:
https://mis.softpyramid.com.pk/api/log-activity

## Using with Husky

1. Install Husky:
   ```bash
   npm install husky --save-dev
   ```

2. Initialize Husky:
   ```bash
   npx husky install
   ```

3. Add the post-commit hook:
   ```bash
   npx husky add .husky/post-commit "bash post-commit"
   ```

## Troubleshooting

### Windows Users
- Ensure Git Bash is installed
- Use forward slashes (/) in paths
- Check if curl/wget is accessible

### Unix/Linux/macOS Users
- Verify execute permissions
- Ensure bash is available at /usr/bin/env bash

## Security

- Uses Basic Authentication
- Requires valid MIS credentials
- Communicates over HTTPS
- Handles sensitive data safely

## Support

For any issues or questions, please contact SOFT PYRAMID LLC.

---
Developed by SOFT PYRAMID LLC
