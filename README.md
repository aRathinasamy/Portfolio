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
│   └── index.md            ← Selected Work / Projects
│
├── learnings/
│   ├── index.md            ← Learnings overview
│   ├── react-performance.md
│   ├── postgres-indexing.md
│   └── ...                 ← Add more sub-pages here
│
├── topic1/
│   └── index.md            ← Future topic placeholder
│
└── topic2/
    └── index.md            ← Future topic placeholder
```

---

## ✏️ How to Edit Content

All content is plain Markdown (`.md`). Just edit the files and push — GitHub Pages will serve the updated content automatically.

**Edit a section:**
```bash
# Example: update your About Me
nano about/index.md
git add about/index.md
git commit -m "Update about me"
git push
```

**Add a new sub-page inside Learnings:**
1. Create a file: `learnings/my-new-topic.md`
2. Link to it from `learnings/index.md`:
   ```markdown
   [Read notes →](./my-new-topic.md)
   ```
3. Push — it's live!

**Add a new top-level section:**
1. Create a folder: `my-section/`
2. Add `my-section/index.md`
3. In `index.html`, add the section to the `SECTIONS` config object:
   ```js
   const SECTIONS = {
     ...
     mysection: 'my-section/index.md',
   };
   ```
4. Add a nav button in the HTML:
   ```html
   <button class="nav-btn" data-section="mysection">My Section</button>
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
