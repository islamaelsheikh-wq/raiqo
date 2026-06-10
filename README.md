# RAIQO Demo App
**Regulatory Intelligence Platform — Demo for CIF Proposal**

> ⚠️ All product names, registration numbers, CCF codes, and company data in this app are **entirely fictional** and created for demonstration purposes only.

---

## Quick start (5 steps)

### Step 1 — Clone and install
```bash
git clone <your-repo>
cd raiqo-demo
npm install
```

### Step 2 — Create Firebase project
1. Go to https://console.firebase.google.com
2. Create new project: `raiqo-demo`
3. Enable **Authentication** → Sign-in method → **Email/Password**
4. Enable **Firestore Database** → Start in test mode
5. Go to Project settings → Your apps → Add web app → Copy config

### Step 3 — Configure environment
```bash
cp .env.example .env
# Fill in your Firebase config values
# Set up EmailJS (emailjs.com) and add credentials
# Set up CallMeBot WhatsApp (optional for demo)
```

### Step 4 — Run locally
```bash
npm run dev
# App opens at http://localhost:5173
```

### Step 5 — Seed demo users
1. Open the app → Sign in with Admin user
2. Admin panel → System tab → "Seed demo users to Firebase"
3. All 13 demo users created with password: `Raiqo@2026`

---

## Deploy to Netlify (free)

### Option A: GitHub + Netlify (recommended)
1. Push code to GitHub
2. Go to https://netlify.com → New site from Git
3. Connect your repo → Build command: `npm run build` → Publish dir: `dist`
4. Site settings → Environment variables → Add all VITE_* vars from your .env
5. Deploy → Get public URL like `raiqo-demo.netlify.app`

### Option B: Netlify CLI
```bash
npm install -g netlify-cli
netlify login
npm run build
netlify deploy --prod --dir dist
```

---

## Demo credentials

| User ID | Role | Password |
|---------|------|----------|
| ADMIN-001 | App Admin | Raiqo@2026 |
| RM-001 | RA Manager | Raiqo@2026 |
| RO-001 | RA Officer | Raiqo@2026 |
| QM-001 | QA Manager | Raiqo@2026 |
| QO-001 | QA Officer | Raiqo@2026 |
| RD-001 | Regulatory Director | Raiqo@2026 |
| SC-001 | Supply Chain | Raiqo@2026 |
| EX-001 | Executive | Raiqo@2026 |

> All users must change their password on first login.

---

## WhatsApp notifications setup (CallMeBot — free)

1. From the phone you want to receive WhatsApp alerts, send this message to **+34 644 60 49 16**:
   ```
   I allow callmebot to send me messages
   ```
2. Wait for their reply — it will contain your personal API key
3. Add to `.env`:
   ```
   VITE_DEMO_WA_PHONE=971501234567  (your number, no + sign)
   VITE_DEMO_WA_APIKEY=xxxxxxxx
   ```
4. In Admin panel → User management → Click "Configure" next to any user to add their WhatsApp

---

## Email notifications setup (EmailJS — free, 200 emails/month)

1. Create account at https://emailjs.com
2. Email services → Add service → Gmail → Connect your Gmail
3. Email templates → Create template with these variables:
   - `{{to_email}}` — recipient
   - `{{to_name}}` — recipient name
   - `{{subject}}` — email subject
   - `{{message}}` — main message
   - `{{product_name}}`, `{{market}}`, `{{event_type}}`, `{{timestamp}}`
4. Copy Service ID, Template ID, and Public Key to `.env`

---

## Tech stack (all free)

| Layer | Technology | Cost |
|-------|-----------|------|
| Frontend | React 18 + Vite | Free |
| Database | Firebase Firestore | Free (Spark plan) |
| Auth | Firebase Authentication | Free |
| Hosting | Netlify | Free |
| Email | EmailJS | Free (200/month) |
| WhatsApp | CallMeBot | Free |

---

## App screens

1. **Sign in** — User ID + password
2. **Change password** — Forced on first login
3. **Dashboard** — Interactive world map + KPIs + alerts
4. **Registrations** — All product registrations across markets
5. **RA Updates** — Regulatory update entry (replaces Emerson email)
6. **Variations** — Post-approval changes tracker
7. **Batch release gate** — Pre-release compliance check engine
8. **Vendors** — Approved vendor list
9. **Notifications** — Alert centre + email/WhatsApp test
10. **Reports** — Compliance charts and KPIs
11. **Admin panel** — User management, roles, WhatsApp config

---

*RAIQO Demo v1.0 · Fictional data only · Built for CIF proposal presentation*
