<div align="center">

# 📱 Mobilytics

### WordPress Mobile UX Auditor

**Find what's hurting your mobile experience.**

[![WordPress](https://img.shields.io/badge/WordPress-5.8%2B-21759B?logo=wordpress&logoColor=white)](https://wordpress.org)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-777BB4?logo=php&logoColor=white)](https://php.net)
[![License](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-1.0.0-brightgreen.svg)](CHANGELOG.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A lightweight WordPress plugin that audits a site's mobile user experience and turns it into something you can actually act on:

**A 0–100 score · 8 categories · 24 checks · Plain-English fixes · A client-ready report.**

[Features](#-features) · [Screenshots](#-screenshots) · [Install](#-installation) · [How it works](#-how-a-scan-works) · [Roadmap](#-roadmap)

</div>

---

## 🎯 Why This Exists

Most site owners **know** mobile matters — but "run a Lighthouse audit" isn't something they can act on. Reports are built for engineers, not for the person running the business.

Mobilytics lives inside the WordPress dashboard they already use, speaks in plain language, and turns every finding into a task:

> **Here's what's wrong → Here's why it matters → Here's how to fix it.**

For freelancers and agencies, it doubles as a **lead-generation tool**: run it on a prospect's site, hand them a branded client report with a *"Need help fixing these issues?"* CTA — and turn an audit into a sales conversation.

---

## ✨ Features

| | |
|---|---|
| 🎯 **Overall Mobile UX Score** | 0–100 with Good / Needs Work / Critical grading |
| 📊 **8 Category Scores** | Responsive, Readability, Touch Targets, Navigation, Images, Performance, Accessibility, Mobile SEO |
| ✅ **24 Reliable Checks** | Each marked Passed / Warning / Critical — with *why it matters* and *how to fix it* |
| ⚡ **One-Click Audit** | Loading state, progress messages, last-scan timestamp |
| 🎨 **Beautiful Dashboard** | Score ring, category cards, severity badges, filterable issue list |
| 📄 **Client Report** | Public `[mobilytics_report]` shortcode with PDF export |
| 💼 **Lead-Gen CTA** | Customizable "Need help fixing these issues?" block |
| ⚙️ **Full Settings Page** | Scan frequency, exclusions, thresholds, branding, report options |
| 🔒 **Secure by Default** | Nonces, capability checks, sanitization, escaping throughout |
| 🌍 **i18n Ready** | All strings translatable |

---

## 📦 Installation

1. Clone or download this repo into `wp-content/plugins/mobilytics/`
2. Activate **Mobilytics** under **Plugins → Installed Plugins**
3. Go to **Mobilytics** in the admin sidebar → click **Run Mobile Audit**
4. *(Optional)* Create a page and add the shortcode:


- **PHP handles** everything visible in raw HTML: viewport, alt text, image weight, render-blocking scripts, meta tags.
- **JS handles** everything needing a real render: horizontal overflow, computed font sizes, real tap-target geometry, intrusive overlays.
- The JS scanner is **only ever injected** when a one-time, 5-minute transient token is present — **normal visitors never load it**.

This is the core architectural decision that keeps the plugin lightweight while still getting **real data, not guesses**.

---

## 🧮 Scoring Model

- Each check has a **weight (1–3)** based on its relative importance.
- Points: `Passed = 100`, `Warning = 50`, `Critical = 0`.
- **Category score** = weight-adjusted average of its checks.
- **Overall score** = average of all categories with applicable checks.
- Thresholds (`Good ≥ 80`, `Needs Work ≥ 50`) are configurable.

---

## 🛠 Tech Stack

`PHP 7.4+` · `WordPress 5.8+` · `WordPress REST API` · `AJAX` · `WP-Cron` · `Vanilla JS` · `CSS Grid` · `DOMDocument` · `DOMXPath`

No Composer. No npm. No build step. No external services. **Just WordPress, done right.**

---

## 🗺 Roadmap

- [ ] Multi-page / full-site crawl
- [ ] Historical score trend chart *(data already tracked)*
- [ ] Optional PageSpeed Insights API integration for Core Web Vitals
- [ ] Emailed scheduled-scan summaries
- [ ] Server-rendered PDF export (Dompdf) for pixel-perfect agency branding
- [ ] Per-page-type exclusion presets (auto-skip WooCommerce checkout)


## 📄 License

GPL v3 or later — see [LICENSE](LICENSE).

---

<div align="center">

**Built by [ Ehan Siddique ] (https://www.linkedin.com/in/ehan-siddique-0742aa34b/))**

*Mobilytics — Find what's hurting your mobile experience.*

</div>
