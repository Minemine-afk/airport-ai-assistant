# Setting Up GitHub Repository

Complete guide for creating and pushing your Airport AI Assistant to GitHub.

---

## Step 1: Create GitHub Repository

### On GitHub.com

1. **Go to [github.com/new](https://github.com/new)**
2. **Enter repository name**: `airport-ai-assistant`
3. **Add description**: `AI-powered chatbot for regional airport passenger support`
4. **Choose settings**:
   -  Public (so anyone can deploy it)
   -  Add README.md
   -  Add .gitignore (Node)
5. **Click "Create repository"**

---

## Step 2: Clone to Your Computer

```bash
git clone https://github.com/YOUR_USERNAME/airport-ai-assistant.git
cd airport-ai-assistant
```

---

## Step 3: Add Project Files

Copy these files from the deployment guide to your cloned repo:

```
airport-ai-assistant/
├── index.html
├── server.js
├── package.json
├── .env.example
├── .gitignore
├── vercel.json
├── render.yaml
├── DEPLOYMENT_GUIDE.md
├── GITHUB_README.md
└── README.md
```

---

## Step 4: Initialize Git & Push

### First time setup:

```bash
# Navigate to your project
cd airport-ai-assistant

# Check status
git status

# Add all files
git add .

# Commit changes
git commit -m "Initial commit: Airport AI Assistant with deployment configs"

# Push to GitHub
git push origin main
```

If you get an error about "main" branch, try:
```bash
git push origin master
```

---

## Step 5: Verify on GitHub

1. **Go to your repo**: `github.com/YOUR_USERNAME/airport-ai-assistant`
2. **You should see all files listed**
3. **README should display** (with Vercel deploy button)

\ **Success!** Your repo is ready to deploy.

---

## Deploy

### Option A: Deploy to Vercel (Recommended)

1. **Go to [vercel.com](https://vercel.com)**
2. **Click "New Project"**
3. **Click "Import Git Repository"**
4. **Select your GitHub repo**
5. **Add environment variables**:
   - `ANTHROPIC_API_KEY` = your API key
6. **Click "Deploy"**

 **Live!** The app is deployed at `https://your-app.vercel.app`


---

## Update Your GitHub Repository

After deploying, update your repo:

### Edit README.md

```bash
# After you deploy, get your live URL
# Then update GITHUB_README.md with your actual URL

# Example changes:
# - Replace "YOUR_USERNAME" with your actual username
# - Add your live deployment URL
# - Update any customizations

git add GITHUB_README.md
git commit -m "Update with deployment URL"
git push origin main
```

---

##  GitHub Workflow

### After you make changes:

```bash
# Make your changes to files
nano index.html  # or any file

# Check what changed
git status

# Add changes
git add .

# Commit with descriptive message
git commit -m "Add multilingual support"

# Push to GitHub
git push origin main
```

### Automatic Deployment (Optional)

If you set up GitHub Actions (`.github/workflows/deploy.yml`):
- Every push to `main` auto-deploys to Vercel 


No additional steps needed!

---

## GitHub Features to Use

### 1. Releases
```bash
git tag -a v1.0.0 -m "First production release"
git push origin v1.0.0
```

Then on GitHub → Releases, create release notes.

### 2. Issues
Use GitHub Issues to track:
- Feature requests
- Bug reports
- Deployment issues

### 3. Branches
```bash
# Create feature branch
git checkout -b feature/multilingual-support

# Make changes
git add .
git commit -m "Add Spanish and Mandarin support"

# Push feature branch
git push origin feature/multilingual-support

# Create Pull Request on GitHub
# Review → Merge to main
```

### 4. GitHub Pages (Optional - for docs)
```bash
# Enable in Settings → Pages → Deploy from main /docs folder
# Create /docs folder with documentation
```

---

##  Protecting Your Repository

### In GitHub Settings:

1. **Go to Settings → Security**
2. **Enable "Require status checks"** (if using CI/CD)
3. **Enable "Dismiss stale reviews"**
4. **Require code review** before merging PRs

---

##  Troubleshooting

### "fatal: not a git repository"
```bash
git init  # Initialize git in the folder
git remote add origin https://github.com/YOUR_USERNAME/airport-ai-assistant.git
```

### "fatal: Authentication failed"
Use a personal access token instead of password:
1. Go to Settings → Developer settings → Personal access tokens
2. Generate new token
3. Use token as password when pushing

### "Your branch is ahead of 'origin/main'"
```bash
git push origin main
```

### Files appear in .gitignore but still tracked
```bash
git rm --cached .env
git commit -m "Remove .env from tracking"
git push origin main
```

---

##  Next Steps

1.  Create GitHub repo
2.  Push your code
3.  Deploy to Vercel/Render
4.  Test live deployment
5.  Share your repo link!

---

##  You're Ready!

Your GitHub repo is now:
-  Version controlled
-  Deployable with one click
-  Shareable with the world
-  Ready for collaboration

**Share your repo**: `https://github.com/YOUR_USERNAME/airport-ai-assistant`

---

**Questions?**
- GitHub Docs: https://docs.github.com
- Git Help: https://git-scm.com/doc
- Vercel GitHub: https://vercel.com/docs/git
