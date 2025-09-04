# Integrations

This directory contains integrations with external services and APIs used throughout the application. These integrations provide seamless connections to CMS, e-commerce, and marketing platforms.

## Available Integrations

- `sanity/` - Sanity CMS integration for content management

## Sanity Integration

The Sanity integration provides headless CMS functionality with visual editing capabilities.

### Features

- Content management with Sanity Studio
- Rich text rendering with Portable Text
- Visual editing and live preview
- Draft mode support
- Image optimization

### Usage

```tsx
import { fetchSanityPage, SanityContextProvider, RichText } from '~/integrations/sanity'

// Fetch content from Sanity
async function getPageData(slug: string) {
  const { data } = await fetchSanityPage(slug)
  return data
}

// Render content with context
function ContentPage({ data }) {
  return (
    <SanityContextProvider document={data}>
      <RichText content={data.content} />
    </SanityContextProvider>
  )
}
```

## Environment Variables

```env

# Sanity CMS
NEXT_PUBLIC_SANITY_PROJECT_ID="your-project-id"
NEXT_PUBLIC_SANITY_DATASET="production"
NEXT_PUBLIC_SANITY_STUDIO_URL="http://localhost:3000/studio"
SANITY_API_WRITE_TOKEN="your-viewer-token"

```
