---
title: "Added Custom DEVM Favicon to Site"
date: 2025-06-09 10:00:00 +0500
categories: [Blog]
tags: [favicon, branding, customization]
---

Today, I customized my site’s appearance by adding a unique favicon using my own DEVM logo design. A favicon helps establish visual identity and appears in browser tabs, bookmarks, and more.

---

## 🧩 Favicon Variants I Added

To ensure compatibility across all platforms and devices, I included the following favicon files:

- `favicon.ico`
- `favicon-32x32.png`
- `favicon-16x16.png`
- `apple-touch-icon.png`
- `site.webmanifest`
- `browserconfig.xml`
- `mstile-150x150.png`

These are located in the `assets/img/favicons/` folder.

---

## 🧾 Head Tag Code Snippet

I updated the `<head>` section of my site with this block to load all favicon types:

```liquid
{% raw %}
{% capture favicon_path %}{{ '/assets/img/favicons' | relative_url }}{% endcapture %}

<link rel="apple-touch-icon" sizes="180x180" href="{{ favicon_path }}/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="{{ favicon_path }}/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="{{ favicon_path }}/favicon-16x16.png">
<link rel="shortcut icon" href="{{ favicon_path }}/favicon.ico">
{% if site.pwa.enabled %}
  <link rel="manifest" href="{{ favicon_path }}/site.webmanifest">
{% endif %}
<meta name="apple-mobile-web-app-title" content="{{ site.title }}">
<meta name="application-name" content="{{ site.title }}">
<meta name="msapplication-TileColor" content="#da532c">
<meta name="msapplication-config" content="{{ favicon_path }}/browserconfig.xml">
<meta name="theme-color" content="#ffffff">
{% endraw %}
