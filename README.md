# 📌 GitHub Pages: Static Hosting

GitHub Pages is a **static site hosting service**.

It hosts websites built from static files and does **not** run backend code or servers.

## What "static" means

* Files are served as-is from a CDN.
* No server-side execution (Node.js, Python, Java, PHP, etc.).
* No databases or APIs hosted on GitHub Pages.
* The browser executes HTML, CSS, and JavaScript directly.

---

# 🚀 GitHub Pages Deployment (Behind the Scenes)

This project is hosted using **GitHub Pages**.

When GitHub Pages is enabled (**Settings → Pages → Deploy from a branch → `main` branch → `/ (root)`**), GitHub automatically creates and manages a deployment workflow called:

```text
pages-build-deployment
```

This workflow is automatically created and maintained by GitHub when using the default GitHub Pages deployment. In most cases, **no custom GitHub Actions workflow or YAML configuration is required**.

---

## 🔧 What Happens Automatically

Every push to the `main` branch triggers a deployment.

GitHub will:

* Check out the repository
* Detect the site type (static in this project)
* Skip build steps if no build process is required (for example, no Jekyll, Node.js, or npm)
* Create a Pages deployment artifact
* Deploy the artifact to GitHub Pages
* Publish the updated website through GitHub's global CDN

The website is **not served directly from the repository**, but from the generated deployment artifact.

---

# 📁 Referencing Static Assets

All static assets (images, CSS, JavaScript, fonts, etc.) must exist inside the repository.

Example project structure:

```text
.
├── index.html
├── style.css
└── images
    └── profile.jpg
```

Reference assets using **relative paths**:

```html
<img src="images/profile.jpg" alt="Profile Image">
```

If `profile.jpg` is in the same folder as `index.html`, then simply use:

```html
<img src="profile.jpg" alt="Profile Image">
```

> **Note:** GitHub Pages serves files exactly as they exist in the repository. File names are **case-sensitive**, so `Profile.jpg` and `profile.jpg` are treated as different files.

---

# 🌐 Hosting & Accessibility

This website is hosted using **GitHub Pages** and is publicly accessible by default.

* **User Site URL**

  ```
  https://username.github.io
  ```

* **Project Site URL**

  ```
  https://username.github.io/repository-name/
  ```

* **Access:** Public (unless configured otherwise)

* **Hosting:** GitHub Pages (CDN-backed)

* **Protocol:** HTTPS enabled

The site is served from GitHub's global CDN rather than directly from the Git repository, providing fast and reliable access worldwide.

---

# 🔎 Why It Is Public

* GitHub Pages sites are public by default.
* Content is served through GitHub's CDN.
* Anyone with the website URL can access the site.
* Repository visibility controls access to the source code, **not necessarily** the published website.

> **Note:** GitHub Pages capabilities vary depending on your GitHub plan and repository settings. Always verify your Pages visibility in **Settings → Pages** if your project contains sensitive information.

---

# 🔄 Deployment Flow

```text
Content Update
(Code / Static Files)
        ↓
Source Repository
(GitHub Repository)
        ↓
GitHub Pages Enabled
(Repository Settings)
        ↓
Pages Build & Deploy Workflow
(GitHub-managed Action)
        ↓
Site Processing
• Detect site type (static / Jekyll)
• Optional build step
        ↓
Pages Artifact Creation
(Prepared website files)
        ↓
Deployment to Pages Environment
(github-pages)
        ↓
GitHub Pages Infrastructure
(Global CDN)
        ↓
Live Website
(username.github.io or custom domain)
```

---

# 🔧 Troubleshooting

If recent changes are not visible:

* Wait 30–60 seconds for GitHub Pages to finish deployment.
* Refresh the browser using **Ctrl + Shift + R** (or perform a hard refresh).
* Ensure all asset paths are correct.
* Verify file names match exactly (GitHub Pages is case-sensitive).
* Confirm that images, CSS, and JavaScript files have been committed and pushed to the repository.

---

# ✅ Key Benefits

* Zero-configuration CI/CD
* Automatic redeployment on every push
* CDN-backed performance
* Versioned deployments and deployment history
* Enterprise-grade hosting with minimal setup

---

# 📄 GitHub Pages Support

**GitHub Pages is a static site hosting service.**

## ✅ Supported

* Static files: **HTML, CSS, JavaScript**
* Assets: images, fonts, JSON
* Frontend frameworks (**React, Vue, Angular, etc.**) after build (compile → bundle → static files)
* UI libraries (Tailwind CSS, Bootstrap, Material UI)
* GitHub Actions–based build and deployment workflows

## ❌ Not Supported

* Backend/server-side code (Node.js, Python, Java, PHP, etc.)
* Server-Side Rendering (SSR) without generating static files
* Databases
* Hosting APIs or backend services

> **Rule of thumb:** If your application can be built into static HTML, CSS, JavaScript, and assets, GitHub Pages can host it.
