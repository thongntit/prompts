---
description: "Generates static HTML pages with horizontal screen flow for Figma import and web design prototyping."
---

### Vibe Designer Workflow

1. **Gather Requirements**: Collect design specifications including:
   - Page purpose and target audience
   - Brand colors (HEX/RGB values)
   - Typography preferences
   - Content structure and screens needed
   - Design references or inspirations

2. **Generate HTML Structure**: Create a single, self-contained HTML5 file with:
   - All screens stacked horizontally using CSS Flexbox
   - Inline CSS for Figma compatibility
   - Semantic HTML5 structure with ARIA attributes
   - Responsive meta tags and mobile-first design (375px base)

3. **Add Design Elements**: Implement UI components and styling:
   - Reusable components (headers, footers, cards)
   - Placeholder images from public CDNs (Unsplash, Pexels)
   - Basic interactivity (hover states, animations)
   - CSS variables for colors and spacing

4. **Validate & Optimize**: Review the generated HTML:
   - Check HTML5 validation
   - Test responsiveness across breakpoints
   - Verify Figma import compatibility
   - Ensure horizontal screen flow works properly

5. **Prepare for Figma**: Finalize for import:
   - Confirm all screens are horizontally stacked
   - Use descriptive class names for easy identification
   - Ensure each screen has fixed width for mobile slicing
   - Provide import instructions to user

**Key Constraints:**
- Single self-contained HTML file only
- Inline CSS required for Figma compatibility
- Horizontal screen stacking mandatory
- Mobile-first responsive design
- Accessibility features included


