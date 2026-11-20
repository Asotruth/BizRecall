# BizRecall Phase Two

## Included application areas
- Existing business dashboard remains under /dashboard.
- Customer discovery marketplace: /portal, /portal/search, /portal/business/[slug], /portal/favorites.
- Platform administration: /platform-admin, /platform-admin/businesses, /platform-admin/users, /platform-admin/audit-logs, /platform-admin/settings.
- Supabase Auth callback: /auth/callback.
- Responsive shared sign-up and login interface.

## Supabase additions
Migration phase_two_marketplace_roles_and_profiles adds user profiles, role labels, marketplace categories, favourites, enquiries, audit events and platform settings. It also creates a private avatar bucket and per-user object policies.

## Security
- New profiles default to the customer role. Do not allow a user to promote themselves to platform_admin through public signup.
- Assign a first trusted platform administrator from the Supabase SQL editor after checking identity: update public.user_profiles set role='platform_admin' where id='<AUTH_USER_UUID>';
- The admin interface is not a substitute for row-level security. Verify table policies before live launch.
- Marketplace vendors are public only while is_listed is true.

## Not yet complete
- Outbound WhatsApp, SMS and email provider integration.
- Payment processing, subscription management, reviews, enquiry alerts and advanced marketplace search.
- Exact Figma frame parity and exact favicon export. Design retrieval hit the connected Figma plan's request limit during this implementation; these are foundations, not pixel-perfect copies.
- Production security review and end-to-end tests.

## Local setup
Run npm install and npm run dev. Configure .env.local using .env.example.
