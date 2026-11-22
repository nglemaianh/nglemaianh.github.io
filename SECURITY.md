# Security Policy

Thank you for taking the time to look after this project. It is a personal portfolio website maintained by one person on a best-effort basis — reports are welcome and genuinely appreciated.

## Security overview

This repository is a **static website**: one `index.html` plus images, videos, and PDFs. The page's own code has:

- no backend, database, user accounts, or forms;
- no cookies, `localStorage`, or analytics;
- no `eval()` or `new Function()`, and nothing is rendered from the URL (query string or hash).

That keeps the attack surface small. The areas that *do* deserve attention are:

| Area | Why it matters |
|---|---|
| **Content rendering** | Text in the `const D` data object is inserted into the page as HTML (`innerHTML`). It is trusted, owner-authored content — see [Notes for contributors](#notes-for-contributors). |
| **Third-party resources** | The page loads Google Fonts and PDF.js (pinned to v5.6.205) from jsDelivr, with unpkg as a fallback. Visitors' browsers contact these providers. |
| **Published files** | Photos, certificate scans, and PDFs are public. They may contain personal data or metadata (for example GPS location in EXIF). |
| **The repository itself** | GitHub account security, the Pages deployment, and anything accidentally committed (such as tokens). |

## Supported versions

There are no versioned releases. Only the latest state of the `main` branch — the version deployed to GitHub Pages — receives security fixes.

| Version | Supported |
|---|:-:|
| Latest `main` (deployed site) | ✅ |
| Older commits, forks, and copies | ❌ |

## Reporting a vulnerability

**Please do not open a public issue, pull request, or discussion for security problems.**

1. **Preferred — GitHub private reporting:** open the repository's **Security** tab → **Advisories** → **Report a vulnerability** (or go directly to <https://github.com/nglemaianh/nglemaianh.github.io/security/advisories/new>).
2. **Alternative — e-mail:** [nguyenleemaianh@gmail.com](mailto:nguyenleemaianh@gmail.com) with the subject line `[SECURITY] nglemaianh.github.io — short summary`.

A useful report includes:

- what the problem is and what an attacker could do with it;
- clear steps to reproduce (URL or file, browser and OS, and a proof of concept if you have one);
- the affected file or section of `index.html`, if you know it;
- optionally, a suggested fix and how you would like to be credited.

Please don't include other people's real personal data in a report, and don't access, modify, or delete data that isn't yours.

## What to expect

This project is maintained by one person, so the timelines below are targets rather than guarantees:

- **Acknowledgement** within 7 days.
- **Initial assessment** (accepted, needs more information, or declined, with reasons) within 14 days.
- **Fix or mitigation** as soon as reasonably possible, with updates to you along the way.
- **Credit** in the published advisory or release notes, unless you prefer to stay anonymous.

Please allow up to 90 days for a fix before disclosing details publicly; for a static site it should normally be much faster. I will not take action against anyone who researches and reports in good faith under this policy.

## Scope

**In scope**

- The live site (`https://nglemaianh.github.io/REPO-NAME/`) and the code and files in this repository.
- Cross-site scripting or HTML injection through content the page renders, and unsafe link or media URLs (for example `javascript:`) in the data.
- Third-party code loaded in a way that could be hijacked or tampered with.
- Sensitive information exposed in the repository, its history, or the deployed files — secrets, ID numbers or addresses on certificates, EXIF location data, and similar.

**Out of scope**

- Vulnerabilities in GitHub, GitHub Pages, jsDelivr, unpkg, Google Fonts, PDF.js, or browsers themselves — please report those to the vendor. (If the way this site uses them makes the issue exploitable, do tell me.)
- Missing HTTP response headers (CSP, `X-Frame-Options`, HSTS, …) — GitHub Pages doesn't allow custom headers.
- Clickjacking, CSRF, or rate-limiting reports — the site has no logins or state-changing actions.
- Self-XSS (requiring a visitor to paste code into their own console) and issues that only affect outdated browsers.
- Automated scanner output with no demonstrated impact, denial-of-service or volumetric traffic, spam, social engineering, and physical attacks.
- Typos, broken links, or content mistakes — please open a regular issue for those.

## Notes for contributors

- **Content is HTML.** Every field in `const D` goes through `innerHTML`, so only add content you trust. When reviewing a pull request that touches `index.html`, look for `<script>`, `<iframe>`, inline event handlers (`onerror=`, `onclick=`), `javascript:` or `data:` URLs, and unexpected external hosts.
- **Keep external links safe.** Links that open in a new tab must keep `target="_blank" rel="noopener"` (all of them do today).
- **Update third-party code deliberately.** PDF.js is pinned to an exact version and loaded with a dynamic `import()`, so it isn't covered by Subresource Integrity hashes. When upgrading, change the version on purpose and re-test the flipbook reader. To remove the third-party dependency entirely, self-host PDF.js (copy `pdf.min.mjs` and `pdf.worker.min.mjs` into the repository) and point `PDFJS_SOURCES` at your copy.
- **Check files before you commit them:**
  - strip EXIF metadata (GPS location, device info) from photos;
  - crop or blur ID numbers, dates of birth, addresses, phone numbers, and QR codes on certificates and PDFs;
  - never commit tokens, passwords, or `.env` files — this project doesn't need any.
- **Git remembers.** Deleting a file in a new commit doesn't remove it from history. If something sensitive was committed, remove it from history (for example with `git filter-repo` or BFG), force-push, and treat any exposed secret as compromised — revoke and replace it.
- **Protect the account.** Enable two-factor authentication on GitHub, and turn on secret scanning and push protection (free for public repositories).

## Contact

Maintainer: **Nguyen Le Mai Anh** ([@nglemaianh](https://github.com/nglemaianh)) — [nguyenleemaianh@gmail.com](mailto:nguyenleemaianh@gmail.com)
