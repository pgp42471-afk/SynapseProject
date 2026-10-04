# Nivas Suvidha

**A student's portal for hostel issues.**

Nivas Suvidha is a web prototype where college students can register complaints and grievances about their hostel, track the progress of each complaint, and see an anonymous overview of issues raised in their hostel (Hostel 13 in this prototype).

The whole app is a single static file, `index.html`. The CSS, JavaScript and logo are all inside it, so there is no build step and nothing to install.

## Features

- **Login screen** with user ID and password, or "Continue with Google".
- **Home dashboard** with three cards (your active grievances, your resolved grievances, total Hostel 13 grievances), quick actions, and a contacts list.
- **New complaint form** with 11 categories grouped into Service Requests, Complaints and Security. Each complaint takes the hostel floor, hostel number, a date, a time to be contacted, a description, and up to 3 attached images.
- **Your registered complaints** as an expandable table with a 4-step progress tracker (Complaint Received, Under Inquiry, Action Initiated, Resolved) and filters by status and category.
- **Total Hostel 13 grievances** table showing only category, date, time, description and status. No resident names are shown. Your own complaints are marked with an avatar icon.
- **Light and dark mode** with an icon-only toggle switch. Light mode is the default and the choice is remembered in the browser.
- Colour-coded statuses: Received (orange), Under inquiry (yellow), Action initiated (light blue), Resolved (green).
- Responsive layout for desktop and mobile.

## Run it locally

1. Download `index.html`.
2. Double-click it to open it in a browser. That's it.

## Deploy

The file must be named `index.html`.

### Vercel

**With the CLI**

1. Put `index.html` in a folder.
2. Install the CLI: `npm i -g vercel`
3. In that folder run `vercel`, then `vercel --prod` for the live URL.

**With GitHub**

1. Push `index.html` to a GitHub repository.
2. In Vercel choose Add New, then Project, and import the repository.
3. Set Framework Preset to "Other", leave the build command and output directory empty, and click Deploy.

### Netlify

Drag the folder containing `index.html` onto https://app.netlify.com/drop.

### GitHub Pages

Push `index.html` to a repository, open Settings, then Pages, choose the main branch and the root folder, and save.

## Customise

Everything is in `index.html`:

| What | Where |
|---|---|
| Colours | CSS variables at the top of the `<style>` block (`--navy`, `--orange`, and so on) |
| Contacts (names, phone numbers, emails) | The `<ul class="clist">` list in the Home section |
| Sample complaints | The `mine` and `others` arrays near the start of the `<script>` block |
| Complaint categories and icons | The `IC` and `GR` objects in the `<script>` block |
| Contact time options | The loop that fills the time dropdown (8 AM to 8 PM) |
| Hostel name and number | Search for "Hostel 13" |

## Limitations of this prototype

- **No real login.** Any non-empty user ID and password signs you in, and the Google button simply signs you in. The "registered college email only" rule is not enforced.
- **No database.** Complaints and attached images live only in the browser's memory and reset when the page is refreshed.
- **Sample data.** The complaints, counts, phone numbers and email addresses are placeholders.
- **Placeholder screen.** "View profile" in the profile menu only shows a short message.
- **One fixed hostel.** The dashboard and tables are set up for Hostel 13.

## Next steps

- Real authentication limited to registered college email addresses (for example Google sign-in through Firebase or Supabase).
- A database and file storage so complaints and images are saved.
- A profile page.
- Warden and admin views to update complaint stages.
- Notifications when a complaint changes status.
- A multi-file React project. A detailed build prompt for this is provided separately in `Nivas_Suvidha_Antigravity_Prompt.md`.

## Tech

Plain HTML, CSS and JavaScript. Font: Nunito (loaded from Google Fonts).
