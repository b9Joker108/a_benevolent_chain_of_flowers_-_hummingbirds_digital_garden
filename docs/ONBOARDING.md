---
layout: onboarding
title: "Onboarding Guide"
description: "Get started with the Digital Garden widgets and features"
---

# Welcome to the Digital Garden! 🌺

This guide will help you understand and use the modular widget system, tile layouts, and content management features available in this digital garden.

## Getting Started {#getting-started}

This digital garden is built with Jekyll and includes several modular components to help you create rich, interactive content:

- **Video Widget**: Embed YouTube videos or HTML5 video players
- **Audio Widget**: Stream audio content with HTML5 audio players
- **Obsidian Widget**: Link to Obsidian vault notes
- **Tile Layout**: Create responsive grid and masonry layouts

## Using Widgets {#widgets}

### Video Widget

The video widget supports both YouTube embeds and direct HTML5 video files:

```liquid
{% raw %}
{% include widgets/video-widget.html 
   id="demo-video" 
   title="Demo Video" 
   source="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
   caption="Watch this demo"
   caption_url="/more-info" %}
{% endraw %}
```

**Parameters:**
- `id` (required): Unique identifier for the video
- `title` (optional): Video title for accessibility
- `source` (required): YouTube URL or direct video file URL
- `poster` (optional): Thumbnail image for HTML5 video
- `caption` (optional): Caption text below video
- `caption_url` (optional): Make caption a clickable link

**YouTube Support:**
- Automatically detects YouTube URLs
- Supports multiple URL formats: `youtube.com/watch?v=`, `youtu.be/`, `youtube.com/embed/`
- Uses lazy loading for better performance

### Audio Widget

The audio widget provides streaming audio playback:

```liquid
{% raw %}
{% include widgets/audio-widget.html 
   id="podcast" 
   title="Episode 1" 
   source="https://example.com/audio/episode1.mp3"
   caption="Latest episode" %}
{% endraw %}
```

**Parameters:**
- `id` (required): Unique identifier for the audio player
- `title` (optional): Audio title
- `source` (required): URL to audio file (mp3, ogg, or wav)
- `caption` (optional): Caption text
- `caption_url` (optional): Make caption a clickable link
- `autoplay` (optional): Enable autoplay (default: false)

**Note:** Audio files should be stored externally or managed via Git LFS. See [Git LFS Setup](#git-lfs) below.

### Obsidian Widget

Link to Obsidian vault notes or display excerpts:

```liquid
{% raw %}
{% include widgets/obsidian-widget.html 
   id="project-note" 
   title="Project Structure" 
   vault_url="obsidian://open?vault=MyVault&file=project"
   excerpt="Quick reference to project organization"
   content="# Overview\n\nKey points about the project..." %}
{% endraw %}
```

**Parameters:**
- `id` (required): Unique identifier
- `title` (optional): Note title
- `vault_url` (optional): Obsidian URI or web link
- `content` (optional): Markdown content to display inline
- `excerpt` (optional): Short preview text
- `caption` (optional): Caption text

### Tile Layout

Create responsive grid layouts for your content:

```html
<div class="tile-layout tile-layout-grid tile-columns-3 tile-gap-medium">
  <div class="tile">
    <h3>Tile 1</h3>
    <p>Content here</p>
  </div>
  <div class="tile">
    <h3>Tile 2</h3>
    <p>More content</p>
  </div>
</div>
```

**Parameters:**
- `columns` (optional): Number of columns (1-4, default: 3)
- `gap` (optional): Spacing between tiles (small/medium/large, default: medium)
- `style` (optional): Layout style (grid/masonry, default: grid)

**Responsive Behavior:**
- 4 columns → 2 columns on tablets
- 3+ columns → 2 columns on tablets
- 2+ columns → 1 column on mobile

## Layouts {#layouts}

### Default Layout

The `default` layout includes:
- Responsive navigation
- Widget CSS styles automatically loaded
- SEO optimization
- Feed meta tags

### Onboarding Layout

The `onboarding` layout is optimized for documentation pages with:
- Sidebar navigation
- Sticky table of contents
- Help section
- Responsive design

Use it in your page front matter:

```yaml
---
layout: onboarding
title: "Your Page Title"
description: "Page description"
---
```

## Examples {#examples}

Check the `/examples/` directory for working demonstrations:

- `video-demo.md` - Video widget examples
- `audio-demo.md` - Audio streaming examples
- `obsidian-demo.md` - Obsidian integration examples
- `tile-demo.md` - Tile layout examples

## Git LFS Setup {#git-lfs}

### What is Git LFS?

Git Large File Storage (LFS) is a Git extension for versioning large files. Instead of storing large binary files directly in your repository, Git LFS stores pointers to files in a separate storage location.

### When to Use Git LFS

Use Git LFS for:
- Audio files (mp3, wav, ogg, flac)
- Video files (mp4, mov, avi)
- Large images
- Any binary file over 1MB

### Configuration Files

This repository includes Git LFS scaffolding:

**.gitattributes** - Defines which file types use LFS:
```
*.mp3 filter=lfs diff=lfs merge=lfs -text
*.wav filter=lfs diff=lfs merge=lfs -text
*.mp4 filter=lfs diff=lfs merge=lfs -text
```

**.lfsconfig** - LFS-specific settings

### Enabling Git LFS

**Repository owners should:**

1. Install Git LFS on your system:
   ```bash
   # macOS
   brew install git-lfs
   
   # Ubuntu/Debian
   sudo apt-get install git-lfs
   
   # Windows (use Git for Windows installer)
   ```

2. Enable Git LFS in the repository:
   ```bash
   git lfs install
   ```

3. Verify LFS is tracking the correct files:
   ```bash
   git lfs track
   ```

4. Push LFS objects:
   ```bash
   git lfs push --all origin main
   ```

### Storage Considerations

- GitHub provides 1GB of free LFS storage and 1GB/month bandwidth
- Additional packs available for purchase
- Consider external hosting for large media libraries

### Alternative: External Hosting

For large media files, consider:
- YouTube for videos
- SoundCloud or external CDN for audio
- Cloudinary or similar for images

Link to external content using the widget `source` parameter.

## Best Practices

### Content Organization

```
/
├── _includes/widgets/     # Widget templates
├── _layouts/              # Page layouts
├── examples/              # Demo pages
├── docs/                  # Documentation
├── assets/
│   ├── css/              # Stylesheets
│   ├── audio/            # Audio files (LFS)
│   └── video/            # Video files (LFS)
└── content/              # Your content pages
```

### Performance Tips

1. **Use lazy loading**: YouTube embeds load lazily by default
2. **Optimize media**: Compress audio/video before adding
3. **Use external hosting**: For frequently accessed files
4. **Enable caching**: Configure CDN for static assets

### Accessibility

1. Always provide `title` attributes for widgets
2. Include captions for media content
3. Ensure keyboard navigation works
4. Test with screen readers

## CI/CD Validation {#ci}

The repository includes a GitHub Actions workflow (`.github/workflows/validate.yml`) that:

- Validates Jekyll configuration
- Checks for broken links
- Validates HTML output
- Tests widget rendering

**Note:** Repository owners must enable Actions in repository settings.

## Troubleshooting

### Jekyll Build Errors

Check your `_config.yml`:
```yaml
plugins:
  - jekyll-feed
  - jekyll-seo-tag
```

### Widgets Not Rendering

1. Verify include path: `_includes/widgets/`
2. Check parameter syntax: Use `key="value"` format
3. Validate Liquid syntax

### LFS Issues

```bash
# Re-fetch LFS objects
git lfs fetch --all

# Check LFS status
git lfs status
```

## Next Steps

1. Review the [examples/]({{ '/examples/' | relative_url }}) directory
2. Create your first content page
3. Experiment with different widget combinations
4. Set up Git LFS for your media files

## Contributing

Suggestions for improvements? Open an issue or submit a pull request!

---

**Happy gardening! 🌸🌼🌺**
