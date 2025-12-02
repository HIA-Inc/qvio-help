# Embedding Qvio Videos on Your Website

This guide provides comprehensive instructions for embedding Qvio videos into external websites using iframes.

## Table of Contents

- [Quick Start](#quick-start)
- [Embed Code Structure](#embed-code-structure)
- [URL Parameters](#url-parameters)
- [Sizing and Responsive Design](#sizing-and-responsive-design)
- [Platform-Specific Instructions](#platform-specific-instructions)
- [Troubleshooting](#troubleshooting)
- [Security Considerations](#security-considerations)
- [Getting Your Embed Code](#getting-your-embed-code)
- [Advanced: Q&A Only Embed](#advanced-qa-only-embed)

---

## Quick Start

Copy and paste the following iframe code into your website's HTML:

```html
<iframe
  title="My Qvio Video"
  src="https://qvio.hia.ai/embed?v=YOUR_VIDEO_ID&autoplay=true"
  allow="microphone;autoplay;fullscreen"
  allowtransparency="true"
  width="1280"
  height="720"
></iframe>
```

Replace `YOUR_VIDEO_ID` with your video's short ID (found in the video's share URL).

---

## Embed Code Structure

### Complete Iframe Example

```html
<iframe
  title="488EF0D9-E229-4B3C-862D-221A8ECAC128"
  src="https://qvio.hia.ai/embed?v=jsUW-0csSje-4Yy9MRtRWw&autoplay=true"
  allow="microphone;autoplay;fullscreen"
  allowtransparency="true"
  width="100%"
  height="100%"
></iframe>
```

### Required Attributes

| Attribute           | Value                                  | Description                      |
| ------------------- | -------------------------------------- | -------------------------------- |
| `src`               | `https://qvio.hia.ai/embed?v=VIDEO_ID` | The embed URL with your video ID |
| `allow`             | `microphone;autoplay;fullscreen`       | Permissions for Qvio features    |
| `allowtransparency` | `true`                                 | Enables transparent background   |

### Recommended Attributes

| Attribute | Value            | Description                    |
| --------- | ---------------- | ------------------------------ |
| `title`   | Video name or ID | Label for the iframe           |
| `width`   | `1280` or `100%` | Width in pixels or percentage  |
| `height`  | `720` or `100%`  | Height in pixels or percentage |

---

## URL Parameters

### Video Embed (`/embed`)

| Parameter  | Required | Values           | Description                                    |
| ---------- | -------- | ---------------- | ---------------------------------------------- |
| `v`        | Yes      | Short video ID   | The unique identifier for your video           |
| `autoplay` | No       | `true` / `false` | Auto-play video when loaded (default: `false`) |

**Example URLs:**

```
# Basic embed
https://qvio.hia.ai/embed?v=jsUW-0csSje-4Yy9MRtRWw

# With autoplay enabled
https://qvio.hia.ai/embed?v=jsUW-0csSje-4Yy9MRtRWw&autoplay=true
```

---

## Sizing and Responsive Design

### Minimum Dimensions

For optimal viewing of 16:9 video content:

| Dimension | Minimum Value | Recommended |
| --------- | ------------- | ----------- |
| Width     | 320px         | 640px+      |
| Height    | 180px         | 360px+      |

**Note:** The minimum recommended size for 16:9 content is **320×180 pixels**. Below this size, video controls may become difficult to use.

### Fixed Size Embed

For a fixed 16:9 aspect ratio container:

```html
<iframe
  src="https://qvio.hia.ai/embed?v=YOUR_VIDEO_ID&autoplay=true"
  allow="microphone;autoplay;fullscreen"
  allowtransparency="true"
  width="1280"
  height="720"
  style="border: none;"
></iframe>
```

### Responsive Embed (Recommended)

To make the embed responsive, wrap the iframe in a container that maintains aspect ratio:

```html
<style>
  .qvio-container {
    position: relative;
    width: 100%;
    max-width: 1280px; /* Maximum width */
    padding-bottom: 56.25%; /* 16:9 aspect ratio (9/16 = 0.5625) */
    height: 0;
    overflow: hidden;
  }

  .qvio-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
  }

  /* Ensure minimum size for usability */
  @media (max-width: 320px) {
    .qvio-container {
      min-width: 320px;
      min-height: 180px;
    }
  }
</style>

<div class="qvio-container">
  <iframe
    title="My Qvio Video"
    src="https://qvio.hia.ai/embed?v=YOUR_VIDEO_ID&autoplay=true"
    allow="microphone;autoplay;fullscreen"
    allowtransparency="true"
  ></iframe>
</div>
```

### Responsive with Media Queries

For full control over the embed at different breakpoints:

```html
<style>
  .qvio-responsive {
    position: relative;
    width: 100%;
    padding-bottom: 56.25%; /* 16:9 default */
    height: 0;
    overflow: hidden;
  }

  .qvio-responsive iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
  }

  /* Desktop: Max width with centered alignment */
  @media (min-width: 1024px) {
    .qvio-responsive {
      max-width: 1280px;
      margin: 0 auto;
    }
  }

  /* Tablet: Full width */
  @media (min-width: 768px) and (max-width: 1023px) {
    .qvio-responsive {
      max-width: 100%;
    }
  }

  /* Mobile: Full width with minimum height */
  @media (max-width: 767px) {
    .qvio-responsive {
      min-height: 200px;
      padding-bottom: 56.25%;
    }
  }

  /* Very small screens: Fixed minimum */
  @media (max-width: 400px) {
    .qvio-responsive {
      min-height: 180px;
    }
  }
</style>

<div class="qvio-responsive">
  <iframe
    title="My Qvio Video"
    src="https://qvio.hia.ai/embed?v=YOUR_VIDEO_ID&autoplay=true"
    allow="microphone;autoplay;fullscreen"
    allowtransparency="true"
  ></iframe>
</div>
```

### Common Aspect Ratios

| Aspect Ratio | padding-bottom | Use Case                     |
| ------------ | -------------- | ---------------------------- |
| 16:9         | 56.25%         | Standard video (recommended) |
| 4:3          | 75%            | Legacy/older video content   |
| 21:9         | 42.86%         | Ultra-wide/cinematic         |
| 1:1          | 100%           | Square format                |

---

## Platform-Specific Instructions

### WordPress

WordPress has security restrictions that may block or strip iframe content. This is because WordPress sanitizes HTML in posts and pages to prevent malicious code injection. Here are solutions:

#### Option 1: HTML Block (Gutenberg Editor)

**Why this works:** The Custom HTML block bypasses WordPress's content sanitization, allowing raw HTML including iframes to be rendered directly.

1. In the block editor, click **+** to add a new block
2. Search for and select **Custom HTML**
3. Paste your iframe code
4. Preview to verify it works

#### Option 2: Embed Shortcode

**Why this works:** Shortcodes are processed server-side before content sanitization occurs. By registering a custom shortcode, you control the HTML output and WordPress trusts the output from registered shortcode functions.

Add this to your theme's `functions.php`:

```php
function qvio_embed_shortcode($atts) {
    $atts = shortcode_atts(array(
        'id' => '',
        'autoplay' => 'true',
        'width' => '100%',
        'height' => '100%'
    ), $atts);

    if (empty($atts['id'])) {
        return '<p>Error: Video ID required</p>';
    }

    $url = 'https://qvio.hia.ai/embed?v=' . esc_attr($atts['id']);
    if ($atts['autoplay'] === 'true') {
        $url .= '&autoplay=true';
    }

    return sprintf(
        '<div class="qvio-container" style="position:relative;width:%s;padding-bottom:56.25%%;height:0;overflow:hidden;">
            <iframe
                src="%s"
                allow="microphone;autoplay;fullscreen"
                allowtransparency="true"
                style="position:absolute;top:0;left:0;width:100%%;height:100%%;border:none;"
                title="Qvio Video">
            </iframe>
        </div>',
        esc_attr($atts['width']),
        esc_url($url)
    );
}
add_shortcode('qvio', 'qvio_embed_shortcode');
```

Then use in posts/pages:

```
[qvio id="jsUW-0csSje-4Yy9MRtRWw" autoplay="true"]
```

#### Option 3: Iframe Whitelist Plugin

**Why this works:** These plugins modify WordPress's HTML filtering to explicitly allow iframe tags from trusted domains, adding `qvio.hia.ai` to the allowed sources list.

If iframes are being stripped:

1. Install a plugin like **iframe** or **Advanced iFrame**
2. Configure it to allow iframes from `qvio.hia.ai`
3. Use the plugin's shortcode or settings to embed

#### WordPress Security Headers

**Why this matters:** Some WordPress hosts or security plugins add Content Security Policy (CSP) headers that restrict which domains can be embedded. If you see a blank iframe or console errors mentioning "frame-src", you need to add Qvio to your allowed frame sources.

If you manage your WordPress server, ensure these headers allow Qvio:

```apache
# In .htaccess or server config
Header set Content-Security-Policy "frame-src 'self' https://qvio.hia.ai;"
```

### Squarespace

1. Add a **Code Block** or **Embed Block**
2. Paste the responsive iframe code (including the container div and styles)
3. Switch to the page's **Page Settings > Advanced** and add the CSS

### Wix

1. Add an **HTML iframe** element from **Add > Embed > HTML iframe**
2. Click "Enter Code" and paste the iframe HTML
3. Resize the element to your desired dimensions
4. Use Wix's built-in responsive settings for mobile

### Shopify

In your Liquid template or page content:

```html
<div
  class="qvio-embed"
  style="position:relative;width:100%;padding-bottom:56.25%;height:0;"
>
  <iframe
    src="https://qvio.hia.ai/embed?v=YOUR_VIDEO_ID&autoplay=true"
    allow="microphone;autoplay;fullscreen"
    allowtransparency="true"
    style="position:absolute;top:0;left:0;width:100%;height:100%;border:none;"
    title="Qvio Video"
  ></iframe>
</div>
```

### React/Next.js

```jsx
function QvioEmbed({ videoId, autoplay = true }) {
  const src = `https://qvio.hia.ai/embed?v=${videoId}${autoplay ? "&autoplay=true" : ""}`;

  return (
    <div
      style={{
        position: "relative",
        width: "100%",
        paddingBottom: "56.25%",
        height: 0,
        overflow: "hidden",
      }}
    >
      <iframe
        src={src}
        allow="microphone;autoplay;fullscreen"
        allowTransparency={true}
        style={{
          position: "absolute",
          top: 0,
          left: 0,
          width: "100%",
          height: "100%",
          border: "none",
        }}
        title="Qvio Video"
      />
    </div>
  );
}

// Usage
<QvioEmbed videoId="jsUW-0csSje-4Yy9MRtRWw" autoplay={true} />;
```

### Vue.js

```vue
<template>
  <div class="qvio-embed">
    <iframe
      :src="embedUrl"
      allow="microphone;autoplay;fullscreen"
      allowtransparency="true"
      title="Qvio Video"
    ></iframe>
  </div>
</template>

<script>
export default {
  props: {
    videoId: { type: String, required: true },
    autoplay: { type: Boolean, default: true },
  },
  computed: {
    embedUrl() {
      const base = `https://qvio.hia.ai/embed?v=${this.videoId}`;
      return this.autoplay ? `${base}&autoplay=true` : base;
    },
  },
};
</script>

<style scoped>
.qvio-embed {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
}
.qvio-embed iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
}
</style>
```

---

## Troubleshooting

### Iframe Not Displaying

**Possible causes and solutions:**

1. **Content Security Policy (CSP) blocking**
   - Check browser console for CSP errors
   - Add `https://qvio.hia.ai` to your site's `frame-src` directive:
     ```
     Content-Security-Policy: frame-src 'self' https://qvio.hia.ai;
     ```

2. **X-Frame-Options header**
   - Ensure your server isn't setting restrictive `X-Frame-Options`
   - Qvio allows embedding from any origin

3. **HTTPS/HTTP mismatch**
   - Always use `https://qvio.hia.ai` for the embed URL
   - Your site should also use HTTPS

### Autoplay Not Working

Modern browsers restrict autoplay. Qvio handles this gracefully, but note:

- **Chrome/Edge**: Autoplay works if user has previously interacted with the domain
- **Safari**: May require user interaction first
- **Mobile browsers**: Often require explicit user tap to start playback

The video will display a play button if autoplay is blocked.

### Video Shows "Permission Denied"

- The video may be set to **Private** - only the owner can view it
- Ensure the video is set to **Public** or **Unlisted** for embedding
- Check video visibility settings in Qvio

### Sizing Issues

- Verify your container has explicit dimensions
- Use the responsive wrapper pattern for fluid layouts
- Check for conflicting CSS on your site

### Video Not Loading

- Verify the video ID is correct
- Ensure the video hasn't been deleted
- Check network connectivity to `qvio.hia.ai`

---

## Security Considerations

### Iframe Permissions

The `allow` attribute grants specific permissions to the embedded content:

| Permission   | Purpose                                        |
| ------------ | ---------------------------------------------- |
| `microphone` | Enables voice interaction features within Qvio |
| `autoplay`   | Allows video to auto-play when loaded          |
| `fullscreen` | Enables fullscreen video playback              |

These permissions are scoped only to the Qvio iframe and do not affect your parent page.

### Cross-Origin Security

- Qvio embeds use secure HTTPS connections
- No sensitive data is passed between your site and the embed
- The embed operates in an isolated browsing context

### Content Security Policy Recommendations

If your site uses CSP headers, add the following:

```
Content-Security-Policy:
  frame-src https://qvio.hia.ai;
  media-src https://qvio.hia.ai https://*.blob.core.windows.net;
```

---

## Feature Summary

| Feature           | Supported                |
| ----------------- | ------------------------ |
| Autoplay          | Yes                      |
| Fullscreen        | Yes                      |
| Voice interaction | Yes                      |
| Responsive sizing | Yes                      |
| Q&A overlay       | Yes (use `/embedqna`)    |
| Custom styling    | Limited (container only) |
| Mobile support    | Yes                      |

---

## Getting Your Embed Code

If you are the owner of the video:

1. Open your video in Qvio
2. Click the **Share** button
3. Select **Embed** in the share modal
4. Copy the provided iframe code directly — it's ready to paste into your website

The embed code includes your video's unique ID and recommended settings. You can customize the `width`, `height`, and `autoplay` attributes as needed.

### Finding the Video ID Manually

If you need just the video ID (e.g., for dynamic embedding), it's the string after `v=` in the embed URL (e.g., `jsUW-0csSje-4Yy9MRtRWw`).

---

## Advanced: Q&A Only Embed

> **Note:** This is an edge case for specialized use. Most users should use the standard `/embed` endpoint which includes both the video player and Q&A functionality.

The Q&A-only embed (`/embedqna`) displays just the interactive Q&A interface associated with a Qvio, without the video player. This is useful when you want to embed the Q&A portion separately from the video, such as in a sidebar or a dedicated Q&A section on your page.

### When to Use Q&A Only Embed

- You're displaying the video through a different player or method
- You want to show Q&A in a separate area of your page layout
- You need a text-focused interface without video playback

### Q&A Only Embed Code

```html
<iframe
  title="Qvio Q&A"
  src="https://qvio.hia.ai/embedqna?v=YOUR_VIDEO_ID"
  allow="microphone;autoplay;fullscreen"
  allowtransparency="true"
  width="400"
  height="600"
></iframe>
```

### URL Parameters

| Parameter | Required | Values         | Description                          |
| --------- | -------- | -------------- | ------------------------------------ |
| `v`       | Yes      | Short video ID | The unique identifier for your video |

### Sizing Recommendations for Q&A Embed

Unlike the video embed which uses 16:9 aspect ratio, the Q&A embed works better with a portrait or square layout:

| Layout    | Recommended Size | Use Case                |
| --------- | ---------------- | ----------------------- |
| Sidebar   | 350×500px        | Alongside other content |
| Card      | 400×400px        | Compact Q&A display     |
| Full page | 100% × 600px     | Dedicated Q&A section   |

