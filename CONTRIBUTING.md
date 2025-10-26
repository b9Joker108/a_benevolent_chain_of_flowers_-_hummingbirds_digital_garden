# Contributing to the Digital Garden

Thank you for your interest in contributing to this digital garden! 

## Philosophy

This is a personal knowledge garden, but suggestions and contributions are welcome. The goal is to create a space for learning and growing ideas together.

## How to Contribute

### Suggesting Ideas

If you have ideas for new topics or improvements:
1. Open an issue describing your suggestion
2. Provide context and reasoning
3. Link to relevant resources if applicable

### Fixing Errors

Found a typo or factual error?
1. Fork the repository
2. Make your correction
3. Submit a pull request with a clear description

### Adding Content

Want to add a note or seed?
1. Follow the existing structure in `_notes/`, `_seeds/`, or `_thoughts/`
2. Use the front matter format:
   ```yaml
   ---
   title: Your Title
   date: YYYY-MM-DD
   tags: [tag1, tag2]
   ---
   ```
3. Write in Markdown
4. Link to related notes when possible

## Style Guide

### Writing
- Use clear, concise language
- Link liberally to related concepts
- It's okay to be incomplete—this is a garden, not a publication
- Use headers to structure content
- Add tags to help with discovery

### Formatting
- Use `##` for main sections
- Use `###` for subsections
- Use bullet points for lists
- Use code blocks with syntax highlighting when appropriate

### File Naming
- Use lowercase with hyphens: `my-note-title.md`
- Be descriptive but concise
- Avoid special characters

## Development

### Local Setup

1. Install Ruby and Bundler
2. Clone the repository
3. Run `bundle install`
4. Run `bundle exec jekyll serve`
5. Visit `http://localhost:4000`

### Testing Changes

Before submitting a pull request:
1. Test locally with Jekyll
2. Check all links work
3. Ensure formatting is consistent
4. Verify the page renders correctly

## Questions?

Open an issue or reach out through GitHub discussions.

## Code of Conduct

Be kind, be respectful, and assume good intentions. This is a space for learning and growth.
