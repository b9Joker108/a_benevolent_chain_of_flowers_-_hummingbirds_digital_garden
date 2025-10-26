---
layout: default
title: "Obsidian Widget Demo"
---

# Obsidian Widget Examples

This page demonstrates the Obsidian widget for linking to and displaying Obsidian vault notes.

## Basic Obsidian Link

Link to an Obsidian note using the `obsidian://` protocol:

{% include widgets/obsidian-widget.html 
   id="basic-link" 
   title="Project Planning Notes" 
   vault_url="obsidian://open?vault=MyVault&file=Projects/Planning"
   excerpt="Central hub for project planning and coordination" %}

## With Inline Content

Display markdown content inline with a link to the full note:

{% include widgets/obsidian-widget.html 
   id="with-content" 
   title="Quick Reference Guide" 
   vault_url="obsidian://open?vault=DigitalGarden&file=References/QuickGuide"
   content="## Key Points

- Always use Git LFS for large files
- Reference external media when possible
- Keep widgets modular and reusable"
   caption="Last updated: October 2025" %}

## Web Link Alternative

For published Obsidian vaults, use regular HTTPS links:

{% include widgets/obsidian-widget.html 
   id="web-link" 
   title="Public Knowledge Base" 
   vault_url="https://publish.obsidian.md/username/Note-Title"
   excerpt="Publicly accessible version of the note" %}

## Excerpt Only

Display a preview without inline content:

{% include widgets/obsidian-widget.html 
   id="excerpt-only" 
   title="Meeting Notes Template" 
   vault_url="obsidian://open?vault=Work&file=Templates/Meetings"
   excerpt="Structured template for capturing meeting notes with attendees, agenda, decisions, and action items." %}

## Multiple Notes Reference

{% include widgets/obsidian-widget.html 
   id="note-1" 
   title="Architecture Decisions" 
   vault_url="obsidian://open?vault=TechDocs&file=ADR/001-widget-system"
   excerpt="Why we chose a modular widget architecture" %}

{% include widgets/obsidian-widget.html 
   id="note-2" 
   title="Design System" 
   vault_url="obsidian://open?vault=TechDocs&file=Design/System"
   excerpt="Color palette, typography, and component guidelines" %}

{% include widgets/obsidian-widget.html 
   id="note-3" 
   title="Deployment Guide" 
   vault_url="obsidian://open?vault=TechDocs&file=Operations/Deployment"
   excerpt="Step-by-step deployment procedures and checklists" %}

## Usage Code

```liquid
{% raw %}
{% include widgets/obsidian-widget.html 
   id="my-note" 
   title="Note Title" 
   vault_url="obsidian://open?vault=VaultName&file=Path/To/Note"
   excerpt="Short description or preview"
   content="Optional inline markdown content"
   caption="Optional caption text" %}
{% endraw %}
```

## Obsidian URI Format

The `obsidian://` protocol supports various actions:

### Open a Note
```
obsidian://open?vault=VaultName&file=Path/To/Note
```

### Search
```
obsidian://search?vault=VaultName&query=search+terms
```

### Create New Note
```
obsidian://new?vault=VaultName&file=NewNote&content=Initial+content
```

### Open Vault
```
obsidian://open?vault=VaultName
```

Learn more in the [Obsidian URI documentation](https://help.obsidian.md/Advanced+topics/Using+obsidian+URI).

## Integration Patterns

### 1. Reference External Knowledge Base

Keep your detailed notes in Obsidian, surface highlights in your digital garden:

- Link to comprehensive Obsidian notes
- Display excerpts or summaries in Jekyll
- Maintain single source of truth in Obsidian

### 2. Publish Parallel Content

Use Obsidian Publish alongside your Jekyll site:

- Deep technical docs in Obsidian Publish
- Public-facing content in Jekyll
- Link between them with the widget

### 3. Template Library

Create a library of Obsidian templates:

- Link to note templates
- Show preview of template structure
- Quick access for team members

## Best Practices

1. **Use descriptive titles**: Help users understand what's in the note
2. **Write informative excerpts**: Give context without requiring a click
3. **Keep vault URLs consistent**: Use standardized vault names
4. **Consider accessibility**: Not all users can open Obsidian links
5. **Provide web alternatives**: Use Obsidian Publish for public access

## Workflow Example

1. **Take notes in Obsidian** with rich linking and structure
2. **Create summary pages** in your Jekyll digital garden
3. **Use widgets to link** between the two systems
4. **Update Obsidian notes** as the source of truth
5. **Regenerate garden** to pull in new excerpts

## Security Note

The `obsidian://` protocol requires Obsidian to be installed locally. Links will:

- ✅ Work for users with Obsidian installed
- ❌ Not work in web browsers without the app
- ⚠️ Require user permission to open external applications

For public content, use Obsidian Publish with HTTPS links.

## Styling Customization

The widget uses a purple theme to match Obsidian's branding. Customize in `assets/css/widgets.css`:

```css
.obsidian-card {
  border-color: #7c3aed; /* Obsidian purple */
}

.obsidian-button {
  background: #7c3aed;
}
```

---

[Back to Examples]({{ '/examples/' | relative_url }}) | [Onboarding Guide]({{ '/docs/ONBOARDING.html' | relative_url }})
