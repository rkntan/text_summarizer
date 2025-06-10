# Text Summarizer App

A web application that summarizes text using Anthropic's Claude AI model. This project was created as part of my learning journey with Scrimba, implementing a frontend with Vite and a Cloudflare Worker backend. The app allows users to input text and receive AI-powered summaries using Claude's advanced language capabilities.

## Prerequisites
- Node.js and npm installed
- Cloudflare account
- Anthropic API key
- Basic knowledge of JavaScript

## Important Note ⚠️
Before running the application, ensure you have:
1. An Anthropic API key with sufficient credit balance
2. If you see the error "Your credit balance is too low", please visit [Anthropic's website](https://www.anthropic.com/) to upgrade or purchase credits

## Getting Started

### Frontend Setup
1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies and start the development server:
```bash
npm install
npm start
```

The frontend will be available at `http://localhost:5173`

### Backend Setup
1. Create a new Cloudflare Worker project:
```bash
npm create cloudflare@latest worker
cd worker
```

2. Install the Anthropic AI SDK:
```bash
npm install @anthropic-ai/sdk@0.24.3
```

3. Configure your Anthropic API key (you will be prompted to enter your key):
```bash
npx wrangler secret put ANTHROPIC_API_KEY
```

4. Deploy the worker to Cloudflare:
```bash
npm run deploy
```

After deployment, you'll receive a URL for your worker (e.g., `https://your-worker.your-subdomain.workers.dev`)

## Project Structure
```
├── frontend/               # Frontend application
│   ├── index.html         # Main HTML file
│   ├── index.js           # Main JavaScript file
│   ├── index.css          # Styles
│   └── images/            # Static assets
├── backend/
│   └── worker/            # Cloudflare Worker
│       ├── src/           # Worker source code
│       └── test/          # Worker tests
```

## Technologies Used
- Frontend: 
  - Vite (for fast development and building)
  - HTML, CSS, JavaScript
  - Loading spinner for better UX
- Backend: 
  - Cloudflare Workers (serverless platform)
  - Anthropic Claude AI API
  - Vitest for testing

## Features
- Text input for long-form content
- AI-powered text summarization
- Responsive design
- Loading state indication
- Error handling for API issues

## Example Usage

Here's a sample text you can use to test the summarizer:

```text
Whatever this is that I am, it is a little flesh and breath, and the ruling part. Throw away thy books; no longer distract thyself: it is not allowed; but as if thou wast now dying, despise the flesh; it is blood and bones and a network, a contexture of nerves, veins, and arteries. See the breath also, what kind of a thing it is, air, and not always the same, but every moment sent out and again sucked in. The third then is the ruling part: consider thus: Thou art an old man; no longer let this be a slave, no longer be pulled by the strings like a puppet to unsocial movements, no longer either be dissatisfied with thy present lot, or shrink from the future.
```

To use:
1. Copy the text above
2. Navigate to `http://localhost:5173` in your browser
3. Paste the text into the input field
4. Click the "Summarize" button
5. Wait for the AI-powered summary to appear

## Development
- Frontend runs on Vite's development server with hot module replacement
- Backend can be tested locally using `wrangler dev`
- Tests can be run using `npm test`

## Troubleshooting
- If you encounter API errors, check your Anthropic API key balance
- For local development issues, ensure all dependencies are installed
- Check the Cloudflare Workers dashboard for deployment status

