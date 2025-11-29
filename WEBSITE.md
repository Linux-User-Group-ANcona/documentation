# LUGAN Website Architecture & Maintenance

The official LUGAN website is built entirely on **Jekyll**, utilizing **GitHub Pages** for automatic building and hosting. This approach ensures maximum maintainability and allows us to treat our website content exactly like our code ("Governance as Code").

---

## Core Philosophy

* **Markdown First:** we strictly avoid adding custom CSS, JavaScript, or HTML files. The goal is to keep the site lightweight and easily editable by any member using standard Markdown.
* **Zero-Maintenance Build:** GitHub Pages handles the build process automatically. No local build chain is required.

---

## Structure & Navigation

* **Repositories as Subfolders:** to create a new section or "subfolder" of the organization's web presence, simply create a dedicated **ad-hoc repository**.
* **Index Files:** the `README.md` file within any repository (or folder) automatically serves as the `index.html` for that section.

---

## How to Publish a Repository

If a repository is intended to be a visible part of the LUGAN website:

1.  Go to the repository **Settings**.
2.  Navigate to the **Pages** section (sidebar).
3.  Under **Build and deployment**, select **Source** -> `Deploy from a branch`.
4.  Select the branch (usually `main`) and folder (`/root`), then click **Save**.
5.  **Critical Step:** once GitHub generates the live URL (e.g., `linux-user-group-ancona.github.io/repo-name`), copy it and paste it into the **"About"** section (website url) on the main page of the repository. This ensures the link is visible to everyone.

---

## 🌐 Web Standards & Theme Uniformity (Mandatory)

To ensure visual consistency across all LUGAN projects hosted on GitHub Pages, every new repository must adopt the official LUGAN theme configuration.

### Action: Standardize `_config.yml`

You **should** copy and use the following `_config.yml` for the new repository:

```yaml
title: <choice your title>
description: <choice your description>

plugins:
- jekyll-remote-theme

remote_theme: pages-themes/cayman@v0.2.0

defaults:
  - scope:
      path: "" # apply to all files
    values:
      layout: "default"
```

---

## ⚠️ Troubleshooting: Markdown Not Rendering?

If your Markdown page is not redirecting correctly, or if it renders as raw text/code instead of a styled HTML page, it is likely due to a missing Jekyll trigger.

**Follow these two steps to fix it:**

### 1. Ensure `_config.yml` Exists
Make sure a file named `_config.yml` exists in the root of the repository (even if it is empty or contains minimal settings).
Paste these lines inside the file:
```yaml
defaults:
  - scope:
      path: "" # apply to all files
    values:
      layout: "page" # use default page layout
```

### 2. Add Empty Front Matter
You **must** add the front matter markers at the very top of your `.md` file. This tells Jekyll to process the file.

**Add these exact lines at line 1 of your file:**

```markdown
---
---
# Your Title Here
... rest of the content ...
```
