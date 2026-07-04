
[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/new?repository-url=https%3A%2F%2Fgithub.com%2Fyour-username%2Fairport-ai-assistant)



### Deploy to Vercel (Recommended)
```bash
# 1. Fork this repo
# 2. Go to vercel.com
# 3. Import GitHub repo
# 4. Add ANTHROPIC_API_KEY environment variable
# 5. Click Deploy
```

### Deploy to Render
```bash
# 1. Go to render.com
# 2. New Web Service
# 3. Connect GitHub repo
# 4. Add ANTHROPIC_API_KEY
# 5. Deploy
```

### Deploy to Railway
```bash
# 1. Go to railway.app
# 2. New Project from GitHub
# 3. Select repo
# 4. Set ANTHROPIC_API_KEY
# 5. Auto-deploys
```

[ Full Deployment Guide](./DEPLOYMENT_GUIDE.md)

---

##  Features

-  **AI-Powered**: Uses Claude 3.5 Sonnet for intelligent responses
-  **Real-time Chat**: WebSocket-based messaging system
-  **Responsive**: Works on mobile, tablet, desktop
-  **Secure**: API keys protected via environment variables
-  **Fast**: <3 second response times
-  **Deployed**: Live in minutes on any platform

---

## Architecture

```
Frontend (index.html)
    ↓
Express Server (server.js)
    ↓
Anthropic API
    ↓
Claude 3.5 Sonnet
    ↓
Response back to user
```

---

## 📋 Project Structure

```
airport-ai-assistant/
├── 📄 index.html              # Frontend chatbot UI
├── 🖥️  server.js              # Express backend API
├── 📦 package.json            # Node.js dependencies
├── 🔑 .env.example            # Environment template
├── ⚙️  vercel.json            # Vercel config
├── 🎯 render.yaml             # Render config
├── 📚 DEPLOYMENT_GUIDE.md     # Step-by-step deployment
├── 🔗 GITHUB_README.md        # This file
└── 📋 README.md               # Project documentation
```

---

## 🚀 Get Started

### Prerequisites
- Node.js 16+
- Anthropic API Key (free at [console.anthropic.com](https://console.anthropic.com))
- Git

### Local Setup

1. **Clone the repo**
   ```bash
   git clone https://github.com/YOUR_USERNAME/airport-ai-assistant.git
   cd airport-ai-assistant
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment**
   ```bash
   cp .env.example .env
   # Edit .env and add your ANTHROPIC_API_KEY
   ```

4. **Run locally**
   ```bash
   npm start
   # Visit http://localhost:3000
   ```

5. **Development mode** (with auto-reload)
   ```bash
   npm run dev
   ```

---

## 🌐 Deploy to Production

### Vercel
1. Sign in to [vercel.com](https://vercel.com) with GitHub
2. Click "New Project"
3. Select this repository
4. Add `ANTHROPIC_API_KEY` environment variable
5. Click "Deploy"

✅ **Live at**: `https://your-app.vercel.app`


---

## 🔧 Environment Variables

Create a `.env` file (copy from `.env.example`):

```env
ANTHROPIC_API_KEY=sk_your_api_key_here
PORT=3000
NODE_ENV=production
```

**Never commit `.env` to GitHub!** Use platform secrets instead:
- **Vercel**: Settings → Environment Variables
- **Render**: Environment → Environment Variables
- **Railway**: Variables
- **Fly.io**: `flyctl secrets set`

---

## 📊 API Endpoints

### Chat Endpoint
```bash
POST /api/chat
Content-Type: application/json

{
  "message": "Where is Terminal A?"
}
```

**Response**:
```json
{
  "reply": "Terminal A is located on the east side of the airport...",
  "messageId": "msg_123456"
}
```

### Health Check
```bash
GET /health
```

---

##  Use Cases

-  Regional airport passenger support
-  Flight information queries
-  Wayfinding and directions
-  Airport services inquiries
-  Ground transportation help
-  Multi-language support (customizable)

---

##  Scaling

| Stage | Platform | Cost | Capacity |
|-------|----------|------|----------|
| MVP | Vercel Free | $0 | 100 req/day |
| Pilot | Render | $7/mo | 750 hrs/mo |
| Production | Vercel Pro | $20/mo | Unlimited |
| Enterprise | AWS/GCP | $1000+ | Custom |

---

##  Security

- API keys stored in environment variables
- `.env` file in `.gitignore`
- No secrets in source code
- CORS enabled for deployment platforms
- Rate limiting (platform-dependent)

---

## 🐛 Troubleshooting

### "Cannot find module 'express'"
```bash
npm install
```

### "API key not found"
Check your platform's environment variables. Don't use local `.env` file.

### "Port already in use"
```bash
PORT=3001 npm start
```

### "CORS errors"
Check that your frontend URL matches the backend CORS configuration.

[Full troubleshooting guide →](./DEPLOYMENT_GUIDE.md#-troubleshooting)

---

## 📚 Documentation

- [Deployment Guide](./DEPLOYMENT_GUIDE.md) - Step-by-step deployment instructions
- [Project README](./README.md) - Full project documentation
- [Anthropic Docs](https://docs.anthropic.com) - API documentation

---



##  Ready to Deploy?

1. **[Fork this repo](https://github.com/YOUR_USERNAME/airport-ai-assistant/fork)**
2. **[Get your API key](https://console.anthropic.com)**
3. **[Follow deployment guide](./DEPLOYMENT_GUIDE.md)**
4. **[Deploy in 5 minutes](https://vercel.com/new)**


