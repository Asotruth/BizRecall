# Beginner setup guide

## 1. Install tools
Install Node.js LTS from https://nodejs.org and Visual Studio Code from https://code.visualstudio.com.

## 2. Download the code
Open https://github.com/Asotruth/BizRecall, select Code → Download ZIP and extract it. You can later use GitHub Desktop to keep the project updated.

## 3. Add Supabase settings
Copy `.env.example` to a new file named `.env.local`. Your Supabase URL and publishable key are available in Supabase Dashboard → Project Settings → API Keys. Paste them into the matching variables. Never put a secret/service-role key in a NEXT_PUBLIC variable or in GitHub.

## 4. Run the website
Open the extracted folder in VS Code. Choose Terminal → New Terminal and run:

```bash
npm install
npm run dev
```

Visit http://localhost:3000. Stop the server with Ctrl+C.

## 5. Supabase Auth settings
In Supabase → Authentication → URL Configuration, set the Site URL to your website domain. Add `http://localhost:3000/**` to Redirect URLs for local development. Configure email confirmation and an SMTP provider before real customer onboarding.

## 6. Cloudflare deployment
This repository includes OpenNext and Wrangler configuration. Connect the GitHub repository in Cloudflare Workers & Pages → Create → Workers → Import a repository. Add the two Supabase environment variables in Worker Settings → Variables and Secrets. Follow the current adapter guide at https://opennext.js.org/cloudflare before production deployment. Preview and deploy scripts are `npm run preview` and `npm run deploy`.

## 7. Messaging providers
WhatsApp, SMS and email delivery are not live yet. Before enabling them, set up provider accounts, approved WhatsApp templates, sender IDs, secure credentials and a consent/opt-out process. A reminder saved in the dashboard is not the same as a message successfully sent.

## Notes
- Existing Supabase tables: vendors, customers, catalog_items, transactions, reminders and waitlist.
- Additional tables created: message_templates, message_logs and contact_messages.
- Storage bucket created: private business-assets.
- New customers default to opted_in=false.
- The pricing shown in the Figma design is draft UI only, not a live billing integration.
- Final privacy and terms copy needs legal review in Nigeria.
