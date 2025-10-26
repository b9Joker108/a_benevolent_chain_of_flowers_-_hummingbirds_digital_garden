---
layout: default
title: "Tile Layout Demo"
---

# Tile Layout Examples

This page demonstrates the tile layout system for creating responsive grid and masonry layouts.

## 3-Column Grid (Default)

<div class="tile-layout tile-layout-grid tile-columns-3 tile-gap-medium">
  <div class="tile">
    <h3>🌺 First Tile</h3>
    <p>This is a basic tile in a 3-column grid. The layout automatically adjusts to 2 columns on tablets and 1 column on mobile devices.</p>
  </div>
  
  <div class="tile">
    <h3>🌼 Second Tile</h3>
    <p>Tiles are flexible containers that can hold any content - text, images, widgets, or other HTML elements.</p>
  </div>
  
  <div class="tile">
    <h3>🌸 Third Tile</h3>
    <p>Each tile has subtle hover effects and consistent spacing for a polished appearance.</p>
  </div>
  
  <div class="tile">
    <h3>🌻 Fourth Tile</h3>
    <p>The grid automatically wraps tiles to new rows as needed.</p>
  </div>
  
  <div class="tile">
    <h3>🌹 Fifth Tile</h3>
    <p>You can include as many tiles as you need.</p>
  </div>
  
  <div class="tile">
    <h3>🌷 Sixth Tile</h3>
    <p>Mix and match different content types within tiles.</p>
  </div>
</div>

## 2-Column Grid

<div class="tile-layout tile-layout-grid tile-columns-2 tile-gap-large">
  <div class="tile">
    <h3>Wide Tile Left</h3>
    <p>A 2-column layout works well for comparing two items or showing related content side-by-side.</p>
    <p>This layout uses large gaps for more breathing room.</p>
  </div>
  
  <div class="tile">
    <h3>Wide Tile Right</h3>
    <p>Perfect for feature comparisons, before/after scenarios, or paired examples.</p>
    <p>Collapses to single column on mobile for better readability.</p>
  </div>
</div>

## 4-Column Grid

<div class="tile-layout tile-layout-grid tile-columns-4 tile-gap-small">
  <div class="tile">
    <h3>🎨 Design</h3>
    <p>Beautiful layouts</p>
  </div>
  
  <div class="tile">
    <h3>⚡ Fast</h3>
    <p>Quick loading</p>
  </div>
  
  <div class="tile">
    <h3>📱 Responsive</h3>
    <p>Mobile-friendly</p>
  </div>
  
  <div class="tile">
    <h3>♿ Accessible</h3>
    <p>For everyone</p>
  </div>
</div>

## Tiles with Rich Content

<div class="tile-layout tile-layout-grid tile-columns-3 tile-gap-medium">
  <div class="tile">
    <h3>Video Tile</h3>
    {% include widgets/video-widget.html 
       id="tile-video" 
       title="Example Video in Tile" 
       source="https://www.youtube.com/watch?v=dQw4w9WgXcQ" %}
    <p>Tiles can contain widgets like videos.</p>
  </div>
  
  <div class="tile">
    <h3>Obsidian Tile</h3>
    {% include widgets/obsidian-widget.html 
       id="tile-obsidian" 
       title="Note Reference" 
       vault_url="obsidian://open?vault=Demo&file=Example"
       excerpt="Link to Obsidian notes from tiles" %}
  </div>
  
  <div class="tile">
    <h3>Text Tile</h3>
    <ul>
      <li>Mix different content types</li>
      <li>Images, videos, text</li>
      <li>Widgets and more</li>
    </ul>
    <p><strong>Flexible and powerful!</strong></p>
  </div>
</div>

## Single Column Layout

<div class="tile-layout tile-layout-grid tile-columns-1 tile-gap-medium">
  <div class="tile">
    <h3>Full Width Tile</h3>
    <p>Single column layout is useful for stacked content that needs full width. Great for articles, documentation, or sequential information.</p>
  </div>
  
  <div class="tile">
    <h3>Another Full Width Tile</h3>
    <p>Each tile gets the full width of the container, making it easy to read and scan.</p>
  </div>
</div>

## Usage Code

### Basic Grid

```liquid
{% raw %}
<div class="tile-layout tile-layout-grid tile-columns-3 tile-gap-medium">
  <div class="tile">
    <h3>Tile Title</h3>
    <p>Tile content</p>
  </div>
  
  <div class="tile">
    <h3>Another Tile</h3>
    <p>More content</p>
  </div>
</div>
{% endraw %}
```

### With Variables

You can use Jekyll variables for dynamic layouts:

```liquid
{% raw %}
{% assign num_columns = 3 %}
{% assign gap_size = "medium" %}

<div class="tile-layout tile-layout-grid tile-columns-{{ num_columns }} tile-gap-{{ gap_size }}">
  {% for item in site.data.items %}
    <div class="tile">
      <h3>{{ item.title }}</h3>
      <p>{{ item.description }}</p>
    </div>
  {% endfor %}
</div>
{% endraw %}
```

## Configuration Options

### Columns
- `tile-columns-1` - Single column
- `tile-columns-2` - Two columns
- `tile-columns-3` - Three columns (default)
- `tile-columns-4` - Four columns

### Gap Sizes
- `tile-gap-small` - 0.5rem spacing
- `tile-gap-medium` - 1rem spacing (default)
- `tile-gap-large` - 2rem spacing

### Layout Styles
- `tile-layout-grid` - CSS Grid layout (default)
- `tile-layout-masonry` - Masonry-style layout (experimental)

## Responsive Behavior

The tile system automatically adjusts:

- **Desktop (>1024px)**: Shows configured column count
- **Tablet (768px-1024px)**: 
  - 4 columns → 2 columns
  - 3 columns → 2 columns
- **Mobile (<768px)**: All layouts → 1 column

## Best Practices

1. **Keep tile content balanced**: Similar heights look better in grid layouts
2. **Use appropriate column counts**: 
   - 1-2 for detailed content
   - 3-4 for previews or cards
3. **Choose gap sizes wisely**:
   - Small gaps for compact layouts
   - Large gaps for breathing room
4. **Test responsive behavior**: Preview on different screen sizes
5. **Combine with widgets**: Tiles work great with video, audio, and Obsidian widgets

## Accessibility

- Tiles maintain document flow for screen readers
- Keyboard navigation works naturally
- Touch-friendly on mobile devices
- Sufficient contrast in default styling

## Custom Styling

Customize tiles in your CSS:

```css
.tile {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

.tile h3 {
  color: white;
}
```

---

[Back to Examples]({{ '/examples/' | relative_url }}) | [Onboarding Guide]({{ '/docs/ONBOARDING.html' | relative_url }})
