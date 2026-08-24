# Qvio Watch Page URL Parameters

This guide explains the URL parameters available when sharing Qvio video links. Use these parameters to customize how shared videos are displayed and played.

## Table of Contents

- [Quick Start](#quick-start)
- [URL Structure](#url-structure)
- [Available Parameters](#available-parameters)
- [Examples](#examples)
- [Sharing from the Qvio Platform](#sharing-from-the-qvio-platform)
- [Comparison with Embed URLs](#comparison-with-embed-urls)

---

## Quick Start

A basic Qvio watch page URL looks like this:

```
https://qvio.hia.ai/watch?v=YOUR_VIDEO_ID
```

> **Tip:** You don't need to construct these URLs manually. Use the **Share** button in the Qvio platform to get your video or playlist share link with the correct ID already included. See [Sharing from the Qvio Platform](#sharing-from-the-qvio-platform) for details.

Add parameters to customize playback:

```
https://qvio.hia.ai/watch?v=YOUR_VIDEO_ID&startTime=30&ap=true
```

---

## URL Structure

```
https://qvio.hia.ai/watch?v={videoId}&startTime={seconds}&p={playlistId}&ap={true|false}
```

The base URL is always `https://qvio.hia.ai/watch` followed by query parameters.

---

## Available Parameters

### Required Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `v` | **Video ID** - The unique short ID for your video. Found in the share URL or video settings. | `v=jsUW-0csSje-4Yy9MRtRWw` |

### Optional Parameters

| Parameter | Description | Values | Default |
|-----------|-------------|--------|---------|
| `startTime` | Start playback at a specific time (in seconds) | Any positive number | `0` |
| `ap` | Enable autoplay when the page loads | `true` or `false` | `false` |
| `p` | Playlist ID - Display the video within a playlist context, showing the playlist panel | Playlist short ID | None |
| `trackId` | Analytics tracking ID for attributing views to specific campaigns or sources | Any string | None |
| `playlistAutoScroll` | When viewing a playlist, auto-scroll to the current video in the playlist panel | `true` or `false` | `false` |
| `cp` | Continuous playlist mode - hide the playlist panel and play the playlist as one continuous presentation, advancing automatically from each video to the next. Requires `p` | `true` (only value that enables it) | `false` |

---

## Examples

### Basic Video Link

Share a video starting from the beginning:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw
```

### Start at Specific Time

Share a video starting at 1 minute and 30 seconds (90 seconds):

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&startTime=90
```

### Autoplay Enabled

Share a video that plays automatically when opened:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&ap=true
```

> **Note:** When autoplay is enabled, browsers may start the video muted due to autoplay policies. A prompt will appear allowing viewers to unmute.

### Start Time with Autoplay

Share a video that autoplays from a specific timestamp:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&startTime=120&ap=true
```

### Video in a Playlist

Share a video within the context of a playlist. The playlist panel will be visible, showing all videos in the playlist:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&p=abc123PlaylistId
```

### Playlist with Auto-Scroll

When sharing a video deep in a playlist, use `playlistAutoScroll` to automatically scroll the playlist panel to show the current video:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&p=abc123PlaylistId&playlistAutoScroll=true
```

### Continuous Playlist Mode

Share a playlist as one continuous presentation. The playlist panel is hidden and each video advances automatically into the next, while the player's chapter navigation (previous/next buttons and the chapter menu) remains available:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&p=abc123PlaylistId&cp=true
```

> **Note:** `cp=true` does not start playback on its own - combine it with `ap=true` to also autoplay the first video.

### Analytics Tracking

Track views from a specific marketing campaign or source:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&trackId=summer-campaign-2025
```

### Combined Parameters

Share a video in a playlist, starting at 45 seconds with autoplay and analytics tracking:

```
https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw&p=abc123PlaylistId&startTime=45&ap=true&trackId=newsletter
```

---

## Sharing from the Qvio Platform

The easiest way to create share links is using the **Share** button in the Qvio platform. You don't need to manually construct URLs - the platform generates them for you with the correct video or playlist IDs.

### Sharing a Video

1. Open any video on the Watch page
2. Click the **Share** button (share icon) in the video player or page header
3. The share dialog opens with your video's link ready to copy
4. Optionally enable **"Start at current time"** to include the `startTime` parameter
5. Click **Copy Link** to copy the URL to your clipboard

### Sharing a Playlist

1. Open a playlist from your library
2. Click the **Share** button on the playlist page
3. The share dialog generates a link to the playlist
4. Click **Copy Link** to copy the URL

When sharing a playlist, the link will include the playlist ID. If you're viewing a specific video within the playlist, the link will include both the video ID and playlist ID so viewers see the video in context.

The exact link shape depends on whether a video in the playlist is currently open:

- **A playlist video is open** - the link is a watch URL carrying both IDs (`/watch?v=VIDEO_ID&p=PLAYLIST_ID`).
- **No video is open** - the link points at the playlist page itself (`/playlists?v=PLAYLIST_ID`), which has no player. **Play as continuous video** is not offered in this case, because `cp` has no player to act on.

### Sharing a Video Within a Playlist

When watching a video that's part of a playlist:

1. Click the **Share** button while the video is playing
2. The generated link includes both the video (`v=`) and playlist (`p=`) parameters
3. Recipients will see the video with the playlist panel visible

### Share Dialog Options

The dialog is organized into tabs:

| Tab | Result |
|--------|--------|
| Social | Shares the watch link to a social network. Where the network supports it, the post is prefilled with the Qvio name |
| Embed | Generates iframe code for embedding, using the `/embed` URL. Available for both video and playlist shares, and only when embed link sharing is enabled for the team |
| QR Code | Downloads a QR code image for the watch link |
| Unique Codes | Issues per-share tracking codes and copies a watch link with `&trackId=` already appended, for attributing views to a specific recipient or campaign |

Options that apply to the generated link:

| Option | Result |
|--------|--------|
| Copy Link | Copies the watch page URL to clipboard with appropriate video/playlist IDs |
| Start at current time | Adds `&startTime=X` to the watch link based on current playback position. It does not affect embed code - `/embed` ignores `startTime` |
| Play as continuous video (hide playlist panel) | Adds `&cp=true` to the share link and embed code - playlist shares only, and only when the playlist has a current video to link to |

---

## Comparison with Embed URLs

Qvio provides two types of URLs for different use cases:

| Feature | Watch Page (`/watch`) | Embed Page (`/embed`) |
|---------|----------------------|----------------------|
| **Use case** | Direct sharing, social media | Embedding in websites via iframe |
| **URL format** | `/watch?v=ID` | `/embed?v=ID` |
| **Autoplay param** | `ap=true` | `ap=true` (legacy `autoplay=true` still honored) |
| **Start time** | Yes (`startTime=X`) | No - ignored on `/embed` |
| **Playlist support** | Yes (`p=ID`) | Yes (`p=ID`) |
| **Continuous playlist** | Yes (`cp=true`) | Yes (`cp=true`) |
| **Playlist sidebar control** | No | Yes (`plc`) |
| **Playlist auto-scroll** | Yes (`playlistAutoScroll=true`) | Yes (`playlistAutoScroll=true`) |
| **Analytics tracking** | Yes (`trackId=X`) | Yes (`trackId=X`) |
| **Full Qvio UI** | Yes (header, Q&A panel, etc.) | Minimal (video player only) |

### When to Use Each

- **Watch Page** (`/watch`): Use for sharing links via email, social media, messaging apps, or anywhere users will click to open in a new browser tab. Provides the full Qvio experience including Q&A interaction.

- **Embed Page** (`/embed`): Use when embedding videos directly into your website or application using an iframe. Provides a minimal, focused video player experience.

---

## Tips

1. **Short IDs**: Video and playlist IDs in URLs are shortened versions of the full UUID. The platform handles the conversion automatically when you use the Share button.

2. **Time Format**: The `startTime` parameter uses seconds. Common conversions:
   - 1 minute = `startTime=60`
   - 2 minutes 30 seconds = `startTime=150`
   - 1 hour = `startTime=3600`

3. **Browser Autoplay Policies**: Most modern browsers block autoplay with sound. When `ap=true` is used, videos may start muted. Viewers will see a prompt to unmute the video.

4. **Playlist Links**: When sharing a playlist link without a specific video (`p` without `v`), the first video in the playlist will be loaded automatically.

5. **URL Encoding**: Special characters in parameter values should be URL-encoded. Most sharing scenarios won't require manual encoding.

---

## Related Documentation

- [Embedding Qvio Videos](../embedding/EMBEDDING_QVIO_GUIDE.md) - Complete guide for embedding videos in websites using iframes
