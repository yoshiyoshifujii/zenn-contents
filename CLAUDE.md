# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Zenn content repository for managing articles and books for the Zenn platform (a Japanese technical writing platform). The repository uses Zenn CLI for content management and preview.

## Common Commands

### Content Management
- `npx zenn preview` - Start local preview server to view articles and books in browser
- `npx zenn new:article` - Create a new article with auto-generated filename
- `npx zenn new:book` - Create a new book
- `npx zenn list:articles` - List all articles
- `npx zenn list:books` - List all books

### Development
- `npm install` - Install dependencies (primarily zenn-cli)

## Content Structure

### Articles
- Located in `articles/` directory
- Filenames are auto-generated unique IDs (e.g., `d15771141169c1.md`)
- Each article starts with frontmatter containing:
  - `title`: Article title
  - `emoji`: Emoji for the article
  - `type`: Either "tech" (technical article) or "idea" (idea/opinion piece)
  - `topics`: Array of topic tags
  - `published`: Boolean indicating publication status

### Images
- Located in `images/` directory
- Organized by article ID subdirectories
- Referenced from articles using relative paths

### Books
- Located in `books/` directory (currently empty but available for book content)

## Content Guidelines

- Articles cover both technical topics and ideas/opinions
- Content is written in Japanese
- Technical articles use the "tech" type, opinion pieces use "idea" type
- Images should be organized in subdirectories matching article IDs
- Use proper frontmatter formatting for all articles

## Architecture Notes

This is a static content repository with no build process beyond the Zenn CLI preview functionality. The primary workflow involves creating content locally and using the preview server to review before publishing to Zenn.