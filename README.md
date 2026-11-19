# Buildflow Agency website

A responsive, self-contained front-end prototype for Buildflow Agency. It includes a public agency site, enquiry flow, client portal, and an admin portal with realistic seeded data.

## Run locally

Open `index.html` in a modern browser. No package installation or build step is required.

## Demo routes

- `#/` — public marketing site
- `#/services` and `#/work` — public site sections
- `#/contact` — quote / project enquiry form
- `#/login` — demo login
- `#/client` — customer portal
- `#/admin` — admin portal

For the login screen, any email and password work. An email containing `admin` opens the admin portal; all others open the customer portal.

## Demo behavior and production requirements

This project intentionally has no real backend. It is safe to explore locally:

- **Authentication:** replace the demo login with an identity provider or server-side auth (for example Auth.js, Clerk, Supabase Auth, or Firebase Auth). Enforce roles server-side.
- **Data:** replace the hard-coded project, customer, ticket, invoice, and lead arrays with a database/API. Add authorization checks for every record.
- **Enquiries:** the contact form saves only a timestamp to browser local storage as a visual demo. Submit it to a protected API endpoint and send notifications through a provider such as Resend, Postmark, or SendGrid.
- **Files:** connect upload/download actions to private object storage (S3, Cloudflare R2, or Supabase Storage) and use signed URLs.
- **Payments:** connect invoices and payment buttons to Stripe (or the selected accounting provider); never accept card data directly in the application.
- **Security:** add server-side validation, rate limiting, CSRF protection where applicable, audit logging, error monitoring, secure environment variables, and a privacy policy before launch.

## Suggested production stack

Use Next.js or Remix for the application, Postgres with Prisma/Drizzle for persistence, a managed authentication service, object storage for project files, Stripe for payments, and a transactional email provider. The current front-end can be split into route and component files during that migration.
