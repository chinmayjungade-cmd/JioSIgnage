# JioSignage — Build log (prompts)

A chronological record of the prompts/requests used to build this project with Claude Code,
so the "how it was built" history travels with the code. Live site:
https://chinmayjungade.github.io/jiosignage/ · Repo: https://github.com/chinmayjungade/jiosignage

> Note: paraphrased faithfully from the working session; grouped where several small
> tweaks happened together. Design source of truth throughout = the Jio Design System (JDS).

## 1. Initial build
- Build the official **JioSignage landing page** as a Senior Product Designer / Frontend
  Engineer. Use the **JDS** as the single source of truth (colors, type, spacing, components,
  radii, motion). References: jiodigisign `index.html` (content & information architecture,
  section order), **Samsung VXT** (hero + industry-showcase quality, motion inspiration),
  **jio.com** (brand feel, white space, cards, CTAs). Modern, premium, enterprise-SaaS, B2B.
  Sections required: Sticky Nav, Hero, Trusted-by, Product Overview, Key Features, Industries,
  Why Choose, Platform Capabilities, Device Compatibility, CMS Dashboard Preview, Customer
  Benefits, Testimonials, FAQ, Final CTA, Footer. Accessible, responsive, subtle animations,
  meaningful enterprise copy (no lorem). (Delivered as a self-contained HTML/CSS/JS site,
  since the machine had no Node — chosen over a Next.js project so it could be previewed here.)
- Remove the "Chat with us" section completely.

## 2. Features page
- Add the content from jiodigisign `features.html` to the **Features** tab in the menu —
  built `features.html` (14-feature grid + "deep dive" section), wired the Features nav to it.
- Later cleanups on Features:
  - Remove the "Deep Dive" section heading kicker and the category labels.
  - Remove the "✨ 14 Powerful Features" badge and the hero buttons.
  - Make the hero font-size & spacing match the homepage banner.
  - Make the hero paragraph width the same as the header (full container width).

## 3. Sign-in / Login page (from Figma)
- On clicking the header **Sign in** CTA, open a login page. First pass referenced Figma
  node `26-2379` with flows: Login, Wrong email, Wrong password, Forgot password.
- Rebuilt to the exact Figma frames once Figma reconnected — Login (`26:33108`), **OTP**
  (`26:33158`), Forgot password (`26:33110`): JDS underlined fields with floating labels,
  6-digit OTP with resend timer, "Get OTP" → verify → dashboard, Jio dot-grid left panel.
- Match the login screen to the reference exactly (heading "Log in", left-aligned
  "Forgot password?", no eye toggle, corrected dot-grid).
- Keep the site header on the sign-in page and remove the "Back to website" link.
  Use ds.jio.com/login as the reference for the left-side section.

## 4. Landing-page edits
- Remove the "Watch overview" button from the hero.
- Remove the "Enterprise Digital Signage" hero badge.
- Header active-tab highlight: apply the underline highlight consistently (scroll-spy).
- "Trusted by" strip → header **"Trusted by India's Leading Brands"**, remove icons,
  continuous right-to-left loop, use the supplied list of ~65 real brand names.
- Industries: change the icons to **image format** (real Indian-sector signage photos);
  images load from `images/industries/*.png` (icon/placeholder fallback until added).
- Fix images not loading (filename `.jpg` vs `.png` mismatch; corrected to `.png`).
- Device Compatibility: remove the table; remove the leftover bottom space.
- CMS Dashboard: replace the built mockup with the **real dashboard image**, lay it out
  **text-left / image-right** (`images/dashboard.png`).
- FAQ: add smooth open/collapse transitions; reduce the white space below the section.
- "View all 14 features" CTA opens the Features page.
- Industries section → rebuilt as a **Samsung-VXT-style tabbed showcase** (Restaurant,
  Retail, Corporate, Healthcare, Grocery) with fade transitions.
- Add, then remove, a bold **"Engage. Inform. Inspire."** highlight band.

## 5. Global header changes
- Rename nav tabs across all pages: **Product → Solutions**, **FAQ → About us**.

## 6. Solutions page
- Build the **Solutions page** from the jiodigisign `solutions.html` reference, same branding,
  spacing and formatting: 8 industry solution cards with tag chips, "Trusted by India's
  Leading Brands" brand grid, and an "In the wild" 3-card row. Wire the Solutions nav to it.
- Remove `span.eyebrow` and `span.kicker` (badge + section kickers).
- Make the Solutions hero match the homepage/features hero (`.fhero`) for consistency.
- Replace the "In the wild" LED-walls icon with a real image (`images/solutions/led-walls.png`).

## 7. Book a demo
- Build a dedicated **Book a demo** page with a request form (name, email, company, phone,
  industry, screens, message; validation + success state). Link every "Book a demo" CTA to it.
- Book a demo: pin the footer to the bottom (responsive), remove the trust line, add spacing
  under the heading.

## 8. Branding
- Use the supplied logo globally (extracted to `images/logo.png`; replaced all brand marks
  and favicons across every page).

## 9. Publish & hosting
- Create a public, auto-updating link → set up as a **GitHub Pages** site.
- Guide through the GitHub CLI; then uploaded to `github.com/chinmayjungade/jiosignage` and
  enabled Pages. Live at `https://chinmayjungade.github.io/jiosignage/`.
- Every `git push` auto-redeploys the live site.

## Pages in this project
- `index.html` → redirects to the landing page
- `jiosignage-landing.html` — home
- `features.html` — Features (14-feature grid + deep dive)
- `solutions.html` — Solutions (industry solutions, brand grid, in-the-wild)
- `login.html` — Sign in (Login / OTP / Forgot password)
- `book-a-demo.html` — demo request form
- `images/` — logo, dashboard, industry & solutions photos
