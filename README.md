# a_benevolent_chain_of_flowers_-_hummingbirds_digital_garden

Beauford A. Stenberg's digital garden 🌺🌼🌸

A Jekyll-powered digital garden featuring modular widgets for rich multimedia content, tile-based layouts, and seamless integration with external tools like Obsidian.

## 🚀 Quick Start

This repository includes scaffolding for:

- **Modular Widgets**: Video (YouTube & HTML5), Audio, and Obsidian note embedding
- **Tile Layouts**: Responsive grid and masonry layouts for content organization
- **Git LFS Support**: Configuration for managing large audio/video files
- **CI Validation**: Automated GitHub Actions workflow for quality checks

## 📚 Documentation

- **[Onboarding Guide](docs/ONBOARDING.md)** - Comprehensive guide to using all features
- **[Examples](examples/)** - Working demonstrations of all widgets and layouts
  - [Video Widget Demo](examples/video-demo.md)
  - [Audio Widget Demo](examples/audio-demo.md)
  - [Obsidian Widget Demo](examples/obsidian-demo.md)
  - [Tile Layout Demo](examples/tile-demo.md)

## 🧩 Widgets Scaffolding

This repository provides ready-to-use widget templates:

### Video Widget
Embed YouTube videos or HTML5 video players with lazy loading and responsive design.

```liquid
{% include widgets/video-widget.html 
   id="my-video" 
   title="Video Title" 
   source="https://www.youtube.com/watch?v=VIDEO_ID" %}
```

### Audio Widget
Stream audio content with HTML5 audio controls.

```liquid
{% include widgets/audio-widget.html 
   id="my-audio" 
   title="Audio Title" 
   source="/assets/audio/file.mp3" %}
```

### Obsidian Widget
Link to Obsidian vault notes with previews.

```liquid
{% include widgets/obsidian-widget.html 
   id="my-note" 
   title="Note Title" 
   vault_url="obsidian://open?vault=MyVault&file=Note" %}
```

### Tile Layout
Create responsive grid layouts for your content.

```html
<div class="tile-layout tile-layout-grid tile-columns-3 tile-gap-medium">
  <div class="tile">Content here</div>
</div>
```

## 🛠️ Local Development

1. Install Jekyll and dependencies:
   ```bash
   gem install bundler jekyll
   bundle install
   ```

2. Run the development server:
   ```bash
   bundle exec jekyll serve
   ```

3. Visit `http://localhost:4000` in your browser

## 📦 Git LFS Setup

For managing large media files (audio/video):

1. Install Git LFS: `brew install git-lfs` (macOS) or `apt-get install git-lfs` (Linux)
2. Enable LFS: `git lfs install`
3. Verify tracking: `git lfs track`

See the [Onboarding Guide](docs/ONBOARDING.md#git-lfs) for detailed instructions.

## 🧪 Testing

The repository includes a CI workflow (`.github/workflows/validate.yml`) that:
- Validates Jekyll configuration
- Checks for required files and directories
- Builds the site
- Performs basic quality checks

## 📝 License

See [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions welcome! Please open an issue or submit a pull request.

---

**Happy gardening! 🌺**
