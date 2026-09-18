# Canis — A Dog Breed Encyclopedia

A single-file, static web app for exploring dog breeds: browse detailed profiles, compare two breeds side by side, and run a short questionnaire to get breed suggestions worth researching further.

No build step, no dependencies, no backend — it's one `index.html` file you can open directly or deploy anywhere that serves static files.

## Features

- **Breed Explorer** — browse and filter breeds by group, size, and other traits, with a live search.
- **Breed Profiles** — overview, temperament tags, care notes, quick facts, and a photo gallery for each breed.
- **Compare** — pick two breeds and see their stats (energy, trainability, grooming, size, lifespan, etc.) side by side.
- **Find a Breed** — a short questionnaire that surfaces breeds worth researching further based on lifestyle and home.
- **Light/Dark theme** — toggleable, persisted via `localStorage`.
- **Cookie consent banner** — persisted via `localStorage`.
- **Client-side routing** — hash-based (`#/explorer`, `#/compare`, `#/finder`, `#/about`, etc.), no page reloads.
- **Accessible & responsive** — skip link, keyboard-dismissible mobile drawer, responsive layout down to small screens.

## Tech Stack

- Plain HTML, CSS, and vanilla JavaScript (IIFE, no framework)
- Google Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) (headings) + [Inter](https://fonts.google.com/specimen/Inter) (body)
- Breed data and images are embedded directly in the file (base64)

## Getting Started

No installation required.

```bash
# Clone the repo
git clone <repo-url>
cd <repo-folder>

# Just open it in a browser
open index.html   # macOS
# or double-click index.html
```

For hash-based routing to work smoothly with a local server (optional):

```bash
npx serve .
# or
python3 -m http.server
```

## Deployment

Since this is a single static HTML file, it can be deployed as-is to any static host — GitHub Pages, Netlify, Vercel, Cloudflare Pages, S3, etc. No build command is required.

## Project Structure

```
.
└── index.html   # entire app: markup, styles, breed data, and routing/rendering logic
```

## Adding a Breed

Breed data lives in the `BREEDS` array in the inline `<script>`. Each entry looks like:

```js
{
  id: "breed-slug", name: "Breed Name", group: "Herding", size: "Large",
  weight: "22–40 kg", lifespan: "9–13 years", origin: "Country",
  coat: "Double", energy: 5, trainability: 5, grooming: 3,
  temperament: ["Confident", "Loyal", "Courageous", "Watchful"],
  overview: "…",
  care: "…",
  facts: ["…", "…", "…", "…"],
  primary: IMG.example_primary, gallery: [IMG.example_g1, IMG.example_g2, IMG.example_g3]
}
```

Add a new object to the array (and its images to the `IMG` lookup) to add a breed — no other code changes needed.

## Disclaimer

Breed profiles are written as general starting points for research. Individual dogs vary, and breed tendencies are not guarantees of any one dog's temperament or needs.

## License

Add a license of your choice (e.g. MIT) here.
# canis-encyclopedia
