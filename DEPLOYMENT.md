# 🚀 Agent Naser PRO — Deployment Guide (Render.com, GitHub & VPS)

এই নির্দেশিকাটি অনুসরণ করে আপনি খুব সহজেই **Agent Naser PRO** সম্পূর্ণ প্ল্যাটফর্মটিকে GitHub-এ আপলোড করে **Render.com**, **Railway.app** অথবা যেকোনো **Cloud VPS**-এ ৫ মিনিটে লাইভ করতে পারবেন।

---

## 📁 প্রজেক্টের ফাইল স্ট্রাকচার (Cloud Ready)

```
backlink-agent/
├── package.json          # Node.js dependencies & scripts (Express, CORS)
├── server.js             # Production-Ready Node.js Express Server
├── server.ps1            # Local Windows PowerShell Server (Zero-install)
├── render.yaml           # Render.com Blueprint (1-Click Zero Config Deploy)
├── netlify.toml          # Netlify Frontend Redirects
├── .gitignore            # Git exclusion rules
├── data/
│   └── database.json     # Persistent database (Campaign, Users, Links, Tasks)
├── public/
│   ├── index.html        # Complete SaaS Dashboard UI
│   ├── style.css         # Modern SaaS CSS & Print styles
│   ├── app.js            # Frontend Orchestration & API Connector
│   ├── login.html        # Client & Admin Login Portal
│   └── agent_naser.jpg   # Agent Naser Avatar Asset
└── README.md
```

---

## 🌟 অপশন ১: Render.com এ ৫ মিনিটে লাইভ করার নিয়ম (১০০% ফ্রি ও সহজ)

[Render.com](https://render.com) এ আমাদের দেওয়া `render.yaml` এবং `package.json` স্বয়ংক্রিয়ভাবে ডিটেক্ট হয়।

### ধাপ ১: কোড GitHub-এ আপলোড করুন
1. আপনার ব্রাউজারে **[GitHub.com](https://github.com)** এ যান এবং একটি নতুন রিপোজিটরি তৈরি করুন (যেমন: `agent-naser-pro`)।
2. যদি আপনার কম্পিউটারে Git ইনস্টল করা থাকে:
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Agent Naser PRO SaaS"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/agent-naser-pro.git
   git push -u origin main
   ```
   *(যদি Git না থাকে, তাহলে **GitHub Desktop** অ্যাপ ব্যবহার করুন অথবা GitHub পেজের **"uploading an existing file"** বাটনে ক্লিক করে পুরো ফোল্ডারের ফাইলগুলো টেনে ছেড়ে দিন।)*

### ধাপ ২: Render.com এ ডিপ্লয় করুন
1. **[Render.com](https://render.com)** এ ফ্রি একাউন্ট খুলুন (বা GitHub দিয়ে লগইন করুন)।
2. ড্যাশবোর্ডে গিয়ে **"New +"** বাটনে ক্লিক করে **"Web Service"** সিলেক্ট করুন।
3. আপনার GitHub একাউন্ট কানেক্ট করে **`agent-naser-pro`** রিপোজিটরি সিলেক্ট করুন।
4. Render নিজে থেকেই সব কনফিগারেশন নিয়ে নিবে:
   - **Name:** `agent-naser-pro`
   - **Environment:** `Node`
   - **Region:** Singapore / Frankfurt
   - **Branch:** `main`
   - **Build Command:** `npm install`
   - **Start Command:** `npm start` (অথবা `node server.js`)
   - **Plan:** `Free` (বা Starter)
5. নিচে **"Deploy Web Service"** বাটনে ক্লিক করুন।
6. ৩-৪ মিনিটের মধ্যে বিল্ড সম্পন্ন হবে এবং Render আপনাকে একটি লাইভ পাবলিক ইউআরএল দিবে:
   👉 **`https://agent-naser-pro.onrender.com`**

🎉 **অভিনন্দন! আপনার প্ল্যাটফর্ম সারা বিশ্বের জন্য লাইভ হয়ে গেছে!**

---

## 🌟 অপশন ২: Railway.app এ লাইভ করার নিয়ম

1. **[Railway.app](https://railway.app)** এ যান এবং GitHub দিয়ে লগইন করুন।
2. **"New Project"** -> **"Deploy from GitHub repo"** সিলেক্ট করুন।
3. আপনার রিপোজিটরি নির্বাচন করুন।
4. Railway স্বয়ংক্রিয়ভাবে `server.js` ফাইলটি রান করে লাইভ ইউআরএল তৈরি করে দিবে।

---

## 🌟 অপশন ৩: ক্লাউড ভিপিএস (DigitalOcean / Hetzner / AWS EC2) — কমার্শিয়াল SaaS এর জন্য

একটি কমার্শিয়াল SaaS-এর ক্ষেত্রে যেখানে শত শত ইউজার স্বয়ংক্রিয় ব্রাউজার বট (Playwright Bot) রান করবে, সেখানে Ubuntu VPS ব্যবহার করা সবচেয়ে নির্ভরযোগ্য:

1. Ubuntu 22.04/24.04 সার্ভার তৈরি করুন ($৪-$৫/মাস)।
2. সার্ভারে লগইন করে Node.js ও PM2 ইনস্টল করুন:
   ```bash
   curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
   sudo apt-get install -y nodejs
   sudo npm install -g pm2
   ```
3. রিপোজিটরি ক্লোন করুন এবং ডিপেন্ডেন্সি ইনস্টল করুন:
   ```bash
   git clone https://github.com/YOUR_USERNAME/agent-naser-pro.git
   cd agent-naser-pro
   npm install
   ```
4. PM2 দিয়ে সার্ভার ২৪/৭ ব্যাকগ্রাউন্ডে চালু রাখুন:
   ```bash
   pm2 start server.js --name "agent-naser-pro"
   pm2 startup
   pm2 save
   ```
5. Nginx রিভার্স প্রক্সি এবং Certbot দিয়ে ফ্রি SSL (HTTPS) সেট করুন:
   ```bash
   sudo apt install -y nginx certbot python3-certbot-nginx
   sudo certbot --nginx -d app.yourdomain.com
   ```

---

## 🔑 ডিফল্ট লগইন ক্রিডেনশিয়ালস

| রোল | ইমেইল | পাসওয়ার্ড | অ্যাক্সেস |
| :--- | :--- | :--- | :--- |
| 👑 **SuperAdmin** | `admin@agentnaser.pro` | `AGENTNASERPRO` | আনলিমিটেড ১০০টি ডুফলো সাইট, ক্রেডিট লিমিটহীন, সমস্ত ইউজার ডাটা |
| 🎁 **Demo Test User** | `demo@agentnaser.pro` | `AGENT NASER` | ১০টি ফ্রি ট্রায়াল ক্রেডিট, ডুফলো নিচ ফাইন্ডার, পেওয়াল টেস্ট |

---

## 🛡️ প্রধান সিকিউরিটি ও স্প্যাম ফিল্টার রুলস

1. **Moz Spam Score < 15%:** ১৫% এর বেশি স্প্যাম স্কোর থাকা কোনো সাইট প্ল্যাটফর্মে এন্ট্রি পাবে না।
2. **Minimum DA 40+ to 96+:** শুধুমাত্র হাই-অথরিটি সাইটে ব্যাকলিংক তৈরি হবে।
3. **Daily Limit Safeguard (10-25/day):** গুগল স্প্যাম ব্রেইন পেনাল্টি এড়াতে ধীর ও স্বাভাবিক গতিতে ব্যাকলিংক তৈরি করা হয়।
4. **Isolated Outreach Mailbox:** ক্লায়েন্টের মূল বিজনেস ডোমেইন রক্ষা করতে আইসোলেটেড ডোমেইনে SPF, DKIM, DMARC সহ যোগাযোগ করা হয়।
