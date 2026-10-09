# Adding a Featured Project

Every featured project is a card in the two-column table in [README.md](../README.md). Follow these steps so every card looks the same.

## 1. Create the banner in the project repo

- **Size:** 1280×640 PNG. This is also GitHub's social preview size, so you can reuse it under the repo's *Settings → Social preview*.
- **Content:** the project title plus a small screenshot of the project, matching the existing banners:
  - [librewxr-viewer](https://raw.githubusercontent.com/camyers/librewxr-viewer/main/docs/images/banner.png)
  - [agent-harness](https://raw.githubusercontent.com/camyers/agent-harness/main/docs/images/banner.png)
- **Path:** commit it to `docs/images/banner.png` on the repo's `main` branch.

## 2. Add a card to the README

Paste this snippet into the next empty `<td>` in the Featured Projects table:

```html
<td width="50%" valign="top">
  <a href="https://github.com/camyers/REPO">
    <img src="https://raw.githubusercontent.com/camyers/REPO/main/docs/images/banner.png" alt="PROJECT TITLE">
  </a>
  <p>One sentence about the problem the project solves and why it matters.</p>
  <p><a href="https://github.com/camyers/REPO">Repo</a> · <a href="https://cavinmyers.com/projects/REPO">Write-up</a></p>
</td>
```

- Put the newest or strongest projects first.
- Each `<tr>` holds two cards. If a row has only one card, keep an empty `<td width="50%" valign="top"></td>` beside it so the layout holds.
- Keep the caption to one or two sentences. The full Problem/Solution story belongs in the project's own README and its write-up on cavinmyers.com.
- Add a `Tutorial` link if a blog series goes with the project.

## Fallback banner

If a project doesn't have a banner yet, use GitHub's generated preview image until it does:

```
https://opengraph.githubassets.com/1/camyers/REPO
```

**To do:** the Miacademy extension currently uses this fallback. Replace it once `docs/images/banner.png` exists in that repo.

# Latest Posts

The list sits between the `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` markers. Each entry uses this format:

```md
- **Mon D, YYYY:** [Post Title](https://cavinmyers.com/blog/slug)
```

Keep the 5 most recent posts, newest first.

These markers are the ones [gautamkrishnar/blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow) uses, so the list can be filled automatically from `https://cavinmyers.com/feed.xml`. A PR opened from the website repo can also fill it. One catch: the feed currently includes the individual Agent Harness phase pages, so those would need to be filtered out or left out of the feed first.
