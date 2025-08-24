# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a Chinese cross-border e-commerce resource repository (`mswnlz/cross-border`) that serves as a curated collection of cross-border business tools, knowledge, and resources. The repository includes:

- A simple GitHub Action for notifications (`cross-border-action`)
- Monthly resource files containing cross-border e-commerce tools and guides
- Multilingual README linking to related projects in the mswnlz ecosystem
- Cross-border business strategies and platform information

## Architecture

### Repository Structure
- `index.js` - Main GitHub Action entry point using @actions/core
- `action.yml` - GitHub Action configuration file
- `package.json` - Node.js dependencies (minimal: only @actions/core)
- `202X0X.md` files - Monthly cross-border resource collections (format: YYYYMM.md)
- `README.md` - Multilingual project description with ecosystem links
- `.gitignore` - Standard gitignore for Node.js projects
- `WARP.md` - This configuration file

### GitHub Action Component
The repository contains a minimal GitHub Action called "Cross-border Notify" that:
- Takes a message input parameter (optional, defaults to "Hello from Cross-border Action!")
- Uses Node.js 16 runtime
- Simply prints the provided message to console
- Handles errors gracefully using @actions/core.setFailed()

### Monthly Resource Files
Resource files follow a YYYYMM.md naming pattern and contain:
- Cross-border e-commerce platform guides (Amazon, eBay, AliExpress, etc.)
- Payment and logistics solutions
- Marketing tools and strategies
- Legal and compliance resources
- Market research and analytics tools

## Common Commands

### Development
```bash
# Install dependencies
npm install

# Test the action locally (simulate GitHub Action environment)
node index.js
```

### GitHub Action Usage
This action can be used in workflows with:
```yaml
- uses: mswnlz/cross-border@main
  with:
    message: "Custom cross-border notification message"
```

### Resource Management
```bash
# Create new monthly resource file
touch $(date +%Y%m).md

# View recent resource files
ls -la 2025*.md | head -5

# Search for specific cross-border topics
grep -r "Amazon" *.md
grep -r "跨境电商" *.md

# Count total resources
wc -l 2025*.md
```

### Content Validation
```bash
# Check for broken links
grep -o 'https\?://[^)]*' *.md | while read url; do curl -s --head "$url" | head -n 1; done

# Validate markdown syntax
markdown-link-check *.md
```

## Content Guidelines

### Monthly Resource Files
- Use consistent formatting with descriptive titles
- Include proper attribution with "超过100T资料总站网站-doc.869hr.uk" suffix
- Organize resources by category (Platforms, Tools, Legal, Marketing)
- Provide both Chinese and English descriptions for international resources
- Include extraction codes for cloud storage links where required

### Cross-border Specific Content
- Focus on practical tools and actionable advice
- Include platform-specific guides and best practices
- Cover legal and compliance aspects for different markets
- Provide updated information on policies and regulations
- Include case studies and success stories

### Link Management
- Verify all external links are active before committing
- Use consistent URL shortening format (s.869hr.uk for shortened links)
- Include alternative links where possible
- Document any required credentials or subscriptions

## Ecosystem Integration

This repository is part of a larger project ecosystem including:
- `tools` - General software tools and utilities
- `healthy` - Health and fitness resources
- `curriculum` - Educational materials
- `AIknowledge` - AI-related knowledge and tutorials
- `auto` - Automation tools and scripts
- `book` - Literature and reading materials
- `movies` - Entertainment and media content
- `self-media` - Social media and content creation resources
- `edu-knowledge` - Educational knowledge base
- `chinese-traditional` - Traditional culture content

## Multilingual Support

The README supports 20+ languages through openaitx.github.io view system:
- Primary: Chinese (Simplified and Traditional)
- Supported: English, Japanese, Korean, Hindi, Thai, French, German, Spanish, Italian, Russian, Portuguese, Dutch, Polish, Arabic, Persian, Turkish, Vietnamese, Indonesian

## Cross-border E-commerce Focus Areas

### Platform Integration
- Amazon (US, EU, JP, etc.)
- eBay global marketplaces
- AliExpress and Alibaba
- Shopify international
- Etsy global reach
- Local marketplaces per region

### Business Operations
- International shipping and logistics
- Payment processing solutions
- Tax and customs compliance
- Currency exchange and management
- Customer service across time zones
- Return and refund policies

### Marketing and Growth
- SEO for international markets
- Social media marketing per region
- Influencer partnerships globally
- Email marketing localization
- PPC advertising optimization
- Brand protection and trademark issues
