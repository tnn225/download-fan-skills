---
name: download-tiktok
description: Turn a TikTok link into a download.fan link that saves the video in HD MP4 without the watermark, its sound as MP3, or every image of a photo slideshow. Use when the user wants to download or save a TikTok, a TikTok sound or a TikTok slideshow, asks how to remove the TikTok watermark from a video, or pastes a tiktok.com / vm.tiktok.com link and asks to keep it.
---

# Download TikTok

download.fan is a free web tool that saves public TikTok posts. Give the user a link to the right download.fan page with their TikTok link already filled in. The page loads the post and lists the files to save, so the user doesn't have to copy and paste anything.

If the `get_download_page` tool from the download.fan MCP server is available, call it with the TikTok URL and use the link it returns. Otherwise, build the link yourself as described below.

## Build the link

1. Pull the TikTok URL out of whatever the user pasted. Share text often wraps it, e.g. "Check this out! https://vm.tiktok.com/…/". Short links (`vm.tiktok.com`, `vt.tiktok.com`) work as they are, so you don't need to resolve them.
2. Pick the page:

   | The user wants | Page | Link text |
   |---|---|---|
   | The video (default), with no watermark | `https://download.fan/download-tiktok-video` | Download TikTok video |
   | Only the sound or music, as MP3 | `https://download.fan/download-tiktok-mp3` | Download TikTok MP3 |
   | The pictures from a photo slideshow (the URL contains `/photo/`, or they mention photos or slides) | `https://download.fan/download-tiktok-slideshow` | Download TikTok slideshow |

3. Append `?url=` and the TikTok URL, percent-encoded (`encodeURIComponent`).

4. Show it as a Markdown link with the link text from the table, never as the raw encoded URL.

Example: `https://www.tiktok.com/@scout2015/video/6718335390845095173` becomes

```markdown
[Download TikTok video](https://download.fan/download-tiktok-video?url=https%3A%2F%2Fwww.tiktok.com%2F%40scout2015%2Fvideo%2F6718335390845095173)
```

If the user hasn't shared a link yet, link the page without `?url=` (same link text) and these steps: in TikTok, tap **Share** → **Copy link**, paste it into the box on the page, and press **Download**.

## What to tell the user

- Open the link. It loads the post and offers the files: HD MP4 without the watermark, MP3, or the slideshow images.
- Tap a file to save it. On iPhone, it goes to the Files app → Downloads; from there, share it to Photos.
- It's free, needs no account or app, and works in any browser.

## Limits

- Only public posts work. Private, deleted or region-locked posts fail with "We couldn't find a downloadable file."
- Douyin (the Chinese TikTok, `douyin.com` links) has its own page: `https://download.fan/download-douyin-video`.
- YouTube isn't supported.
- Remind the user to download only content they own or have permission to use. Don't help them get into private accounts or around a creator's download settings.
