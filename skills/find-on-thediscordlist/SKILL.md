---
name: find-on-thediscordlist
description: Find Discord servers to join, bots to add, and emojis or stickers for a server, using the TheDiscordList tools. Use when someone asks for a Discord community ("a chill server to practise Japanese", "gaming servers"), a bot ("a moderation bot", "a music bot"), or emojis and stickers ("cat emojis", "goofy emojis"), or wants an emoji added to their own server.
---

# Finding things on TheDiscordList

TheDiscordList is a directory of public Discord servers and bots, and of the emojis and
stickers those servers use. The tools search it live, so search instead of answering from
memory: listings change every day.

## Servers and bots

1. Call `search-listings` with the person's own words as `query`. It matches on meaning,
   so "somewhere to practise Japanese with natives" works as is.
2. Set `type` to `bot` when they want something to add to their server rather than a
   community to join.
3. When the need is clearly a category ("gaming", "moderation"), call `browse-categories`
   once with `for: server` (or `bot`) and pass the matching `category` slug. A query with
   no matches is often a category that is too narrow: drop it and search again.
4. Present a few results, not all of them: the name, one line on why it fits, the member
   or server count, and the `join_url`. Use `join_url` to join or add, never an invite
   remembered from elsewhere; it rotates and is how the join is counted.
5. For a closer look at one result, `get-listing` returns its description, a bot's
   commands, and similar listings.

## Emojis and stickers

1. Call `search-media` with a short, literal word for what the emoji shows ("cat",
   "clown", "pepe", "heart"). Emoji names are literal, so an adjective like "goofy" finds
   little on its own.
2. Set `type` to `sticker` when they want stickers: without it the search is for emojis.
3. For a mood or a theme, call `browse-categories` with `for: emoji` (or `sticker`) and use
   a category tag (`meme`, `animals`, `reactions`, `cute`) as `tag`, alone or with a query.
4. Set `animated` to `true` for only animated ones. `sort` is `popular` by default (used in
   the most servers); `newest` and `downloads` are the others.
5. Results come with an image, a `page_url` and a `download_url`.

## Adding an emoji or sticker to the person's server

1. Call `my-listings`. Only servers marked `can_add_media` can take one: they are listed
   on TheDiscordList, the person can edit them, and the TheDiscordList bot is in them.
2. Confirm which emoji and which server with the person before calling `add-to-server`,
   since it uses one of the server's emoji or sticker slots.
3. If no server can take it, say why (the bot is missing or the server is not listed) and
   offer the `download_url` instead.

## Ground rules

- Results are safe for work. Do not try to work around that.
- Ids are opaque. Take them from results; never construct one.
- Do not describe a server, bot or emoji beyond what the results say about it.
