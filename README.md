<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&pause=1000&color=2E8B57&center=true&vCenter=true&width=600&lines=AgroMart;Farm+to+Market%2C+Intelligently." alt="AgroMart" />
# AgroMart

AgroMart is a React + Vite web app for agricultural marketplace/dashboard workflows with a lightweight Express backend and optional Supabase integration.

## Features

- React frontend with Vite
- Tailwind CSS styling
- Express server for page routes and API support
- Supabase-compatible backend integration
- Onboarding and login flow

## Getting Started

### 1. Install dependencies

```powershell
npm install
```

### 2. Configure environment

Copy the sample env file and provide your Supabase values:

```powershell
copy .env.example .env
```

Then update `.env` with:

- `SUPABASE_URL`
- `SUPABASE_SERVICE_KEY`
- `SUPABASE_ANON_KEY` (optional)
- `PORT` (optional)
- `DEBUG` (optional)

### 3. Run locally

Start the web app:

```powershell
npm run dev
```

Start the Express API server:

```powershell
npm run api
```

If you want both web and API together in development, run the `dev` script:

```powershell
npm run dev
```

### 4. Build for production

```powershell
npm run build
```

Preview the production build:

```powershell
npm run preview
```

## Project Structure

- `src/` - React application source files
- `public/` - static HTML, CSS, images, and JavaScript assets
- `server.cjs` - Express backend server
- `scripts/dev.cjs` - development server launcher
- `tailwind.config.js` - Tailwind CSS configuration
- `vite.config.js` - Vite configuration

## Notes

- `node_modules/` is excluded from source control via `.gitignore`
- Use `.env` to keep secrets out of the repo
- The app includes a mock in-memory database when Supabase credentials are not configured

## License

This project is provided as-is.
