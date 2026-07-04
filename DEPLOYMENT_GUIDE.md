#  Airport AI Assistant - GitHub Deployment Guide

Yes! This entire project is **ready to deploy from GitHub** in just a few clicks. Choose your platform and follow the steps below.

##  Platform Comparison

| Platform | Cost | Setup Time | Best For | Free Tier |
|----------|------|-----------|----------|-----------|
| **Vercel** | $0-20/mo | 2 mins | Full-stack apps | Yes, 100 requests/day |
| **Render** | $0-7/mo | 3 mins | Node.js backend | Yes, 750 hours/mo |
| **Railway** | Pay as you go | 3 mins | Docker-friendly | Yes, $5/month free |
| **Fly.io** | $0-10/mo | 5 mins | Global deployment | Yes, 3 shared-cpu-1x VMs |
| **GitHub Pages** | Free | 5 mins | Frontend only | Unlimited |
| **AWS** | Variable | 10 mins | Enterprise | Yes, 12 months free |

---

##  Quick Start (5 minutes)

### **Option 1: Deploy to Vercel** (Recommended - Easiest)

1. **Fork the repository** (or create your own)
   ```bash
   git clone https://github.com/YOUR_USERNAME/airport-ai-assistant.git
   ```

2. **Go to [vercel.com](https://vercel.com)** and sign in with GitHub

3. **Click "New Project"** and select your repository

4. **Configure environment variables**:
   - Click "Environment Variables"
   - Add `ANTHROPIC_API_KEY` = your API key from [Anthropic Console](https://console.anthropic.com)

5. **Click "Deploy"** 
   - The app is live at `https://your-project.vercel.app`

**Vercel Dashboard**: https://vercel.com/dashboard

---


##  Local Development Setup

### Prerequisites
- Node.js 16+ ([Download](https://nodejs.org/))
- Git ([Download](https://git-scm.com/))
- Anthropic API Key ([Get one](https://console.anthropic.com))

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/airport-ai-assistant.git
   cd airport-ai-assistant
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create `.env` file** (copy from `.env.example`)
   ```bash
   cp .env.example .env
   ```

4. **Add your API key** to `.env`
   ```bash
   ANTHROPIC_API_KEY=sk_your_actual_key_here
   ```

5. **Start the server**
   ```bash
   npm start
   ```

6. **Open in browser**
   ```
   http://localhost:3000
   ```

### Development Mode (with auto-reload)
```bash
npm run dev
```

---

##  Getting an Anthropic API Key

1. **Go to [console.anthropic.com](https://console.anthropic.com)**
2. **Sign up or log in**
3. **Click "API Keys" in the sidebar**
4. **Click "Create Key"**
5. **Copy your key** (starts with `sk_`)
6. **Paste into deployment platform** (never commit to git!)

---

##  File Structure

```
airport-ai-assistant/
├── index.html              # Frontend (chatbot UI)
├── server.js               # Backend (Node.js API)
├── package.json            # Dependencies
├── .env.example            # Environment template
├── vercel.json             # Vercel config
├── render.yaml             # Render config
├── .github/workflows/      # CI/CD pipelines
├── README.md               # Project docs
└── DEPLOYMENT_GUIDE.md     # This file
```

---

##  Troubleshooting

### Issue: "API key not found"
**Solution**: Make sure `ANTHROPIC_API_KEY` is set in your platform's environment variables, not just locally.

### Issue: "Cannot GET /"
**Solution**: Make sure your Node.js server is running and listening on the correct port.

### Issue: "CORS error"
**Solution**: Vercel and Render automatically handle CORS. If self-hosting, check `server.js` CORS configuration.

### Issue: "Timeout after 30 seconds"
**Solution**: Some free tiers have limits. Upgrade to a paid plan or use a different platform.

### Issue: Static files not found
**Solution**: Vercel/Render need to know `index.html` is your static file. Check config files above.

---

## Monitoring & Logs

### Vercel
- View logs: Dashboard → Deployments → Select deployment → Functions

---

## 🔄 CI/CD (Automated Deployment)

The project includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that:
-  Runs tests on every push
-  Auto-deploys to Vercel on main branch
-  Auto-deploys to Render on deployment branch

To enable:
1. Go to **Settings → Secrets and variables**
2. Add required secrets:
   - `VERCEL_TOKEN` (from Vercel account)
   - `VERCEL_ORG_ID` (from Vercel account)
   - `VERCEL_PROJECT_ID` (auto-created by Vercel)
   - `ANTHROPIC_API_KEY` (your API key)

---
## Additional Resources

- **Anthropic Docs**: https://docs.anthropic.com
- **Vercel Docs**: https://vercel.com/docs
- **Render Docs**: https://render.com/docs
- **Node.js Guide**: https://nodejs.org/en/docs/

---

## Next Steps

1. **Fork this repository** on GitHub
2. **Choose a platform** above
3. **Get your Anthropic API key**
4. **Deploy in 5 minutes** 
5. **Share your live link!**

---

## Need Help?

- **Documentation**: See README.md
- **API Issues**: Check Anthropic docs at https://docs.anthropic.com
- **Deployment Issues**: Check your platform's support
- **Code Issues**: Open a GitHub issue

---

**Status**: Ready for production deployment  
**Last Updated**: 2026-07-04
