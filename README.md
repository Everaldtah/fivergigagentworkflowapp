# Fiverr Gig Agent Workflow App

An automated n8n workflow that processes Fiverr orders and generates SEO articles with AI-powered quality checks and human approval via Telegram.

## Overview

This workflow streamlines content creation for Fiverr gigs by:
- Automatically monitoring incoming Fiverr order emails
- Extracting order requirements
- Generating SEO-optimized articles via API
- Running AI quality checks on generated content
- Sending Telegram notifications for human approval
- Waiting for approval before finalizing delivery

## Workflow Steps

1. **Monitor Fiverr Emails** - Polls Gmail every 5 minutes for emails from `fiverr.com`
2. **Workflow Configuration** - Sets up API endpoints and Telegram chat ID
3. **Extract Order Requirements** - Parses email content to extract order details
4. **Generate SEO Article via API** - Sends brief to article generation API
5. **AI Quality Check** - Reviews and improves article using OpenAI (GPT-5-mini)
6. **Prepare Telegram Message** - Formats notification with quality score and preview
7. **Send Telegram Notification** - Sends article preview to Telegram
8. **Wait for Human Approval** - Waits up to 24 hours for APPROVE/REWRITE response

## Requirements

- **n8n** - Workflow automation platform
- **Gmail Account** - With OAuth2 credentials for email monitoring
- **OpenAI API** - For AI quality checks (GPT-5-mini)
- **Telegram Bot** - For notifications and approval workflow
- **Article Generation API** - Your SEO article generation endpoint

## Setup

1. **Import the Workflow**
   - Open n8n and import `Fiverr Order to AI Article Generator with Telegram Approval.json`

2. **Configure Credentials**
   - Gmail OAuth2 account
   - OpenAI API key
   - Telegram API token

3. **Set Workflow Variables**
   - `api_endpoint` - Your article generation API endpoint
   - `telegram_chat_id` - Your Telegram chat ID for notifications

4. **Activate the Workflow**
   - Toggle the workflow to active status

## Usage

Once activated:
1. New Fiverr orders will trigger automatically via email monitoring
2. Articles are generated and quality-checked
3. You'll receive a Telegram notification with:
   - Order details
   - Quality score (1-10)
   - Article preview (first 500 characters)
   - SEO keywords and improvement suggestions
4. Reply to the Telegram message with:
   - `APPROVE` - Accept the article
   - `REWRITE` - Request changes

## Workflow File

- `Fiverr Order to AI Article Generator with Telegram Approval.json` - Complete n8n workflow definition

## License

This project is open source and available for personal and commercial use.

## Support

For issues or questions, please open an issue in the GitHub repository.
