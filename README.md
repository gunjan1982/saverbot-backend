# SaverBot Backend API

Backend API for SaverBot - a browser extension that saves articles, PDFs, and videos to Notion with AI-generated summaries.

## Features

- Auto-detect content type (Articles, Books, Podcasts)
- Generate AI summaries using Claude API
- Extract key takeaways
- Save directly to Notion databases
- Support for URLs, PDFs, and video content

## Environment Variables

The following environment variables are required:

- `NOTION_API_KEY`: Your Notion integration API key
- `ANTHROPIC_API_KEY`: Your Anthropic Claude API key
- `NOTION_ARTICLES_DB`: Notion database ID for articles
- `NOTION_BOOKS_DB`: Notion database ID for books/PDFs
- `NOTION_PODCASTS_DB`: Notion database ID for podcasts/videos

## Deployment

This project is configured for deployment on Vercel.

### Via Vercel Dashboard

1. Connect your GitHub repository to Vercel
2. Set environment variables in project settings
3. Deploy automatically on push to main branch

### Via Vercel CLI

```bash
git clone https://github.com/gunjan1982/saverbot-backend.git
cd saverbot-backend
vercel --prod
```

When prompted, add the environment variables.

## API Endpoints

- `POST /api/save` - Save content to Notion
- `GET /api/health` - Health check endpoint

## License

MIT
