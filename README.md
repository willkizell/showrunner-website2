# ShowRunner - AI Event Assistant

ShowRunner is an AI-powered event assistant that generates custom playlists, announcements, and provides real-time control for events of all sizes.

## Features

- 🤖 AI-generated event announcements and song suggestions
- 🎵 Custom playlists tailored to event vibe and timeline
- 🎤 Text-to-speech for announcements
- 📱 Real-time event control dashboard
- 🎪 Perfect for corporate events, weddings, parties, and more

## Quick Start

### Prerequisites

- Node.js 18+ 
- OpenAI API key
- Vercel account (for deployment)

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/willkizell/showrunner-site.git
   cd showrunner-site
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp env.example .env.local
   ```
   
   Edit `.env.local` and add your OpenAI API key:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:3000`

### Deployment to Vercel

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   ```

3. **Set environment variables in Vercel dashboard**
   - Go to your project settings
   - Add `OPENAI_API_KEY` with your API key
   - Optionally add `OPENAI_MODEL` to customize the AI model

## API Endpoints

### POST `/api/generate`

Generates event announcements and song suggestions.

**Request Body:**
```json
{
  "prompt": "Your event description and requirements"
}
```

**Response:**
```json
{
  "choices": [
    {
      "message": {
        "content": "Generated announcements and songs..."
      }
    }
  ]
}
```

### POST `/api/generate` (Text-to-Speech)

Converts text to speech for announcements.

**Request Body:**
```json
{
  "text": "Text to convert to speech"
}
```

**Response:** Audio file (MP3)

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `OPENAI_API_KEY` | Your OpenAI API key | Required |
| `OPENAI_MODEL` | OpenAI model to use | `gpt-4o` |

## Project Structure

```
showrunner-site/
├── api/
│   └── generate.js      # API endpoint for AI generation
├── index.html           # Landing page
├── DemoMode.html        # Event planning interface
├── about.html           # About page
├── package.json         # Dependencies and scripts
├── vercel.json          # Vercel deployment config
└── README.md           # This file
```

## Troubleshooting

### API Errors
- Ensure your OpenAI API key is valid and has sufficient credits
- Check that the API key is properly set in your environment variables
- Verify your OpenAI account has access to the required models

### Deployment Issues
- Make sure all environment variables are set in Vercel
- Check that the `vercel.json` configuration is correct
- Ensure all files are committed to git before deploying

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

© 2025 ShowRunner — All rights reserved. 