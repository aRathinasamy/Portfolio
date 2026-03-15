# My Portfolio — GitHub Pages

> Personal portfolio site hosted via GitHub Pages. Built with vanilla HTML, CSS, and JS. All page content is authored in Markdown.

**Live site:** `https://yourusername.github.io`

---

## 📁 Repo Structure

```
/
├── index.html              ← Single-page app shell (nav + layout)
├── assets/
│   ├── style.css           ← All styles
│   └── photo.jpg           ← Your profile photo (add this yourself)
│
├── about/
│   └── index.md            ← About Me content (CV, skills, bio)
│
├── work/
│   ├── selected-work.html  ← Selected Work (standalone HTML, loaded in iframe)
│   └── index.md            ← Fallback markdown (kept for reference)
│
├── learnings/
│   ├── index.md            ← Learnings overview
│   └── ...                 ← Add more sub-pages here
│
├── topic1/
│   └── index.md            ← Future topic placeholder
│
└── topic2/
    └── index.md            ← Future topic placeholder
```

---

## ✏️ Two Types of Sections

### Markdown sections (About, Learnings, Topics)
Edit the `.md` file in the subfolder and push. Content is rendered automatically.

### HTML sections (Selected Work)
The `work/selected-work.html` file is a fully self-contained HTML page loaded inside an iframe. To update it, replace the `work/selected-work.html` file and push.

**To add a new HTML section:**
1. Place your HTML file in a subfolder (e.g. `projects/my-project.html`)
2. In `index.html`, add it to the `SECTIONS` config with `type: 'html'`:
   ```js
   const SECTIONS = {
     ...
     myproject: { type: 'html', file: 'projects/my-project.html' },
   };
   ```
3. Add a nav button:
   ```html
   <button class="nav-btn" data-section="myproject">My Project</button>
   ```

**To add a new Markdown section:**
1. Create a folder and `index.md`
2. Add to `SECTIONS` with `type: 'md'`:
   ```js
   mysection: { type: 'md', file: 'my-section/index.md' },
   ```

---

## 🖼️ Adding Your Profile Photo

1. Place your photo in `assets/photo.jpg` (or `.png`)
2. In `index.html`, find the `<img>` tag inside `.photo-circle` and remove `style="display:none"`
3. Also remove or hide the `.photo-placeholder` div

---

## 🚀 Deploy to GitHub Pages

1. Push this repo to GitHub as `yourusername.github.io`
   *(or any repo name — then enable Pages under Settings → Pages)*
2. Set the source to `main` branch, `/ (root)`
3. Visit `https://yourusername.github.io` — done!

> **Note:** Because content is loaded via `fetch()`, the site needs to be served over HTTP (GitHub Pages works fine). Opening `index.html` directly as a local file (`file://`) will block fetch requests due to browser security — use a local server instead:
> ```bash
> npx serve .
> # or
> python3 -m http.server 8000
> ```

---

## 🔗 Deep Linking

Each section is hash-routed, so you can share direct links:

| Section       | URL                                       |
|---------------|-------------------------------------------|
| About Me      | `https://yourusername.github.io/#about`   |
| Selected Work | `https://yourusername.github.io/#work`    |
| Learnings     | `https://yourusername.github.io/#learnings` |
| Topic 1       | `https://yourusername.github.io/#topic1`  |
| Topic 2       | `https://yourusername.github.io/#topic2`  |

---

## 🛠️ Tech Stack

- **HTML / CSS / JS** — no build step, no framework
- **[marked.js](https://marked.js.org/)** — Markdown → HTML rendering (loaded from CDN)
- **GitHub Pages** — free static hosting
