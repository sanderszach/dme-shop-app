# DME Shop — Shopify Theme

Custom Shopify theme based on [Dawn](https://github.com/Shopify/dawn) v15.4.1.

## Prerequisites

- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) v3+
- Access to the DME Shopify store (Partner Dashboard or store owner)

Install the Shopify CLI:

```bash
npm install -g @shopify/cli @shopify/theme
```

## Running locally

1. Authenticate with Shopify:

   ```bash
   shopify auth login
   ```

2. Start the development server against your store:

   ```bash
   shopify theme dev --store your-store.myshopify.com
   ```

   This syncs your local files to a development theme on the store and opens a preview URL in the browser. Changes to local files are reflected immediately.

   To target a specific theme ID (e.g. to resume work on an existing dev theme):

   ```bash
   shopify theme dev --store your-store.myshopify.com --theme <theme-id>
   ```

## Publishing (pushing to live)

**Push to an existing theme** (overwrites it):

```bash
shopify theme push --store your-store.myshopify.com --theme <theme-id>
```

**Push as a new theme** (creates a draft; you can then activate it in the Shopify admin):

```bash
shopify theme push --store your-store.myshopify.com --unpublished
```

**Activate the theme** after pushing: go to *Online Store → Themes* in the Shopify admin and click *Publish* next to the theme.

## Useful commands

| Command | Description |
|---|---|
| `shopify theme list --store <store>` | List all themes and their IDs |
| `shopify theme pull --store <store>` | Pull the latest theme files from the store |
| `shopify theme check` | Lint the theme with Theme Check |
| `shopify theme package` | Package the theme into a `.zip` for manual upload |
