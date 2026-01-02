---
title: Image Testing
sync_to_confluence: true
---

# Image Testing

This page tests various image formats and embedding methods for the markdown-confluence-sync-action.

## Local SVG Images

### Architecture Diagram

![Architecture Overview](images/diagram-architecture.svg)

### Workflow Steps

![Workflow Steps](images/workflow-steps.svg)

### Logo / Branding

![Logo](images/logo-placeholder.svg)

### Status Badge

![Status Badge](images/status-badge.svg)

## Image Sizing

Testing different markdown image approaches:

### Standard Markdown

![Small Logo](images/logo-placeholder.svg)

### HTML img Tag (if supported)

<img src="images/logo-placeholder.svg" alt="HTML Logo" width="100" />

## PNG Images

### Blue PNG Test

![Test PNG](images/test-image.png)

### Red Square PNG

![Red Square](images/red-square.png)

## JPEG Images

### Green JPEG Test

![Test JPEG](images/test-image.jpg)

### Gradient Banner JPEG

![Gradient Banner](images/gradient-banner.jpg)

## Expected Results

| Image Type | Format | Expected Result |
|------------|--------|-----------------|
| Local SVG | `.svg` | ✅ Should render |
| Local PNG | `.png` | ✅ Should render |
| Local JPG | `.jpg` | ✅ Should render |
| External URL | `https://...` | ❌ Preview unavailable |

## Notes

- All images should be committed to the repository
- External URLs (e.g., placeholder.com) do not work in Confluence
- SVG files render well and are scalable
- Relative paths from the markdown file location work correctly
