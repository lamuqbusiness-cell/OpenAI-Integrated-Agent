# OpenAI Integrated Agent - Complete Setup Guide

## Phase 1: Environment Setup (Tomorrow)

### Step 1: Get API Keys
1. **OpenAI API**
   - Go to https://platform.openai.com/api-keys
   - Create new secret key
   - Save as OPENAI_API_KEY

2. **Twitter/X API**
   - Apply at https://developer.twitter.com/
   - Get API Key, Secret, Bearer Token
   - Need Academic or Pro access

3. **Instagram/Facebook Graph API**
   - Go to https://developers.facebook.com/
   - Create app with Instagram Graph API
   - Get Access Token and App ID

4. **LinkedIn API**
   - Visit https://www.linkedin.com/developers/
   - Create organization app
   - Get Client ID and Client Secret

5. **Gmail API**
   - Go to https://console.cloud.google.com/
   - Enable Gmail API
   - Create OAuth 2.0 credentials
   - Download credentials.json

### Step 2: Database Setup
```bash
# PostgreSQL Installation
sudo apt-get install postgresql postgresql-contrib

# Create database
sudo -u postgres createdb agent_db

# Create user
sudo -u postgres createuser agent_user

# Set password
sudo -u postgres psql
ALTER USER agent_user WITH PASSWORD 'secure_password';
GRANT ALL PRIVILEGES ON DATABASE agent_db TO agent_user;
```

### Step 3: Python Environment
```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\\Scripts\\activate

# Install requirements
pip install -r requirements.txt
```

## Phase 2: Configuration

### Create .env File
```env
# OpenAI
OPENAI_API_KEY=sk-your-key-here
OPENAI_MODEL=gpt-5.1

# Twitter API
TWITTER_API_KEY=your-key
TWITTER_API_SECRET=your-secret
TWITTER_BEARER_TOKEN=your-bearer-token

# Instagram/Facebook
INSTAGRAM_ACCESS_TOKEN=your-token
FACEBOOK_APP_ID=your-app-id

# LinkedIn
LINKEDIN_CLIENT_ID=your-client-id
LINKEDIN_CLIENT_SECRET=your-secret

# Gmail
GMAIL_CREDENTIALS_FILE=path/to/credentials.json
GMAIL_TOKEN_FILE=path/to/token.pickle

# Database
DATABASE_URL=postgresql://agent_user:password@localhost/agent_db

# Scheduling
CRON_INTERVAL=3600  # seconds
TIMEZONE=UTC
```

## Phase 3: Database Schema

Will be created in `docs/DATABASE_SCHEMA.md` with:
- Users table
- Social Media Accounts
- Email Messages
- Web Research Results
- Reports
- Logs

## Phase 4: Integration Setup

### Social Media Monitoring
- Twitter: Monitor keywords, hashtags, mentions
- Instagram: Track brand mentions
- LinkedIn: Monitor company activity
- Facebook: Collect page engagement

### Email Processing
- Gmail: Read, parse, categorize
- Outlook: Sync emails
- Extract: Links, attachments, senders

### Web Research
- Search engines
- News aggregation
- Trend analysis

## Phase 5: Agent Configuration

Will be detailed in `docs/AGENT_CONFIG.md`

## Phase 6: Testing

Will be documented in `docs/TESTING.md`

## Phase 7: Deployment

Will be documented in `docs/DEPLOYMENT.md`

---

**Next Steps:** Run setup.sh and begin Phase 1
