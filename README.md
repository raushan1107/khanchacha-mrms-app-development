# Flutter Foundations — Day 4 Guide

A self-contained, single-page reference site for the **Flutter Foundations: Getting Started Without Getting Lost** training module — built for students with zero Flutter background, learning to use Claude as an AI pair-programmer from day one.

**Live site:** enable GitHub Pages on this repo (see below) and your guide will be live at `https://raushan1107.github.io/khanchacha-mrms-app-development/`

---

## What this is

This is one HTML file (`index.html`) with everything embedded — styling, content, and interactivity. There's no build step, no `npm install`, no framework. You can:

- Open `index.html` directly in any browser to view it locally
- Host it on GitHub Pages for a shareable link
- Hand the link to students before or after a training session as a standing reference

## What's inside

The page is organized into eight tabs, switchable from the top navigation bar:

| Tab | Covers |
|---|---|
| **Why Flutter** | What Flutter and Dart are, why Flutter is a practical choice for a real business app, and how it compares to React Native and native development |
| **How Flutter Works** | The "everything is a widget" mental model, the `flutter` CLI command reference, what an emulator actually is, the project folder structure, and what literally happens when you click Run |
| **Installation** | Full step-by-step installation guide for Windows, macOS, and Linux — switchable via tabs, with exact commands, what to expect after each command, and a pre-class checklist |
| **Reading the Code** | A plain-English walkthrough of Dart syntax — variables, classes, lists/maps, string interpolation, functions, and named parameters — aimed at someone who has never written Dart, explicitly clarifying that Dart is not Python |
| **Hands-On with Claude** | When to use Claude chat vs. Claude Code, a warning against `--dangerously-skip-permissions` for learners, a full step-by-step workflow for pairing VS Code with Claude, and 15 progressive copy-paste prompts that build a small app incrementally |
| **Working with Data** | The fundamental "ask, wait, convert" pattern behind any data-driven screen, a real `http` package example, and where Claude helps most when connecting Flutter to a database/API |
| **Capstone Project** | One large, complete prompt that generates a full small two-screen app ("Track It"), with a step-by-step guide for wiring the generated files into a real project, plus a troubleshooting prompt template |
| **Questions & Discussion** | An expandable FAQ-style list answering the most common points of confusion, written in the same plain, descriptive style as the rest of the guide |

Every Claude prompt throughout the site has a **Copy** button — students click it, switch to Claude, paste, and run. No prompt needs to be retyped.

---

## Hosting this on GitHub Pages

1. Create a new repository on GitHub (public, so Pages can serve it for free) — for example `flutter-foundations-guide`.
2. Upload `index.html` and this `README.md` to the repository root. You can do this through GitHub's web UI (drag and drop the files in) or via git:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Add Flutter Foundations training guide"
   git branch -M main
   git remote add origin https://github.com/<your-username>/flutter-foundations-guide.git
   git push -u origin main
   ```
3. On the repository page, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
5. Set **Branch** to `main` and folder to `/ (root)`, then click **Save**.
6. Wait about a minute, then refresh — GitHub will show you the live URL, typically:
   ```
   https://<your-username>.github.io/flutter-foundations-guide/
   ```
7. Share that link with your students. Bookmark it yourself as your standing reference for future Flutter training sessions.

### Updating the site later

Any time you want to add a new prompt, fix a typo, or add a new FAQ entry, edit `index.html` directly, commit, and push. GitHub Pages rebuilds automatically within about a minute — no separate deploy step.

---

## Customizing this for a different training day or audience

Everything lives in one file, organized clearly:

- **Tab navigation buttons** are near the top of the `<body>`, inside `<nav class="tabnav">`. Add a new button there and a matching `<div class="tabpanel" id="tab-yourname">...</div>` further down to add a new tab.
- **Colors and branding** are defined once at the top of the `<style>` block under `:root` — change `--teal` and `--teal-deep` to match a different brand palette without touching the rest of the CSS.
- **Footer branding** (Koenig Solutions / RR Skillverse attribution) is in the `<footer>` section near the bottom of the file — update names, links, or the copyright line there.
- **Prompt boxes** follow a consistent pattern — a `<div class="prompt-box">` containing a `<div class="prompt-text" id="some-id">` with the actual prompt text, and a copy button referencing that same id: `onclick="copyPrompt(this,'some-id')"`. Copy this pattern to add new prompts anywhere on the page.

---

## Why this exists

This guide was built to accompany a live Flutter training session, but it's designed to stand on its own afterward. Students who attended the session can revisit it to recheck a step they're unsure about; students who couldn't make it can self-serve through the entire installation and first-prompts process using nothing but this page and Claude.

---

**Powered by RR Skillverse (Raushan Ranjan)** · Built for Koenig Solutions training programs
