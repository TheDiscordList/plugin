# TheDiscordList plugin

Find Discord servers to join, bots to add, and emojis and stickers for your own server, straight from your assistant. The plugin connects to the [TheDiscordList](https://thediscordlist.com) MCP server and adds a skill that teaches the assistant how to search it well.

Ask things like:

- "Find me a chill server to practise Japanese."
- "What's a good moderation bot with auto-mod?"
- "Show me some cat emojis." / "Goofy emojis for my server."
- "Add that emoji to my server."

## What's inside

| Path | What it is |
|---|---|
| `.mcp.json` | The remote MCP server at `https://thediscordlist.com/mcp` |
| `skills/find-on-thediscordlist` | How to turn a request into the right searches |
| `.claude-plugin/` | The plugin manifest, plus a marketplace manifest so this repo can be added directly |

## Tools

| Tool | What it does |
|---|---|
| `search-listings` | Search public servers and bots by meaning and keywords, with category and tag filters |
| `get-listing` | One server or bot in full, with similar listings |
| `search-media` | Search emojis and stickers by name or category tag |
| `browse-categories` | The categories and tags to filter by |
| `my-listings` | Your own servers and bots, and which can take an emoji |
| `add-to-server` | Upload an emoji or sticker into one of your servers |

Every tool is read-only except `add-to-server`, which changes your own Discord server and only when you ask it to.

## Install

**Claude Code**

```
/plugin marketplace add TheDiscordList/plugin
/plugin install thediscordlist@thediscordlist
```

**Claude, ChatGPT and other MCP clients**: add `https://thediscordlist.com/mcp` as a custom connector.

Searching needs no account. `my-listings` and `add-to-server` work on your own servers, so the first time you use one you're asked to sign in with Discord and approve the connection. You can revoke it at any time.

## Privacy and support

- Privacy policy: https://thediscordlist.com/privacy
- Terms: https://thediscordlist.com/terms
- Support: open an issue in this repository

## License

MIT
