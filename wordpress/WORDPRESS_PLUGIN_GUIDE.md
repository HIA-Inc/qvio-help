# Qvio Embed - WordPress Plugin

This guide explains how to install and use the official Qvio Embed plugin for WordPress. The plugin provides native Gutenberg blocks and shortcode for embedding Qvio AI-powered interactive videos.

**Plugin URL:** [https://wordpress.org/plugins/qvio-embed/](https://wordpress.org/plugins/qvio-embed/)

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Using the Qvio Video Block](#using-the-qvio-video-block)
- [Using the Floating Button Block](#using-the-floating-button-block)
- [Using the Shortcode](#using-the-shortcode)
- [Configuration Options](#configuration-options)
- [Finding Your Video ID](#finding-your-video-id)
- [Troubleshooting](#troubleshooting)
- [Comparison with Manual Embed](#comparison-with-manual-embed)

---

## Features

### Qvio Video Block
- **Gutenberg Block**: Native WordPress editor block with live preview
- **Shortcode Support**: Works in Classic Editor, widgets, and anywhere shortcodes are supported
- **Responsive Design**: Automatically adapts to container width
- **Multiple Aspect Ratios**: 16:9, 4:3, 21:9, and 1:1 options
- **Embed Types**: Standard video player or Q&A-only mode
- **Autoplay Option**: Optional autoplay support (subject to browser policies)

### Floating Button Block
- **Floating Action Button**: A fixed-position button that opens video in a modal overlay
- **Multiple Button Styles**: Circular icon, pill with text, or bare icon (no background)
- **Custom Icons**: Choose from built-in dashicons or upload your own PNG/SVG image
- **Flexible Positioning**: Place in any corner with custom offsets
- **Modal Options**: Centered overlay or slide-in panels from left/right
- **Customizable Colors**: Background, text, and hover colors
- **Accessibility**: Full keyboard navigation and ARIA support

---

## Requirements

- WordPress 5.8 or higher
- PHP 7.4 or higher
- A Qvio account with video content

---

## Installation

### Method 1: Install from WordPress.org (Recommended)

1. Go to **Plugins** > **Add New** in your WordPress admin
2. Search for "Qvio Embed"
3. Click **Install Now** on the Qvio Embed plugin
4. Click **Activate**

Or install directly from [https://wordpress.org/plugins/qvio-embed/](https://wordpress.org/plugins/qvio-embed/)

### Method 2: Install via Zip Upload

If you prefer manual installation or need a specific version:

1. **Download the plugin**
   - Go to the [WordPress.org plugin page](https://wordpress.org/plugins/qvio-embed/)
   - Click **Download** to get the latest `qvio-embed.zip`

2. **Upload to WordPress**
   - In your WordPress admin, go to **Plugins** > **Add New**
   - Click **Upload Plugin** at the top of the page
   - Click **Choose File** and select the `qvio-embed.zip` file
   - Click **Install Now**

3. **Activate the plugin**
   - After installation completes, click **Activate Plugin**
   - You'll see "Qvio Embed" in your installed plugins list

---

## Using the Qvio Video Block

The Qvio Video block is the recommended way to embed Qvio videos inline on your WordPress pages.

### Adding a Video

1. **Open the block editor** on any post or page
2. **Add a new block** by clicking the **+** button
3. **Search for "Qvio"** in the block inserter
4. **Select "Qvio Video"** from the results

### Configuring the Block

Once added, you'll see the block settings in the right sidebar:

| Setting | Description |
|---------|-------------|
| **Video ID** | Enter your Qvio video ID or paste a full Qvio URL |
| **Playlist ID** | Enter a Qvio playlist ID to embed a playlist |
| **Playlist Sidebar** | Control playlist sidebar visibility: Auto (default), Force Open, or Force Collapsed |
| **Aspect Ratio** | Choose from 16:9 (default), 4:3, 21:9, or 1:1 |
| **Embed Type** | Select "Video" for full player or "Q&A Only" for the Q&A interface |
| **Autoplay** | Toggle to enable/disable autoplay |

> **Note:** You can enter just a Playlist ID (without a Video ID) to embed a playlist starting on its first video. The Playlist Sidebar setting only appears when a Playlist ID is entered and embed type is "Video".

### Block Features

- **Live Preview**: See your video in the editor before publishing
- **Visual Selection**: Click the block to easily select and configure it
- **Drag and Drop**: Reposition the block like any other WordPress block
- **Copy/Paste**: Duplicate configured blocks across posts

### Example Block Usage

1. Add the Qvio Video block
2. Enter video ID: `jsUW-0csSje-4Yy9MRtRWw`
3. Set aspect ratio to 16:9
4. Enable autoplay if desired
5. Preview or publish your post

---

## Using the Floating Button Block

The Floating Button block creates a fixed-position button that opens your Qvio video in a modal overlay. This is ideal for call-to-action buttons, help videos, or promotional content that should be accessible from anywhere on the page.

### Adding a Floating Button

1. **Open the block editor** on any post or page
2. **Add a new block** by clicking the **+** button
3. **Search for "Qvio"** in the block inserter
4. **Select "Qvio Floating Button"** from the results
5. **Enter your video ID** in the placeholder or sidebar settings

### Block Settings

The Floating Button has four settings panels in the sidebar:

#### Video Settings

| Setting | Description |
|---------|-------------|
| **Video ID or URL** | Enter your Qvio video ID or paste a full Qvio URL |
| **Embed Type** | Select "Full Video Player" or "Q&A Only" |
| **Autoplay on Open** | Start video automatically when modal opens |

#### Button Appearance

| Setting | Description |
|---------|-------------|
| **Button Style** | Choose from three styles (see below) |
| **Button Icon** | Select a dashicon or upload a custom image (PNG, SVG, GIF, WebP) |
| **Button Size / Icon Size** | Small, Medium, Large presets, or custom pixel size for bare style |
| **Background Color** | Button background color (not applicable for bare style) |
| **Icon/Text Color** | Color of the icon and label text |
| **Hover Background** | Background color on mouse hover |

##### Button Styles

| Style | Description |
|-------|-------------|
| **Icon Only (Circular)** | A circular floating action button with just an icon |
| **Icon + Text (Pill)** | A pill-shaped button with icon and text label |
| **Bare Icon (No Background)** | Just the icon with no background, border, or shadow - supports custom sizing from 16px to 320px |

#### Button Position

| Setting | Description |
|---------|-------------|
| **Position** | Bottom Right, Bottom Left, Top Right, Top Left, or Custom |
| **Horizontal Offset** | Distance from the edge (0-200px) |
| **Vertical Offset** | Distance from the edge (0-200px) |
| **Z-Index** | Stack order (higher values appear above other elements) |

#### Modal Settings

| Setting | Description |
|---------|-------------|
| **Modal Type** | Centered Overlay, Slide from Left, or Slide from Right |
| **Modal Size** | Small, Medium, Large, or Custom dimensions |
| **Custom Width/Height** | Pixel dimensions when using Custom size |
| **Backdrop Opacity** | Darkness of the background overlay (0-1) |
| **Show Close Button** | Display an X button to close the modal |
| **Close on Backdrop Click** | Close modal when clicking outside the video |
| **Close on ESC Key** | Close modal when pressing the Escape key |

### Custom Icon Upload

You can use your own image as the button icon:

1. In **Button Appearance**, click the icon picker
2. Select the **Upload** tab
3. Click **Upload Image** and select your file
4. Supported formats: PNG, SVG, GIF, WebP
5. Recommended: Square images with transparent backgrounds work best

To remove a custom icon, click **Remove** in the upload preview and select a dashicon instead.

### Example: Help Video Button

Create a help button in the bottom-right corner:

1. Add the Qvio Floating Button block
2. Enter your help video ID
3. Set **Button Style** to "Icon + Text (Pill)"
4. Set **Button Label** to "Need Help?"
5. Select the **editor-help** (question mark) icon
6. Set **Position** to "Bottom Right"
7. Configure modal as "Centered Overlay" with "Large" size
8. Preview or publish your post

### Example: Bare Icon Promo

Create a minimal branded icon button:

1. Add the Qvio Floating Button block
2. Enter your promo video ID
3. Set **Button Style** to "Bare Icon (No Background)"
4. Upload your brand logo as a custom icon
5. Set **Icon Size** to your desired pixel size (e.g., 64px)
6. Set **Icon Color** to match your brand
7. Position in the desired corner

---

## Using the Shortcode

The shortcode works in the Classic Editor, text widgets, and anywhere shortcodes are processed.

### Basic Shortcode

```
[qvio id="YOUR_VIDEO_ID"]
```

### Shortcode with Options

```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" autoplay="true" aspect="16:9" type="video"]
```

### Shortcode Parameters

| Parameter | Values | Default | Description |
|-----------|--------|---------|-------------|
| `id` | Video ID or URL | — | Your Qvio video ID or full video URL |
| `playlist` | Playlist ID | — | Qvio playlist ID |
| `collapsed` | `true`, `false` | `false` | Start with playlist sidebar collapsed |
| `autoplay` | `true`, `false` | `false` | Auto-start video when loaded |
| `aspect` | `16:9`, `4:3`, `21:9`, `1:1` | `16:9` | Video aspect ratio |
| `type` | `video`, `qna` | `video` | Embed type (full player or Q&A only) |

> **Note:** At least one of `id` or `playlist` is required.

### Shortcode Examples

**Basic embed:**
```
[qvio id="jsUW-0csSje-4Yy9MRtRWw"]
```

**With autoplay enabled:**
```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" autoplay="true"]
```

**Q&A only mode:**
```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" type="qna"]
```

**Custom aspect ratio:**
```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" aspect="4:3"]
```

**Full URL instead of ID:**
```
[qvio id="https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw"]
```

**Playlist embed (starts on first video):**
```
[qvio playlist="YOUR_PLAYLIST_ID"]
```

**Specific video in a playlist:**
```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" playlist="YOUR_PLAYLIST_ID"]
```

**Playlist with sidebar collapsed:**
```
[qvio playlist="YOUR_PLAYLIST_ID" collapsed="true"]
```

---

## Configuration Options

### Aspect Ratios

Choose the aspect ratio that matches your video content:

| Aspect Ratio | Best For | Notes |
|--------------|----------|-------|
| **16:9** | Standard videos | Most common, recommended default |
| **4:3** | Legacy content | Traditional TV/older recordings |
| **21:9** | Cinematic content | Ultra-wide format |
| **1:1** | Square format | Social media style content |

### Embed Types

| Type | Description | Use Case |
|------|-------------|----------|
| **Video** | Full video player with controls | Standard video embedding |
| **Q&A Only** | Interactive Q&A interface only | When video is displayed separately, or for text-focused interaction |

### Autoplay Behavior

When autoplay is enabled:
- Video attempts to start automatically when the page loads
- Modern browsers may block autoplay with sound due to browser policies
- If blocked, a play button appears for manual start
- Works reliably when users have previously interacted with your site

---

## Finding Your Video ID

You can use either the video ID or full URL with this plugin.

### Option 1: Use the Full URL

1. Open your video in Qvio
2. Copy the URL from your browser's address bar (e.g., `https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw`)
3. Paste the entire URL as the `id` value

### Option 2: Use Just the Video ID

1. Open your video in Qvio
2. Look at the URL - the video ID is the value after `v=`
3. For example, in `https://qvio.hia.ai/watch?v=jsUW-0csSje-4Yy9MRtRWw`, the ID is `jsUW-0csSje-4Yy9MRtRWw`

### Option 3: Use the Share Button

1. Open your video in Qvio
2. Click the **Share** button
3. The video ID is displayed in the share dialog
4. Copy and paste into the plugin

---

## Troubleshooting

### Video Not Displaying

**Check the video ID:**
- Verify the video ID is correct and the video exists
- Try pasting the full URL instead of just the ID
- Ensure the video is set to Public or Unlisted (not Private)

**Check plugin activation:**
- Go to **Plugins** and verify Qvio Embed is activated
- Deactivate and reactivate if needed

### Block Not Appearing in Editor

1. Clear your browser cache
2. Check for JavaScript errors in the browser console (F12 > Console)
3. Ensure WordPress is version 5.8 or higher
4. Try deactivating other plugins temporarily to check for conflicts

### Autoplay Not Working

This is usually due to browser autoplay policies:

- **Chrome/Edge**: Autoplay works if the user has previously interacted with your site
- **Safari**: Often requires explicit user interaction
- **Mobile browsers**: Typically require a tap to start playback

The video will show a play button if autoplay is blocked.

### "Plugin file does not exist" Error During Installation

This error occurs when the zip file structure is incorrect:

1. Ensure you downloaded the official `qvio-embed.zip` file
2. Do not extract and re-zip the file yourself
3. The zip must contain a `qvio-embed/` folder as the root

### Shortcode Shows as Text

If the shortcode displays as plain text instead of a video:

1. Verify the plugin is activated
2. Check you're not inside a code block or preformatted text
3. Ensure shortcodes are enabled for your content type

### Blank Space Where Video Should Be

1. Check browser console for CSP (Content Security Policy) errors
2. Verify your site's security settings allow frames from `qvio.hia.ai`
3. If using a caching plugin, clear the cache

---

## Comparison with Manual Embed

| Feature | Qvio Plugin | Manual iframe |
|---------|-------------|---------------|
| **Installation** | One-time plugin install | Code snippet per video |
| **Configuration** | Visual settings panel | Edit HTML attributes |
| **Responsive** | Automatic | Requires wrapper CSS |
| **Block Editor** | Native block with preview | Custom HTML block only |
| **Maintenance** | Plugin updates | Manual code updates |
| **Best for** | Regular Qvio users | One-off embeds |

### When to Use the Plugin

- You embed Qvio videos frequently
- You want a visual, no-code embedding experience
- You prefer native WordPress block integration
- You want automatic responsive handling

### When to Use Manual iframe

- You only need to embed one or two videos
- You need custom styling or advanced iframe attributes
- You want to avoid adding another plugin

For manual embedding instructions, see the [Embedding Qvio Videos Guide](../embedding/EMBEDDING_QVIO_GUIDE.md).

---

## Related Documentation

- [Embedding Qvio Videos](../embedding/EMBEDDING_QVIO_GUIDE.md) - Manual embedding guide for all platforms
- [Watch Page URL Parameters](../sharing/WATCH_PAGE_URL_PARAMETERS.md) - URL parameters for sharing links

---

## Support

If you encounter issues:

1. Check the [Troubleshooting](#troubleshooting) section above
2. Verify your WordPress and PHP versions meet the requirements
3. Contact Qvio support for video-specific issues
