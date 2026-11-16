# BizRecall

Customer retention and rebooking platform for small and medium businesses.

## Technology
- Next.js + TypeScript
- Tailwind CSS v4 and shadcn-inspired components
- Supabase PostgreSQL, Auth and Storage
- Cloudflare Workers using OpenNext

## Run locally
1. Copy `.env.example` to `.env.local` and add your Supabase project URL and publishable key.
2. Run `npm install`.
3. Run `npm run dev` and visit http://localhost:3000.

See [docs/SETUP.md](docs/SETUP.md) for beginner instructions.

## Important
Messaging screens are prepared, but live delivery is not activated until WhatsApp, SMS and email provider credentials, approved templates and customer consent are configured. Never commit environment files or expose Supabase secret/service-role keys.
