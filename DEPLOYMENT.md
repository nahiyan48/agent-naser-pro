# 🚀 Agent Naser PRO — Cloud Deployment Guide (Render.com, GitHub & VPS)

This comprehensive guide walks you through deploying **Agent Naser PRO** to **Render.com**, **Railway.app**, or any **Cloud VPS** in under 5 minutes using GitHub.

---

## 📁 Cloud-Ready Repository Structure

```text
agent-naser-pro/
├── package.json          # Node.js dependencies & start scripts (Express, CORS)
├── server.js             # Production-Ready Node.js Express Backend
├── server.ps1            # Local Windows PowerShell Server
├── render.yaml           # Render.com Blueprint (Zero-Config 1-Click Deploy)
├── netlify.toml          # Netlify Frontend Redirects & Proxy Rules
├── .gitignore            # Git exclusion rules
├── LICENSE               # Commercial Software License
├── README.md             # Project & Benefits Documentation
├── DEPLOYMENT.md         # Deployment Guide
├── data/
│   └── database.json     # Persistent Database (Campaigns, Users, Backlinks, DB)
└── public/
    ├── index.html        # Complete SaaS Dashboard UI
    ├── style.css         # Modern SaaS CSS & Print Styles
    ├── app.js            # Frontend Client Engine & Anti-Theft Protection
    ├── login.html        # Client & Admin Login Portal
    ├── agent_naser.jpg   # Brand Avatar Asset
    └── agent_naser_real.jpg
```

---

## 🌟 Option 1: Deploy on Render.com (Recommended — 100% Free & Fast)

Render automatically detects `package.json` and `render.yaml`.

### Step 1: Upload to GitHub
1. Open [GitHub.com](https://github.com) and create a new repository (e.g. `agent-naser-pro`).
2. Set visibility to **Private** to keep your source code and database safe.
3. Upload all files and folders from the project directly to the repository root.

### Step 2: Deploy on Render.com
1. Sign in to your [Render.com](https://render.com) account.
2. In the Render Dashboard, click the **+ New** button in the top bar.
3. Select **Web Service**.
4. Choose **Build and deploy from a Git repository** and click **Next**.
5. Connect your GitHub account and click **Connect** next to your `agent-naser-pro` repository.
6. Render will auto-fill the configuration:
   - **Name:** `agent-naser-pro`
   - **Region:** Singapore or Frankfurt
   - **Branch:** `main`
   - **Root Directory:** Leave blank
   - **Runtime:** `Node`
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - **Instance Type:** `Free` ($0/month)
7. Click **Deploy Web Service** at the bottom.
8. Within 2–3 minutes, your build will finish and your live URL will be ready:
   👉 `https://agent-naser-pro.onrender.com`

---

## 🌟 Option 2: Deploy on Railway.app

1. Go to [Railway.app](https://railway.app) and sign in with GitHub.
2. Click **New Project** > **Deploy from GitHub repo**.
3. Select your `agent-naser-pro` repository.
4. Railway will automatically execute `server.js` and assign an HTTPS URL.

---

## 🌟 Option 3: Dedicated Ubuntu Cloud VPS (DigitalOcean / Hetzner / AWS EC2)

For heavy workloads with automated browser bots running 24/7:

1. Provision an Ubuntu 22.04/24.04 droplet or server.
2. Install Node.js 20 LTS and PM2:
   ```bash
   curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
   sudo apt-get install -y nodejs
   sudo npm install -g pm2
   ```
3. Clone your repository and install dependencies:
   ```bash
   git clone https://github.com/YOUR_USERNAME/agent-naser-pro.git
   cd agent-naser-pro
   npm install
   ```
4. Start the server continuously with PM2:
   ```bash
   pm2 start server.js --name "agent-naser-pro"
   pm2 startup
   pm2 save
   ```
5. Set up Nginx reverse proxy with free Let's Encrypt SSL:
   ```bash
   sudo apt install -y nginx certbot python3-certbot-nginx
   sudo certbot --nginx -d app.yourdomain.com
   ```

---

## 🔑 Default Login Credentials

| Role | Email | Password | Access Level |
| :--- | :--- | :--- | :--- |
| 👑 **SuperAdmin** | `admin@agentnaser.pro` | `AGENTNASERPRO` | Full access, unlimited AI credits, all 110+ sites unlocked |
| 🎁 **Demo Test User** | `demo@agentnaser.pro` | `AGENT NASER` | 10 Free AI Trial Credits, Prospect Finder |

---

## 🛡️ Core Security & Guardrails

1. **Moz Spam Score < 15% Filter:** Blocks any domain with spam score exceeding 15%.
2. **Authority Baseline (DA 40+ to 96+):** Exclusively targets authoritative white-hat sources.
3. **Daily Velocity Cap (10–25 links/day):** Prevents search engine penalty triggers.
4. **Isolated Outreach Gateway:** Protects client domains through separate dedicated mailboxes.
