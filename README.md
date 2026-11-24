# VitalCocoa Shopify Theme

Connected to Shopify store: **sjwjsx-uv.myshopify.com**
Development Theme ID: **190635049205**

## Setup

This repository is set up with Shopify CLI for theme development.

### Prerequisites
- Shopify CLI installed (`npm install -g @shopify/cli`)
- Authenticated with Shopify account

### Local Development

**Start development server:**
```bash
shopify theme dev
```

This will:
- Watch for file changes
- Sync changes to your development theme
- Open a preview of your theme

**List all themes:**
```bash
shopify theme list
```

**Push changes to store:**
```bash
shopify theme push
```

### Theme Structure

- `assets/` - CSS, JavaScript, images
- `config/` - Theme configuration files
- `layout/` - Theme layouts
- `sections/` - Customizable sections
- `snippets/` - Reusable snippets
- `templates/` - Page templates
- `locales/` - Translation files

### Reference Files

Original reference design files are in the `refrence/` folder.

## Deployment

Your theme is currently in **development mode**. To make it live:
1. Navigate to Shopify Admin → Themes
2. Find "Development (5e3903-Mac)" theme
3. Click "Actions" → "Publish theme"

Or use CLI:
```bash
shopify theme publish
```
