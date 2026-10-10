# Phase 1 Audit — Progress Report (partial)

Site: https://www.future-leaders.es/ (Wix site "Future Leaders", ID `40e94abc-a69f-48d4-be1f-0c840c5a1c9c`)
Status: **Partial.** Collected via the Wix API (read-only). The live site itself could not be
loaded from this environment yet — see "Blockers" below.

## Site facts (from Wix API)

| Item | Value |
|---|---|
| Editor | Wix Editor (classic), Velo (custom code) **enabled** |
| Plan | Premium, custom domain |
| Language / timezone / currency | en / Europe/Madrid / EUR |
| Contact email | info@future-leaders.es |
| Contact phone | +34 641 077623 |
| Google Search Console verification | `google-site-verification` = `QwnSJZtaTsjsRudWCyAonpRmD079KnJ39Q72o9xhUKE` (must be carried over) |
| Installed apps | Promote SEO, Wix Forms (new), Wix Forms & Payments (legacy), Wix Hotels, Wix Invoices |

## Page & URL inventory (19 static pages)

| # | URL | SEO title | Meta description | Indexed? |
|---|---|---|---|---|
| 1 | `/` | Future Leaders \| Entrepreneurship Case Competition | International entrepreneurship case competition in Spain focused on leadership development, career skills, and hands-on global experience, with a €1,000 investment prize for standout student ideas and projects. | yes |
| 2 | `/about` | About Us \| Future Leaders | — | yes |
| 3 | `/case-competition` | Case Competition \| Future Leaders | Join the Future Leaders Case Competition in Barcelona and solve real-world business challenges while building skills, confidence, and teamwork. | yes |
| 4 | `/summer` | Summer Programs \| Future Leaders | Join immersive summer programs in Spain combining travel, entrepreneurship, and cultural experiences designed for students aged 15–18. | yes |
| 5 | `/semester` | Semester Programs \| Future Leaders | Explore semester-long programs in Barcelona focused on entrepreneurship, innovation, and hands-on learning experiences for global students. | yes |
| 6 | `/alumni` | Alumni \| Future Leaders | — | yes |
| 7 | `/faq` | FAQ \| Future Leaders | Find answers to common questions about Future Leaders programs, applications, travel, accommodation, and student life in Spain. | yes |
| 8 | `/contact` | Contact \| Future Leaders | — | yes |
| 9 | `/apply` | Register \| Future Leaders | — | yes |
| 10 | `/register` | Register Multi Program \| Future Leaders | Apply now to Future Leaders programs in Spain and take the first step toward an immersive experience in entrepreneurship, travel, and growth. | yes |
| 11 | `/form` | Form \| Future Leaders | — | yes |
| 12 | `/pay-now` | Payment \| Future Leaders | — | yes |
| 13 | `/thanks` | Thank You \| Future Leaders | — | **noindex** |
| 14 | `/privacy` | Privacy Policy \| Future Leaders | — | yes |
| 15 | `/terms` | Terms & Conditions \| Future Leaders | — | yes |
| 16 | `/stories` | Success Stories \| Future Leaders | — | **noindex** |
| 17 | `/blog` | Blog \| Future Leaders | Discover entrepreneurship and innovation in Barcelona with Future Leaders. Read expert insights, student stories, and leadership tips for tomorrow’s changemakers. | **noindex** |
| 18 | `/blog-page` | Blog \| Future Leaders | — | **noindex** |
| 19 | `/women-entrepreneurship-blog` | Blog1 \| Future Leaders | — | **noindex** |

Not yet verified: which pages are in the menu / footer, which are hidden, dropdown structure,
section order and all on-page text. These require loading the live pages.

## Forms (Wix Forms)

### Registration Form (`9e29fda0-…`)
Heading: **"Future Leaders Case Competition Registration"**. Submit button: **"Register"**.
On success: redirects to `/thanks`. Saves submitter as a Wix contact.

| Field | Type | Required |
|---|---|---|
| Full name | text | yes |
| Email | email | yes |
| Phone | phone | no |
| Birthdate | date | no |
| Nationality & Languages | text | yes |
| Degree Title & Current Year in University | text | yes |
| What motivates you to apply for this entrepreneurship program, and how does it align with your goals? | long text | yes |
| Are you available to attend our Monday masterclasses from 5:30–7:30pm throughout the program, including the first four weeks online followed by eight weeks of in-person sessions at EU Business School? | radio: Yes / No / Unsure/Depends | yes |
| Do you have flexibility on Wednesday and Thursday afternoons or evenings to collaborate with your group? | radio: Yes / No / Unsure/Depends | no |
| Promotional Code | text | no |
| Consent text: "By submitting this form, you acknowledge that you have read, understood, and agree to our [Terms and Conditions](/terms)." | rich text | — |

(Field display order still to be confirmed against the live page.)

### Subscribe Form (`a134c7b3-…`)
Email (required) + subscribe-to-newsletter checkbox. Saves as a Wix contact with subscription status.

## Media library (Wix Media Manager)

181 image files, all in the root folder (no subfolders). Includes: logo variants
("Future Leaders.png", "Proposed FL Logos*.png", "Favicon.png", "Copy of SGY Logo…"),
hero backgrounds ("FL Case Competition Website Background (1–4).png"), event photos
("Future Leaders_46/50/75/89/96/97/122.JPG"), team/judge headshots, collaborator logo strips,
"How the Future Leaders Challenge Works" graphics, and blog/AI images.

Many are duplicates or older edits (`_edited`, `_edited_edited`). The images **actually used** on
each page can only be determined from the live pages. Originals are downloadable at full
resolution from `static.wixstatic.com` once network access allows it. No video files are in the media library.

## Integrations that will need replacing (preliminary)

| Wix feature | Where | Preliminary replacement |
|---|---|---|
| Wix Forms (registration, subscribe) | `/apply`, `/register`, `/form`, footer? | Form service (e.g. Netlify Forms / Formspree) or serverless function + email |
| Wix Forms & Payments / Wix Invoices | `/pay-now` — **confirmed in active use** by the owner | Stripe Payment Link or Stripe Checkout (must be implemented and tested before migration) |
| Wix Hotels | **Not used** (confirmed by owner) | None — do not rebuild |
| Velo custom code | unknown pages | Must inspect behaviour on live site |
| Blog pages | `/blog`, `/blog-page`, `/women-entrepreneurship-blog` (all noindex) | Static pages / Markdown |
| Contacts/CRM, newsletter list | form submissions | Export contacts; choose email tool |

## Blockers

1. **Live site unreachable from this environment.** The cloud environment's network policy denies
   `www.future-leaders.es`, `static.wixstatic.com` and other non-package hosts. Without them I
   cannot read page text, layout, colors, fonts, menus, or download original images.
2. Velo code and page layouts are not exposed by the Wix REST API for classic Editor sites.
</content>
</invoke>
