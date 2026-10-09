# Adding a Featured Project

Every featured project is a card in the two-column table in [README.md](../README.md). Follow these steps so every card looks the same.

## 1. Generate the banner on cavinmyers.com

The website repo ([camyers/cavinmyers.com](https://github.com/camyers/cavinmyers.com)) draws every project's banner, so they all match. Each banner shows the project screenshot on top, then the title and a one-line tagline.

1. Add the project's page to `content/projects/<slug>.md`, with an `image` (3:2, for example 1500×1000) and a `tagline` (one line, 55 characters at most).
2. Run `npm run og` and commit `public/banners`, `public/og` and `scripts/og/manifest.json`. The site build fails if a banner is missing or out of date.
3. After it deploys, the banner is at `https://cavinmyers.com/banners/<slug>.png`.

Use the repo name as the slug so the banner, project page and repo URLs line up.

## 2. Add a card to the README

Paste this snippet into the next empty `<td>` in the Featured Projects table:

```html
<td width="50%" valign="top">
  <a href="https://github.com/camyers/REPO">
    <img src="https://cavinmyers.com/banners/REPO.png" alt="PROJECT TITLE">
  </a>
  <p>One sentence about the problem the project solves and why it matters.</p>
  <p><a href="https://github.com/camyers/REPO">Repo</a> · <a href="https://cavinmyers.com/projects/REPO">Write-up</a></p>
</td>
```

- Put the newest or strongest projects first.
- Each `<tr>` holds two cards. If a row has only one card, keep an empty `<td width="50%" valign="top"></td>` beside it so the layout holds.
- Keep the caption to one or two sentences. The full Problem/Solution story belongs in the project's own README and its write-up on cavinmyers.com.
- Add a `Tutorial` link if a blog series goes with the project.

# Latest Posts

The list sits between the `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` markers. Each entry uses this format:

```md
- **Mon D, YYYY:** [Post Title](https://cavinmyers.com/blog/slug)
```

Keep the 5 most recent posts, newest first.

These markers are the ones [gautamkrishnar/blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow) uses, so the list can be filled automatically from `https://cavinmyers.com/feed.xml`. A PR opened from the website repo can also fill it. One catch: the feed currently includes the individual Agent Harness phase pages, so those would need to be filtered out or left out of the feed first.
