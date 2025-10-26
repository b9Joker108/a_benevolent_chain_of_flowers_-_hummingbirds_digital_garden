# Quick Start Guide

Welcome to your digital garden! This guide will help you get started quickly.

## Setup

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd a_benevolent_chain_of_flowers_-_hummingbirds_digital_garden
   ```

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Run locally**
   ```bash
   bundle exec jekyll serve
   ```
   
4. **Visit your site**
   Open `http://localhost:4000` in your browser

## Creating Content

### Quick Method

Use the templates in `.templates/` directory:

```bash
# Create a new seed
cp .templates/seed-template.md _seeds/my-new-idea.md

# Create a new note
cp .templates/note-template.md _notes/my-learning.md

# Create a new thought
cp .templates/thought-template.md _thoughts/my-reflection.md
```

Then edit the file and fill in:
- `title`: Your content title
- `date`: YYYY-MM-DD format
- `tags`: Array of relevant tags
- Content: Write in Markdown

### Manual Method

Create a new `.md` file in the appropriate directory with this structure:

```markdown
---
title: Your Title Here
date: 2024-01-15
tags: [tag1, tag2]
---

# Your Title Here

Your content goes here...
```

## Collections Explained

### 🌱 Seeds (`_seeds/`)
- New, unformed ideas
- Quick thoughts and observations
- Starting points for future development
- Don't need to be complete or polished

### 📝 Notes (`_notes/`)
- More developed concepts
- Learning summaries
- Synthesis of information
- Referenced and structured knowledge

### 💭 Thoughts (`_thoughts/`)
- Personal reflections
- Insights and realizations
- Philosophical musings
- Subjective experiences

## Tips

1. **Link Everything**: Use `[[note-name]]` or standard Markdown links to connect ideas
2. **Tag Liberally**: Tags help you find related content later
3. **Iterate Often**: Update and refine your notes over time
4. **Don't Aim for Perfect**: This is a garden, not a museum
5. **Make it Personal**: Your voice and perspective are what make this unique

## Publishing

### To GitHub Pages

1. Push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Add new content"
   git push
   ```

2. Enable GitHub Pages in repository settings:
   - Go to Settings > Pages
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)

3. The GitHub Actions workflow will automatically build and deploy your site

Your site will be available at:
`https://<username>.github.io/<repository-name>/`

## Common Tasks

### Adding an image
1. Place image in `assets/images/`
2. Reference in Markdown: `![Alt text](/assets/images/my-image.png)`

### Changing site title or description
Edit `_config.yml`:
```yaml
title: Your New Title
description: Your new description
```

### Modifying styling
Edit `assets/css/style.css`

### Adding a new page
Create `my-page.md` in the root directory:
```markdown
---
layout: default
title: My Page
---

# My Page

Content here...
```

## Need Help?

- Check [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines
- Read [README.md](README.md) for full documentation
- Open an issue on GitHub for questions

Happy gardening! 🌸
