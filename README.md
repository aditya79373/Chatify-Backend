# Chatify Backend

The server for **Chatify**, a real-time chat app. It handles sign-in, real-time messaging, media uploads, email delivery.

The app lives in a separate repository: **Chatify-Frontend**.

## Tech stack

Node.js with Socket.IO for realtime, Supabase (database), Cloudinary (media uploads), Brevo and SMTP email.

## Getting started

### Prerequisites

- Node.js (LTS) and pnpm through corepack (`corepack pnpm ...`)
- A Supabase project (URL and service role key)
- A Cloudinary account (cloud name, API key, API secret)
- A Brevo account (API key and a verified sender email)
- An email account for sending mail (for example a Gmail address with an app password)


### Clone

```bash
git clone https://github.com/aditya79373/Chatify-Backend.git
cd Chatify-Backend
```

### Install and run

```bash
npm install
node server.js
```

### Environment variables

Copy `.env.example` to `.env` and fill in your own values.

| Variable | Purpose |
| --- | --- |
| `EMAIL_USER` | Email account used to send mail |
| `EMAIL_PASS` | Password or app password for that account |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID (same one the frontend uses) |
| `GOOGLE_CLIENT_SECRET` | Google OAuth client secret |
| `CLOUD_NAME` | Cloudinary cloud name |
| `CLOUD_API_KEY` | Cloudinary API key |
| `CLOUD_API_SECRET` | Cloudinary API secret |
| `SUPABASE_URL` | Supabase project URL |
| `SUPABASE_SERVICE_ROLE_KEY` | Supabase service role key (server only, never expose it in the app) |
| `BREVO_API_KEY` | Brevo API key |
| `BREVO_SENDER_EMAIL` | Verified sender address in Brevo |




Never commit `.env` (keep it in `.gitignore`). These values are secrets: anyone who has them can use your database, email and cloud accounts.

## Deployment

1. Create a new web service from this repository (for example on Render).
2. Build command: `npm install`. Start command: `node server.js`.
3. Add every variable from the table above in the service's environment settings.
4. Allow your frontend's URL in the server's CORS settings.
