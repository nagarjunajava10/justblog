---
title: "GitHub Pages + Jekyll"
date: 2026-02-15
---

# ✅ What this GitHub Pages Jekyll option does
When you choose:

**GitHub Pages → Build and Deployment → GitHub Pages Jekyll**

GitHub will:

- Automatically install all required Jekyll dependencies  
- Use GitHub’s official Jekyll environment  
- Build your site without needing a `Gemfile`  
- Support themes like `minima` out of the box  
- Handle the entire build pipeline for you  

This means you **don’t need to manually add**:

- `Gemfile`
- Ruby setup
- Bundler
- Local Jekyll installation

GitHub takes care of everything.

---

# 🎯 When should you use this option?
Use it if you want:

- A simple Jekyll site  
- Markdown-based daily posts  
- No local Ruby/Jekyll installation  
- Automatic builds  
- Zero maintenance  

This fits your daily-learning-log use case perfectly.

---

# 🧱 What you still need to add manually
Even with GitHub’s Jekyll builder, you still create:

### **1. `_config.yml`**
Example:
```yaml
title: "My Learning Log"
description: "Daily notes and experiments"
theme: minima
```

### **2. `_posts/` folder**
Example post:
```
_posts/2026-02-15-learning-log.md
```

With front matter:
```markdown
---
title: "Day 1 – GitHub Pages + Jekyll"
date: 2026-02-15
---

Today I learned how to set up Jekyll on GitHub Pages...
```

### **3. `index.md`**
```markdown
# Welcome to My Learning Log
```

That’s it — GitHub builds the site automatically.

---

# ⭐ Should you avoid the manual Gemfile method?
You only need the manual method if you want:

- Custom plugins  
- Local preview builds  
- Advanced Jekyll features  

For your use case (daily notes, simple site), the **GitHub Pages Jekyll** option is perfect.

---
---


# Blog Style Layout
A **blog‑style Jekyll layout** is exactly what GitHub Pages is designed for, a clean, ready‑to‑use structure that feels like a real developer blog. You’ll be able to drop in Markdown files every day and GitHub will automatically turn them into posts.

Below is a complete starter you can copy into your repo.

---

# 🧱 1. Folder Structure (Blog‑Ready)
Create this structure in your repo:

```
.
├── _config.yml
├── index.md
├── about.md
├── _posts/
│    ├── 2026-02-15-day-1.md
│    └── 2026-02-16-day-2.md
└── assets/
```

---

# ⚙️ 2. `_config.yml` (Blog Configuration)
This config uses **minima**, GitHub’s official Jekyll blog theme.

```yaml
title: "My Learning Blog"
description: "Daily notes, experiments, and progress"
theme: minima

# Enable blog features
show_excerpts: true

# Author info (optional)
author:
  name: "Nagarjuna"
  email: "your-email@example.com"

# Build settings
markdown: kramdown
```

You can expand this later with categories, tags, plugins, etc.

---

# 🏠 3. `index.md` (Homepage)
This will show your latest posts automatically.

```markdown
---
layout: home
title: "Learning Blog"
---

Welcome to my daily learning log.  
I write something new every day.
```

The `layout: home` comes from the Minima theme and automatically lists posts.

---

# 👤 4. `about.md` (Optional)
```markdown
---
layout: page
title: About
permalink: /about/
---

This is my personal learning blog where I document what I learn every day.
```

---

# 📝 5. Create Your First Blog Post
Inside `_posts/`, create:

### `2026-02-15-day-1.md`
```markdown
---
layout: post
title: "Day 1 – Starting My Learning Blog"
date: 2026-02-15
categories: learning
---

Today I set up my GitHub Pages + Jekyll blog.  
This will be my daily space to write what I learn.
```

### Rules for post filenames
Jekyll requires:

```
YYYY-MM-DD-title.md
```

---

# 🚀 6. Push to GitHub
Once you push:

```
git add .
git commit -m "Initial blog setup"
git push
```

GitHub Pages Jekyll will build your site automatically.

Your blog will appear at:

```
https://<username>.github.io/<repo>/
```

---

# 🎉 You now have a full blog system
Every time you add a new Markdown file to `_posts/`, it becomes a new blog entry.

---

# Add Search Bar
Adding a **search bar** to a Jekyll blog on GitHub Pages is absolutely doable — and you can do it *without any plugins* (since GitHub Pages restricts custom plugins). The best approach is to use a **JavaScript‑based client‑side search**, usually powered by **Lunr.js** or **Simple-Jekyll-Search**.

To keep things clean and easy, I’ll give you the **best GitHub‑Pages‑compatible method**.

---

# 🔍 Option 1 (Recommended): Simple‑Jekyll‑Search  
This works perfectly on GitHub Pages because it requires **no plugins** and only uses JavaScript + a JSON index.

---

# ✅ Step 1: Create `search.json`
In your repo root, create a file named:

```
search.json
```

Add this content:

```liquid
---
layout: none
---

[
  {% for post in site.posts %}
  {
    "title": "{{ post.title | escape }}",
    "url": "{{ post.url }}",
    "date": "{{ post.date }}",
    "content": "{{ post.content | strip_html | strip_newlines | escape }}"
  }{% if forloop.last == false %},{% endif %}
  {% endfor %}
]
```

This file becomes your searchable index.

---

# ✅ Step 2: Add a Search Bar to Your Layout
Open your theme’s header or navigation file.

If you're using **minima**, create a custom header override:

```
_includes/header.html
```

Add this search bar:

```html
<input type="text" id="search-input" placeholder="Search..." />
<ul id="results-container"></ul>
```

---

# ✅ Step 3: Add the Search Script
Create a file:

```
assets/js/search.js
```

Add this:

```html
<script src="https://unpkg.com/simple-jekyll-search@latest/dest/simple-jekyll-search.min.js"></script>

<script>
  SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json',
    searchResultTemplate: '<li><a href="{url}">{title}</a></li>',
    noResultsText: 'No results found',
    limit: 10
  })
</script>
```

---

# ✅ Step 4: Load the Script in Your Layout
In your main layout (likely `_layouts/default.html`), before `</body>`, add:

```html
<script src="/assets/js/search.js"></script>
```

---

# 🎉 Done — You Now Have a Working Search Bar
Your blog now supports:

- Full‑text search  
- Instant results  
- Works entirely client‑side  
- 100% GitHub Pages compatible  

---



