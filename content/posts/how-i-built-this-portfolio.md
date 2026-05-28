---
title: "How I Built This Portfolio"
date: 2026-05-28
draft: false
tags: ["hugo", "github-pages", "portfolio"]
---

This portfolio is built with [Hugo](https://gohugo.io/), a static site generator. I chose Hugo because it keeps the portfolio simple, fast, and easy to maintain. Each article is written as a Markdown file, and Hugo converts those files into a static website.

The visual theme is [Archie](https://github.com/athul/archie), a minimal Hugo theme. I selected it because it keeps the focus on the content: reflections, projects, and proof of professional development.

The source code is hosted in the GitHub repository [v31dt/v31dt.github.io](https://github.com/v31dt/v31dt.github.io). GitHub Pages publishes the repository from the `main` branch. The generated Hugo output is committed in the repository root so the current GitHub Pages configuration can serve the website directly.

## Workflow

To add a new post, I create a Markdown file in the `content/posts` directory. The file starts with front matter containing the title, date, draft status, and tags. After that, I run `hugo --gc --minify --destination .` to regenerate the static site and commit the changes to GitHub.

This makes the portfolio maintainable: new content can be added without redesigning the website, and every change is versioned through Git.
