<div align="center">
  <img src="logo.svg" alt="rss-feeds" width="128"/>

  # rss-feeds

  **📡 My hand-picked RSS subscriptions in one portable OPML file — for any reader or AI agent 🤖**

</div>

My personal RSS subscription list, kept as [`feeds.opml`](feeds.opml).

- Import it into any reader (NetNewsWire, Folo, Feedly, Inoreader…).
- Or let an AI agent read it and summarize what's new.

## 📚 Subscriptions

| Group | Source | Feed |
|-------|--------|------|
| Blogs | [Dave Cheney](https://dave.cheney.net/) | [`feed`](https://dave.cheney.net/feed) |
| Blogs | [Flavio Copes](https://flaviocopes.com/blog/) | [`rss.xml`](https://flaviocopes.com/rss.xml) |
| Blogs | [Martin Fowler](https://martinfowler.com/) | [`feed.atom`](https://martinfowler.com/feed.atom) |
| Labs | [Anthropic Research](https://www.anthropic.com/research) | [`anthropic-research.xml`](https://raw.githubusercontent.com/alan-turing-institute/ai-rss-feeds/refs/heads/main/feeds/anthropic-research.xml) (unofficial, via [ai-rss-feeds](https://github.com/alan-turing-institute/ai-rss-feeds)) |

## 🚀 Use it

**In a reader:** import `feeds.opml`. In NetNewsWire, choose **File → Import Subscriptions…**

**With an AI agent:** point it at this repo and ask, for example: *"Read `feeds.opml`, fetch each feed, and summarize this week's new posts."*

## ➕ Add a feed

1. Find the feed URL. Look for `<link rel="alternate" type="application/rss+xml">` in the page's HTML, or try `/rss.xml`, `/feed`, `/index.xml` or `/feed.atom`.
2. Add an `<outline>` under the right group in `feeds.opml`, in name order:

   ```xml
   <outline text="Name" type="rss" xmlUrl="https://example.com/rss.xml" htmlUrl="https://example.com/"/>
   ```

3. Check that the file is still valid XML: `xmllint --noout feeds.opml`
4. Add a row to the table above, keeping rows sorted by group, then by name. Then commit.
