# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a minimalist CV/portfolio website built with Astro 4. The site is designed for both web viewing and PDF generation, using a JSON Resume schema-based approach where all personal data is stored in `cv.json`.

## Development Commands

| Command | Description |
|---------|-------------|
| `npm run dev` or `npm start` | Start development server on http://localhost:4321 |
| `npm run build` | Type check with `astro check` then build for production |
| `npm run preview` | Preview the production build locally |

## Architecture

### Core Structure
- **Data Source**: All CV content is defined in `cv.json` following the JSON Resume schema
- **Layout**: Single-page application with component-based sections
- **Styling**: Global CSS in Layout.astro with component-scoped styles
- **Type Safety**: TypeScript with strict configuration and custom type definitions

### Key Files
- `cv.json` - Contains all personal/professional data (name, experience, skills, etc.)
- `src/pages/index.astro` - Main page that assembles all sections
- `src/layouts/Layout.astro` - Base layout with global styles and meta tags
- `src/components/sections/` - Individual CV sections (Hero, Experience, Skills, etc.)
- `src/icons/` - Technology and social media icons as Astro components

### Path Aliases
- `@cv` - Points to the root `cv.json` file
- `@/*` - Points to `src/*` directory

### Component Architecture
The application follows a sectioned approach:
- **Hero**: Name, title, contact info
- **About**: Professional summary  
- **Experience**: Work history with highlights and skills
- **Education**: Academic background
- **Projects**: Portfolio projects
- **Skills**: Technical and soft skills

### Styling Approach
- Monospace font for body text (Menlo, Monaco, etc.)
- Sans-serif for headings (system fonts)
- Print-optimized CSS with `.print` and `.no-print` classes
- Responsive design with mobile breakpoints
- Global reset and utility classes

## Data Management

When updating CV content, edit `cv.json` directly. The file structure follows JSON Resume schema with sections for:
- `basics` - Personal info, contact, summary
- `work` - Employment history  
- `education` - Academic background
- `skills` - Technical skills
- `projects` - Portfolio projects

## Dependencies

Key dependencies include:
- **Astro 4.3.2** - Static site generator
- **astro-tooltips** - Interactive tooltips
- **hotkeypad** - Keyboard shortcuts
- **TypeScript** - Type safety

## Node.js Version

This project requires Node.js v22 or higher:
- `.nvmrc` file specifies Node v22
- `package.json` engines field enforces `>=22.0.0`
- Use `nvm use` to switch to the correct version

## Development Notes

- The site is optimized for print output (PDF generation)
- Icons are implemented as individual Astro components
- No testing framework is configured
- No linting beyond TypeScript checking is set up
- VS Code is configured to auto-run dev server on folder open