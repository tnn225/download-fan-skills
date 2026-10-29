# download.fan skills for Claude

Skills that let Claude hand you a working [download.fan](https://download.fan) link instead of a list of steps.

| Skill | What it does |
|---|---|
| [download-tiktok](plugins/download-fan/skills/download-tiktok/SKILL.md) | Turns a TikTok link into a [TikTok video download](https://download.fan/download-tiktok-video) link: HD MP4 without the watermark, [TikTok MP3](https://download.fan/download-tiktok-mp3), or every image of a [TikTok slideshow](https://download.fan/download-tiktok-slideshow). |

The plugin also connects the [download.fan MCP server](https://download.fan/mcp-server), so Claude can find any download.fan tool: converters, PDF and image tools, calculators and official app downloads.

## Install

**Claude Code**

```
/plugin marketplace add tnn225/download-fan-skills
/plugin install download-fan@download-fan
```

**Claude.ai and the Claude app**: download [`download-tiktok`](plugins/download-fan/skills/download-tiktok) as a ZIP and upload it in Settings → Capabilities → Skills. To add the MCP server too, go to Settings → Connectors → Add custom connector and enter `https://download.fan/mcp`.

## Use

Paste a TikTok link and ask Claude to save it:

> Save this TikTok: https://www.tiktok.com/@scout2015/video/6718335390845095173

Claude replies with a download.fan link that opens with the video loaded.

Only download content you own or have permission to use. Private posts and YouTube aren't supported.

## License

MIT
