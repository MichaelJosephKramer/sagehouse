# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website project for Sage House, LLC built using Grunt.js as the build system. It's a simple business card style website with contact information and links.

## Tech Stack

- **Frontend**: HTML5, Sass/SCSS, CoffeeScript
- **CSS Framework**: Bootstrap (via sass-bootstrap)
- **Build Tool**: Grunt.js with extensive plugin ecosystem
- **Testing**: Mocha
- **Deployment**: Heroku with Express.js server
- **Dependencies**: Managed via npm and Bower

## Development Commands

### Core Development
- `grunt serve` - Start development server with live reload (port 9000)
- `grunt watch` - Watch files for changes and rebuild
- `grunt build` - Build production files to `dist/` directory
- `grunt test` - Run Mocha tests
- `grunt default` - Run lint, test, and build (full pipeline)

### Individual Tasks
- `grunt jshint` - Lint JavaScript files
- `grunt coffee` - Compile CoffeeScript to JavaScript
- `grunt compass` - Compile Sass to CSS
- `grunt clean` - Clean temporary and dist directories

### Deployment
- `grunt buildcontrol` - Deploy to Heroku (pushes dist folder to heroku remote)

## Project Structure

```
app/                    # Source files
  ├── index.html       # Main HTML file
  ├── scripts/         # CoffeeScript source files
  │   └── main.coffee  # Main application script (currently minimal)
  ├── styles/          # Sass/SCSS source files
  │   └── main.scss    # Main stylesheet with custom styles
  └── images/          # Static assets
dist/                   # Built/compiled files (production)
heroku/                # Heroku deployment configuration
  ├── Procfile        # Heroku process definition
  └── web.js          # Express server for serving static files
test/                  # Test files
  └── spec/test.js     # Basic Mocha test structure
```

## Build Process

The build system uses Grunt with the following key features:
- CoffeeScript compilation to JavaScript
- Sass compilation to CSS with autoprefixer
- Asset minification (JS, CSS, images)
- File concatenation and versioning (rev)
- HTML minification
- Bower dependency injection
- Live reload during development

## Code Standards

- **JavaScript**: JSHint with strict linting rules (see .jshintrc)
- **Indentation**: 4 spaces
- **Quotes**: Single quotes preferred
- **Strict mode**: Required

## Deployment

The site is configured for Heroku deployment with:
- Express.js server serving static files from dist/
- Gzipped static file serving via gzippo
- Build artifacts copied to dist/ with Heroku-specific files