# Abhay Sharma — Portfolio

Live site: https://git-of-abhay.github.io/portfolio/

The homepage is a single HTML file. GitHub Pages builds the blog with Jekyll from Markdown posts in `_posts/`. No application server or account is needed to publish an article.

## Publish a blog post

1. Copy `_drafts/post-template.md` to `_posts/YYYY-MM-DD-your-post-slug.md`.
2. Update the `title`, `description`, and `date` front matter. Write the article in Markdown with `##` section headings.
3. Optionally add a WebP/JPG/PNG image to `assets/blog/`, then add `image: /assets/blog/filename.webp` and descriptive `image_alt:` text to the post's front matter. Images inside the article can use Markdown, for example `![Diagram description]({{ '/assets/blog/filename.webp' | relative_url }})`.
4. Commit and push to `main`. GitHub Pages rebuilds the article, the blog archive, the homepage article cards, the article count, and reading time automatically.

The starter article is `_posts/2026-09-23-building-software-for-real-operations.md`. Its content is based on the published résumé. Keep `_drafts/post-template.md` as a template; it is not published.

## Project previews

Project cards with a `data-live-url="https://..."` attribute in `index.html` show a live website preview on hover. Add an image under `assets/previews/` as the mobile and loading fallback. The CF Insights card has both. Keep the normal live link so touch and keyboard users can open the project.

## Site statistics

Public repository and star counts come from GitHub's public API. The homepage visitor counter and individual article view counters use CounterAPI and are seeded at 100. They only increment on the live GitHub Pages hostname, not in local preview. These counters are approximate, and the seed is disclosed on the page.

## Preview locally

For the homepage layout only, run `python3 -m http.server 4176` and open http://localhost:4176. To preview Jekyll posts and the archive before publishing, run `jekyll serve --baseurl /portfolio` in an environment with Jekyll installed. The actual build runs on GitHub Pages after a push.
