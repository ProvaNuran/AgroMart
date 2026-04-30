# 🌾 AgroMart

> A weather-aware agricultural e-commerce platform with real-time market insights and data provenance tracking.

---

## 🚀 Features

- 🌦️ **Weather-Aware Pricing** — Product prices and recommendations adjust based on real-time weather data
- 🛒 **Agricultural E-Commerce** — Buy and sell farm products online
- 📊 **Dashboard** — Real-time market insights for farmers and buyers
- 🔍 **Data Provenance Tracking** — Full audit trail of every product and transaction
- 🔐 **Authentication** — Secure login system
- 🗄️ **Supabase Backend** — Cloud database with fallback mock DB for local development

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, Tailwind CSS, Framer Motion |
| Backend | Node.js, Express.js |
| Database | Supabase (PostgreSQL) |
| Build Tool | Vite |

---

## ⚙️ Installation

### Prerequisites
- Node.js 18+
- npm

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/your-username/agromart.git
cd agromart

# 2. Install dependencies
npm install

# 3. Setup environment variables
cp .env.example .env
# Edit .env with your Supabase credentials

# 4. Start the development server
npm run dev
```

---

## 🔑 Environment Variables

Create a `.env` file based on `.env.example`:

```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your-service-role-key
SUPABASE_ANON_KEY=your-anon-key
PORT=3000
```

> ⚠️ Never commit your `.env` file. It contains secret keys.

---

## 📁 Project Structure

```
agromart/
├── src/
│   ├── components/
│   │   ├── Login.jsx
│   │   ├── Dashboard.jsx
│   │   └── Onboarding.jsx
│   ├── App.jsx
│   └── main.jsx
├── public/
│   ├── index.html
│   ├── login.html
│   ├── dashboard.html
│   ├── css/
│   ├── js/
│   └── images/
├── scripts/
├── server.cjs
├── .env.example
└── package.json
```

---

## 📜 Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start full dev server (frontend + backend) |
| `npm run dev:web` | Start Vite frontend only |
| `npm run api` | Start Express backend only |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

---

## 📄 License

This project is for educational purposes.
