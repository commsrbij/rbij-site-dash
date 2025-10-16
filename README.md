# RBIJ Website – Editor Guide

## 0) Create a GitHub Account

Before you start, create a free GitHub account if you don’t already have one:

1. Go to [https://github.com](https://github.com)
2. Click **Sign Up**
3. Enter your email, create a password, and verify your email address
4. Once your account is active, you can create or edit repositories for the RBIJ website

---

## 1) Create a Repository and Upload Your Website Files

After creating your GitHub account, follow these steps:

1. Go to your GitHub homepage and click the green **“New”** button to create a new repository.  
2. Name it something simple, like **rbij-site**.  
3. Keep it **Public** (so GitHub Pages can publish it).  
4. Click **Create repository**.  
5. Once the repository is created, click **“Add file → Upload files”**.  
6. Upload all your website files (the `.html` files for each state and issue area, plus `rbij.css` and `index.html`).  
   - You can also drag-and-drop the files directly from your computer if you downloaded them as a ZIP and extracted them.  
7. Click **Commit changes** to save the upload.  
8. ⚠️ **Important:** Do *not* rename `index.html`. It must stay exactly that for GitHub Pages to recognize it as your homepage.

---

## 2) What’s in this folder (file structure)

- `index.html` — The home page. It lists links to all state and issue pages.
- `rbij.css` — The site’s style sheet (colors, spacing, fonts, layout).
- **State pages** — e.g., `Alabama.html`, `Ohio.html`, `DC.html`.
- **Issue pages** — e.g., `Clean Slate.html`, `Bail Reform.html`.
- Some states are intentionally **blank** (0-byte files) so they render as a white page until there’s content.

---

## 3) CSS purpose (what lives in `rbij.css`)

- **Layout**: `.section-grid` (two columns), `.section-grid.one-col` (single full-width).
- **Structure**: `.col-title`, `.block`, `.issue`, `.stat-stack`, `.stat`.
- **Typography**: fonts, sizes, spacing, links, mobile rules.

> Tip: You can leave `rbij.css` alone. Most content edits happen in the HTML files.

---

## 4) Deploy on GitHub Pages

You only need to do Steps 0–4 once to set up the site.

1. Go to your GitHub repository and click **Settings → Pages**
2. Under **Build and Deployment**:  
   - **Source**: “Deploy from a branch”  
   - **Branch**: `main` and `/ (root)`
3. Click **Save**
4. After a minute or two, your site will be live at:  
   **`https://USERNAME.github.io/REPO/`**

> You can share this link directly with others. Any committed changes automatically update the live site.

---

## 5) How to make content changes

Once deployed, you’ll use these steps for all future edits (Steps 5–10).

1. Open the file on GitHub → click the ✏️ **Edit** button  
2. Update `<p>`, `<ul><li>`, or `.stat` items  
3. Commit with a short message, e.g., “Update Maryland stats”  
4. GitHub Pages auto-updates in ~1 minute

> If a state file is **blank** (0 bytes), paste a template (see below) to give it structure.

---

## 6) Maintaining `index.html`
- Links live in the “States” and “Issue Areas” grids.  
- Add a page: duplicate a link, change `href` and text.  
- Remove a page: delete its `<a …>…</a>` line.

---

## 7) Helpful beginner links
- HTML basics — https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web/HTML_basics  
- CSS basics — https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web/CSS_basics  
- CSS layout — https://developer.mozilla.org/docs/Learn/CSS/CSS_layout  
- GitHub Pages — https://docs.github.com/pages  
- Edit files in GitHub — https://docs.github.com/repositories/working-with-files/managing-files/editing-files

---

## 8) Edit files on GitHub
- **Edit in browser**: open file → ✏️ Edit → Commit.  
- **Upload**: Add file → Upload files → Commit.  
- **Create new page**: Add file → Create new file → name it → paste template → Commit.

---

## 9) Speed up with AI tools
**GitHub Copilot (VS Code)**: generate bullets, convert text to HTML, duplicate stat pills.  
**ChatGPT**: paste text + ask for “RBIJ two-column markup” or “one-column issue page” in your house classes.

---

## 10) Quick templates

**Two-column (state)**
```html
<div class="container">
  <div class="section-grid">
    <section>
      <h2 class="col-title">Current Activity</h2>
      <div class="block">
        <div class="issue">
          <h3>State: Clean Slate</h3>
          <p>One-sentence intro.</p>
          <ul>
            <li>Bullet one</li>
            <li>Bullet two</li>
          </ul>
        </div>
      </div>
    </section>
    <section>
      <h2 class="col-title">Stats</h2>
      <div class="stat-stack" aria-label="Stats">
        <div class="stat"><p><b>1.1 million</b> adults impacted.</p></div>
        <div class="stat"><p><b>19%</b> with a record.</p></div>
      </div>
    </section>
  </div>
</div>
```

**One-column (issue or current-only)**
```html
<div class="container">
  <div class="section-grid one-col">
    <section>
      <h2 class="col-title">Issue Title</h2>
      <div class="block">
        <div class="issue">
          <p>Paragraph content. Bold key numbers like <b>650,000</b>.</p>
          <ul>
            <li>Optional bullet</li>
            <li>Optional bullet</li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</div>
```
