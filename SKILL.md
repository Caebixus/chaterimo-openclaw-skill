---
name: chaterimo
description: AI Customer Service for Shopify & E-commerce - Query conversations, analyze chatbot performance, and manage your Chaterimo AI assistant
emoji: 🛒
homepage: https://www.chaterimo.com
tags:
  - shopify
  - ecommerce
  - customer-service
  - chatbot
  - ai-assistant
  - conversations
  - analytics
  - support
metadata:
  clawdis:
    primaryEnv: CHATERIMO_API_KEY
    requires:
      env:
        - CHATERIMO_API_KEY
    config:
      requiredEnv:
        - name: CHATERIMO_API_KEY
          description: Your Chaterimo API key. Generate at https://www.chaterimo.com/account/api-keys/
---

# Chaterimo - AI Customer Service for Shopify & E-commerce

Connect your Chaterimo AI chatbot to OpenClaw. Query customer conversations, analyze chatbot performance, and get insights from your Shopify store's customer service data.

## What is Chaterimo?

Chaterimo is an AI-powered customer service platform that integrates with **Shopify**, Shoptet, WooCommerce, and other e-commerce platforms. It provides 24/7 automated customer support using GPT-4, Claude, and Gemini AI models.

## What can this skill do?

### List Your Chatbots
> "Show me all my chatbots"

Returns all chatbots configured for your store with their AI model settings and status.

### Browse Conversations
> "Show me conversations from last week"
> "List conversations from my Shopify store"

View customer service conversations with filters by date and platform. All customer PII is automatically stripped for privacy.

### Read Conversation Transcripts
> "Show me conversation #123"
> "What did customers ask about yesterday?"

Get full conversation transcripts between customers and your AI chatbot.

## Setup

1. Sign up at [chaterimo.com](https://www.chaterimo.com)
2. Connect your Shopify store (or other e-commerce platform)
3. Go to **API Keys** in your dashboard
4. Click **Create API Key** and copy the key
5. Set the environment variable:
   ```
   CHATERIMO_API_KEY=cha_your_key_here
   ```

## API Endpoints

| Endpoint | Description |
|----------|-------------|
| `GET /api/v1/chatbots/` | List all chatbots |
| `GET /api/v1/chatbots/{id}/` | Get chatbot details |
| `GET /api/v1/chatbots/{id}/conversations/` | List conversations |
| `GET /api/v1/conversations/{id}/` | Get conversation transcript |

## Privacy & Security

- All customer PII (emails, phone numbers, credit cards) is automatically redacted
- API keys use SHA256 hashing - we never store your raw key
- Rate limited to 60 requests/minute per API key
- All API calls are logged for audit purposes

## Supported Platforms

- **Shopify** - Full integration with product sync
- Shoptet
- WooCommerce
- Magento
- PrestaShop
- Custom XML feeds

## Coming Soon (Phase 2+)

- Analytics & metrics dashboard
- Unanswered questions detection
- Product search
- Knowledge base management
- Chatbot configuration via API

## Support

- Website: [chaterimo.com](https://www.chaterimo.com)
- Documentation: [chaterimo.com/docs](https://www.chaterimo.com/en/docs/)

## Example Usage

```
User: Show me my chatbots
Assistant: You have 2 chatbots configured:

1. **Main Store Support** (GPT-4)
   - Language: English
   - Status: Active

2. **Czech Support** (Claude)
   - Language: Czech
   - Status: Active

User: Show me recent conversations from Main Store Support
Assistant: Here are the last 5 conversations:

1. Session #abc123 - 12 messages - Feb 4, 2026
2. Session #def456 - 8 messages - Feb 4, 2026
3. Session #ghi789 - 3 messages - Feb 3, 2026
...
```
