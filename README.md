# Purple Assistant BETA

A Microsoft Teams-integrated help desk interface using ElevenLabs conversational AI with Microsoft Graph API integration.

## 🔧 Setup Instructions

### 1. GitHub Secrets Configuration

To securely deploy this application, you need to configure GitHub repository secrets:

1. Go to your GitHub repository → **Settings** → **Secrets and variables** → **Actions**
2. Add the following **Repository secrets**:

```
AZURE_TENANT_ID=31c06606-c23c-4881-8914-439ef1a8a645
AZURE_CLIENT_ID=d6e0f9db-ede1-47ae-8b48-7ac65aac032a
AZURE_CLIENT_SECRET=Buh8Q~YhjtaGADnB6Jt3z.DZCwlIW1SLdtpeCbff
ELEVENLABS_AGENT_ID=agent_4901k3gjds1eexs83j5a7pv4xaaz
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
- **Microsoft Graph API** for rich user profile data
- **ElevenLabs widget** for conversational AI
- **Secure credential management** via GitHub secrets

## 📦 Teams App Versions

- **v1.02** - Original with basic SSO
- **v1.03** - Added Samanage API support
- **v1.04** - Fixed Graph API manifest issues
- **v1.05** - Removed SSO complications
- **v1.06** - Clean version without external dependencies

## 🔒 Security

- Client credentials are injected at build time via GitHub Actions
- No secrets are committed to the repository
- Environment variables provide secure configuration
- Production deployment uses GitHub secrets