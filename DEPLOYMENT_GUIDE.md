# SaverBot Backend - Deployment Guide

## Quick Start Deployment to Vercel

This guide provides step-by-step instructions to deploy the SaverBot backend to Vercel.

### Prerequisites

- Vercel account (free tier)
- GitHub account (already connected to Vercel)
- Node.js installed locally (for CLI method)
- The following credentials ready:
  - Notion API Key
  - Anthropic API Key
  - Notion Database IDs (3 total)

---

## Method 1: Vercel Dashboard (Recommended)

### Step 1: Connect GitHub Repository

1. Go to https://vercel.com/dashboard
2. Click "Add New" → "Project"
3. Select "Import Git Repository"
4. Search for and select `gunjan1982/saverbot-backend`
5. Click "Import"

### Step 2: Configure Project

1. Project Name: `saverbot-backend` (auto-filled)
2. Framework: Select "Other"
3. Root Directory: `.` (default)
4. Build Command: Leave empty (not needed)

### Step 3: Set Environment Variables

Click "Environment Variables" and add these:

```
NOTION_API_KEY = [your_notion_api_key]
ANTHROPIC_API_KEY = [your_anthropic_api_key]
NOTION_ARTICLES_DB = [articles_db_id]
NOTION_BOOKS_DB = [books_db_id]
NOTION_PODCASTS_DB = [podcasts_db_id]
```

### Step 4: Deploy

Click "Deploy" button.

Vercel will automatically:
- Clone your repository
- Install dependencies (npm install)
- Deploy the application
- Provide you with a deployment URL

**Your backend URL will be:** `https://saverbot-backend-[random].vercel.app`

---

## Method 2: Vercel CLI Deployment

### Step 1: Install Vercel CLI

```bash
npm install -g vercel
```

### Step 2: Clone Repository

```bash
git clone https://github.com/gunjan1982/saverbot-backend.git
cd saverbot-backend
```

### Step 3: Deploy

```bash
vercel --prod
```

When prompted:
- Set up and deploy? **Yes**
- Which scope? Select your personal account
- Link to existing project? **No**
- What's your project's name? `saverbot-backend`
- In which directory? `.` (current directory)

### Step 4: Add Environment Variables

After initial deployment:

```bash
vercel env add NOTION_API_KEY
vercel env add ANTHROPIC_API_KEY
vercel env add NOTION_ARTICLES_DB
vercel env add NOTION_BOOKS_DB
vercel env add NOTION_PODCASTS_DB
```

Then redeploy:

```bash
vercel --prod
```

---

## Verifying Deployment

Once deployed, verify your backend is working:

```bash
curl https://saverbot-backend-[your-id].vercel.app/api/health
```

Expected response:
```json
{"status":"ok"}
```

---

## Getting Your Credentials

### Notion API Key
1. Go to https://www.notion.so/profile/integrations
2. Find "SaverBot" integration
3. Copy the "Internal Integration Secret"

### Anthropic API Key
1. Go to https://console.anthropic.com/account/keys
2. Create or copy existing API key

### Database IDs
1. Go to your Notion workspace
2. Open each database (Articles, Books, Podcasts)
3. Extract ID from URL: `https://notion.so/[DATABASE_ID]?v=...`

---

## Troubleshooting

### "Module not found" error
- Run `npm install` locally first
- Push changes to GitHub
- Redeploy from Vercel

### "Environment variable not defined"
- Check spelling of variable names (case-sensitive)
- Verify all 5 variables are set in Vercel dashboard
- Redeploy after adding variables

### API returns 401/403
- Verify Notion API key is correct
- Verify Anthropic API key is correct
- Check database IDs match your Notion setup

---

## Next Steps

After deployment:
1. Copy the Vercel deployment URL
2. Use this URL in your browser extension configuration
3. Test the full workflow: save article → check Notion

---

## Support

For issues:
- Check Vercel logs: https://vercel.com/dashboard
- Review server.js for API implementation
- Verify credentials in Notion and Anthropic consoles
