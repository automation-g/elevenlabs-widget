# Purple Assistant BETA

A Microsoft Teams-integrated help desk interface using ElevenLabs conversational AI with Microsoft Graph API integration.

## 🔧 Setup Instructions

### 1. GitHub Secrets Configuration

To securely deploy this application, you need to configure GitHub repository secrets:

1. Go to your GitHub repository → **Settings** → **Secrets and variables** → **Actions**
2. Add the following **Repository secrets**:

```
AZURE_TENANT_ID=xxx
AZURE_CLIENT_ID=xxx
AZURE_CLIENT_SECRET=xxx
ELEVENLABS_AGENT_ID=xxx
```

### 2. Local Development

For local development:

1. Copy `.env.example` to `.env`
2. Fill in your actual Azure credentials
3. The `.env` file is ignored by git for security

### 3. Deployment

The application automatically deploys to GitHub Pages when you push to the `main` branch. The GitHub Actions workflow will:

1. Replace credential placeholders with your secrets
2. Deploy to GitHub Pages
3. Keep your credentials secure

## 🏗️ Architecture

- **Single HTML file** with embedded CSS and JavaScript
- **Teams SDK integration** for context and user information
- **Microsoft Graph API** for rich user profile data using client credentials flow
- **ElevenLabs conversational AI widget** for intelligent chat assistance
- **Secure credential management** via GitHub secrets and environment variables
- **Automated deployment** with GitHub Actions

## 📦 Teams App Versions

- **v1.02** - Original with basic SSO authentication
- **v1.03** - Added Samanage API integration support
- **v1.04** - Fixed Graph API manifest configuration issues
- **v1.05** - Removed problematic SSO complications
- **v1.06** - Clean version focused on core Teams functionality

## 🔒 Security Best Practices

- **No secrets in repository** - All credentials managed through GitHub secrets
- **Build-time injection** - Secrets replaced during GitHub Actions deployment
- **Environment variable support** - Local development uses `.env` files (git-ignored)
- **Validation checks** - Application validates configuration before execution
- **Secure by default** - Placeholder system prevents accidental credential exposure

## 🚀 Features

- **Rich user context** - Extracts user information from Teams context and Graph API
- **App version display** - Shows current Teams app manifest version for debugging
- **Comprehensive error handling** - Graceful fallbacks when APIs fail
- **Debug information** - Detailed context data for troubleshooting
- **Responsive design** - Works seamlessly within Microsoft Teams interface