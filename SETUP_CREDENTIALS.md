# SaverBot Setup - Your Credentials

## Your Configuration Ready to Deploy

All your credentials have been gathered and configured. Below are the details you'll need for deployment.

### Required Environment Variables

When deploying to Vercel, add these exact environment variables:

```
NOTION_API_KEY = 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
ANTHROPIC_API_KEY = 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
NOTION_ARTICLES_DB = 2b8fe958e3bf800a9368df51b3ea5c29
NOTION_BOOKS_DB = 2b8fe958e3bf807a8a10f66a621a8836
NOTION_PODCASTS_DB = 2b8fe958e3bf80adbd68f6932d2e2a2a
```

### Database Configuration

| Type | Database ID |
|------|-------------|
| Articles | 2b8fe958e3bf800a9368df51b3ea5c29 |
| Books/PDFs | 2b8fe958e3bf807a8a10f66a621a8836 |
| Podcasts/Videos | 2b8fe958e3bf80adbd68f6932d2e2a2a |

### Deployment Steps

1. **Go to Vercel Dashboard**
   - https://vercel.com/dashboard

2. **Import GitHub Repository**
   - Click "Add New" → "Project"
   - Select "gunjan1982/saverbot-backend"
   - Click "Import"

3. **Configure Environment Variables**
   - Go to "Settings" → "Environment Variables"
   - Copy and paste ALL 5 variables from above
   - Make sure each variable name matches exactly (case-sensitive)

4. **Deploy**
   - Click "Deploy" button
   - Wait for deployment to complete
   - Copy your deployment URL (will be: https://saverbot-backend-[random].vercel.app)

5. **Verify Deployment**
   - Test health endpoint: `https://your-url/api/health`
   - Should return: `{"status":"ok"}`

### Security Notes

⚠️ **Important:**
- Never commit this file to a public repository with real credentials
- These credentials are sensitive - keep them secure
- Use Vercel's environment variables feature to store them safely
- Don't share your API keys with anyone

### Next Steps After Deployment

1. Note your Vercel deployment URL
2. Create browser extension configuration with this URL
3. Test saving an article from your Notion workspace
4. Verify it appears in the correct database (Articles, Books, or Podcasts)

### Support

If you encounter issues:

1. Check Vercel deployment logs
2. Verify all environment variables are set correctly
3. Test credentials in Notion and Anthropic consoles
4. Review DEPLOYMENT_GUIDE.md for troubleshooting

---

**Status:** ✅ Backend ready for deployment
**Repository:** https://github.com/gunjan1982/saverbot-backend
**All Files:** Complete and ready
