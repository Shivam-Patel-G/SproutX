# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

SproutX is a simple, elegant frontend website serving as a landing page with navigation to prototype and video content. It's a static site built with vanilla HTML, CSS, and optimized for Vercel deployment.

**Tagline**: "Growing Ideas into Reality"

## Common Development Commands

### Local Development
```bash
# No build step required - open directly in browser
start index.html                    # Windows - opens in default browser
# OR
python -m http.server 8000          # Serve locally with Python
# OR  
npx serve .                         # Serve locally with Node.js (if available)
```

### Deployment
```bash
# Deploy to Vercel (if Vercel CLI is installed)
vercel --prod

# Check deployment status
vercel ls
```

### Version Control
```bash
# Standard git workflow
git add .
git commit -m "feat: description"
git push origin main
```

## Architecture & Code Structure

### File Organization
```
SproutX/
├── index.html          # Single-page application entry point
├── css/
│   └── style.css      # All styles in one file using modern CSS
├── vercel.json        # Vercel deployment configuration
└── README.md         # Project documentation
```

### Design System
- **Color Palette**: Gradient-based design using blue-purple (`#667eea` to `#764ba2`) and pink-red (`#f093fb` to `#f5576c`) gradients
- **Typography**: Arial font family with responsive sizing (4rem desktop logo, scales down to 2.5rem mobile)
- **Layout**: Centered flexbox layout with responsive design breakpoints at 768px and 480px
- **Interactive Elements**: Two main navigation buttons (Prototype and Video) with hover animations and gradient backgrounds

### Key Components
1. **Header**: Contains logo and tagline
2. **Main Content**: Two prominent call-to-action buttons
3. **Footer**: Simple copyright notice
4. **Responsive Design**: Mobile-first approach with specific breakpoints

### CSS Architecture
- Global reset using `* { margin: 0; padding: 0; box-sizing: border-box; }`
- Modern CSS features: Flexbox, CSS Grid, gradients, transforms, transitions
- Hover effects with `translateY` transforms and dynamic box shadows
- Shimmer effect on buttons using `::before` pseudo-elements

## Development Notes

### Styling Approach
- Single CSS file contains all styles
- Uses CSS custom properties implicitly through gradient reuse
- Responsive design handled through media queries
- Animation and transition effects for enhanced UX

### Vercel Configuration
- Static site deployment using `@vercel/static`
- All routes redirect to `index.html` for SPA behavior
- No build process required

### Content Structure
The site currently has placeholder navigation buttons that link to `#`. When implementing actual functionality:
- Update href attributes in navigation buttons to point to actual prototype/video URLs
- Consider adding loading states or transitions between sections
- Maintain the existing visual design and hover effects

### Browser Compatibility
- Uses modern CSS features (flexbox, gradients, transforms)
- Should work in all modern browsers (Chrome, Firefox, Safari, Edge)
- IE11 support may require additional polyfills if needed