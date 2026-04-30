# INKWELL — Modern Blog Website

A clean, fully client-side blog web application built with vanilla HTML5, CSS3, and JavaScript. Features a dark/light theme toggle, category filtering, live search, and a smooth post reading experience — all with zero external JavaScript dependencies.

**Live Demo:** [blog-website-29d1.onrender.com](https://blog-website-29d1.onrender.com)

---

## Features

- **Dark / Light theme toggle** — persists across the session with a smooth transition
- **Category filtering** — filter posts by topic (Technology, Design, Lifestyle, News, etc.)
- **Live search** — filters cards in real time as you type, matching title and excerpt
- **Featured post** — first post renders in a wider featured card layout
- **Post reader view** — clicking any card opens a full reading view without a page reload
- **Like button** — toggleable heart button with live count update per post
- **Responsive layout** — fluid grid that adapts from single-column mobile to multi-column desktop
- **Noise texture overlay** — subtle SVG fractal noise for a tactile background feel
- **Glassmorphism navbar** — sticky, blurred navigation bar
- **Zero dependencies** — no frameworks, no build tools, no npm; runs directly in the browser

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, flexbox, transitions) |
| Logic | JavaScript ES6 (DOM API, array methods, template literals) |
| Fonts | Google Fonts — Bebas Neue, DM Serif Display, DM Sans |
| Hosting | Render (Static Web Service) |

---

## Project Structure

```
/
└── index.html      # Complete application — markup, styles, and script in one file
```

All posts, logic, and styles are self-contained in `index.html`. No build step required.

---

## How It Works

### Posts Data
Posts are defined as a JavaScript array of objects inside the `<script>` tag. Each post has an `id`, `title`, `excerpt`, `category`, `date`, `readTime`, `likes`, `image` (Unsplash URL), `tags`, and a `content` string of HTML for the full article body. One post can be marked `featured: true` to trigger the wider card layout.

### Rendering
`renderPosts()` reads the active category and search input, filters the posts array, and dynamically builds card elements via `innerHTML`. The featured card gets a separate HTML template. Cards are re-rendered on every filter or search change.

### Theme
`toggleTheme()` flips the `data-theme` attribute on `<html>` between `"dark"` and `"light"`. All colours are CSS custom properties that change instantly via the attribute selector.

### Post View
`openPost(id)` hides the home grid (`#home-view`) and shows the post view (`#post-view`), injecting the post's full HTML content into `#post-content-area`. `showHome()` reverses this.

---

## Running Locally

No installation needed. Just open the file in a browser:

```bash
# Clone the repository
git clone https://github.com/Devesh-Yadav22/blog-website.git

# Open directly
open index.html
```

Or serve it with any static server:

```bash
npx serve .
# then visit http://localhost:3000
```

---

## Deployment

The project is deployed as a **Static Web Service** on [Render](https://render.com).

To deploy your own copy:
1. Push the repository to GitHub
2. Create a new **Static Site** on Render
3. Set the build command to blank (no build needed) and the publish directory to `/`
4. Connect your GitHub repo — Render auto-deploys on every push to `main`

---

## Screenshots

> Home — dark mode with featured card and category filters

> Post reader view with tags and metadata

---

## License

Free to use for learning and reference purposes.
