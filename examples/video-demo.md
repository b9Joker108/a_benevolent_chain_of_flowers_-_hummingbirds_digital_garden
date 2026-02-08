---
layout: default
title: "Video Widget Demo"
---

# Video Widget Examples

This page demonstrates the video widget capabilities with various configurations.

## YouTube Embed Example

YouTube videos are automatically detected and embedded with lazy loading:

{% include widgets/video-widget.html 
   id="youtube-demo" 
   title="Rick Astley - Never Gonna Give You Up (Official Video)" 
   source="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
   caption="Classic example video from YouTube" %}

## Alternative YouTube URL Formats

The widget supports multiple YouTube URL formats:

### Standard Watch URL
```liquid
source="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
```

### Short URL
```liquid
source="https://youtu.be/dQw4w9WgXcQ"
```

### Embed URL
```liquid
source="https://www.youtube.com/embed/dQw4w9WgXcQ"
```

## HTML5 Video Example

For direct video files (placeholder - no actual file):

{% include widgets/video-widget.html 
   id="html5-demo" 
   title="Sample Video" 
   source="/assets/video/sample.mp4"
   poster="/assets/images/video-poster.jpg"
   caption="HTML5 video player example"
   caption_url="/about-video" %}

**Note:** This is a placeholder. Actual video files should be added via Git LFS.

## With Caption and Link

Add informative captions with optional links:

{% include widgets/video-widget.html 
   id="caption-demo" 
   title="Tutorial Video" 
   source="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
   caption="Learn more about this topic"
   caption_url="/tutorials" %}

## Usage Code

```liquid
{% raw %}
{% include widgets/video-widget.html 
   id="my-video" 
   title="My Video Title" 
   source="https://www.youtube.com/watch?v=VIDEO_ID"
   caption="Optional caption text"
   caption_url="/optional-link" %}
{% endraw %}
```

## Best Practices

1. **Always include a title** for accessibility
2. **Use unique IDs** for each video on a page
3. **Provide captions** to give context
4. **Use YouTube for large videos** to save repository space
5. **Add poster images** for HTML5 videos to improve initial load

## Accessibility Features

- All videos include proper ARIA labels via the `title` parameter
- Keyboard navigation supported
- Screen reader friendly
- Responsive design adapts to screen size

---

[Back to Examples]({{ '/examples/' | relative_url }}) | [Onboarding Guide]({{ '/docs/ONBOARDING.html' | relative_url }})
