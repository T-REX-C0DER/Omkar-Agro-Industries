# OMKAR AGRO INDUSTRIES - Homepage Documentation

## Project Overview

This is a production-ready, modern homepage for OMKAR AGRO INDUSTRIES built with React, TypeScript, Vite, and Tailwind CSS. The site showcases premium agricultural solutions with a professional, minimalist design.

## 🏗️ Architecture

### Component Structure

```
App.tsx (Main Component)
├── Navbar.tsx
│   ├── Logo section with leaf icon
│   ├── Navigation links with active indicator
│   ├── Login button
│   └── Mobile hamburger menu
│
├── Hero.tsx
│   ├── Gradient background
│   ├── Left content area (heading, badge, description)
│   ├── CTA buttons (Explore & Contact)
│   ├── Right image placeholder
│   └── Scroll indicator
│
├── Stats.tsx
│   └── Four stat cards (Experience, Farmers, Hectares, Products)
│
├── WhyChooseUs.tsx
│   ├── Section title with green highlight
│   ├── Description paragraph
│   └── Four feature cards with hover animations
│
├── FeaturedProducts.tsx
│   ├── Section header with "View All" button
│   └── Three product cards
│       ├── Gradient background
│       ├── Category badge
│       ├── Product name & description
│       └── "Learn More" link
│
├── CTA.tsx
│   ├── Green gradient background
│   ├── Main heading
│   ├── Supporting paragraph
│   └── Two CTA buttons
│
└── Footer.tsx
    ├── Company info section
    ├── Four footer columns
    │   ├── Quick Links
    │   ├── Products
    │   └── Contact Info
    └── Copyright & Policy links
```

## 🎨 Design System

### Color Palette

| Element | Color | Code |
|---------|-------|------|
| Primary Green | Green 500 | #22c55e |
| Dark Green | Green 600 | #16a34a |
| Light Green | Green 100 | #dcfce7 |
| White | White | #ffffff |
| Dark Gray | Gray 900 | #111827 |
| Medium Gray | Gray 600 | #4b5563 |

### Typography Scale

| Element | Font | Size | Weight |
|---------|------|------|--------|
| H1 (Hero) | Sans | 48-60px | Bold (700) |
| H2 (Section) | Sans | 36-48px | Bold (700) |
| H3 (Card) | Sans | 24px | Bold (700) |
| Body Text | Sans | 16px | Regular (400) |
| Small Text | Sans | 14px | Regular (400) |

### Spacing System

- **Base Unit**: 8px
- **Common Gaps**: 4, 8, 12, 16, 20, 24, 32, 40px
- **Section Padding**: 20-24px (mobile), 40-80px (desktop)

### Shadow System

```css
/* Soft Shadow */
box-shadow: 0 4px 6px rgba(0, 0, 0, 0.07), 0 1px 3px rgba(0, 0, 0, 0.06);

/* Soft Large Shadow */
box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1), 0 4px 6px rgba(0, 0, 0, 0.05);
```

## 📱 Responsive Behavior

### Breakpoints (Tailwind Default)

- **Mobile**: < 640px (sm)
- **Tablet**: 640px - 1024px (md, lg)
- **Desktop**: > 1024px (xl)

### Responsive Adjustments

**Navbar**
- Desktop: Full horizontal layout
- Tablet/Mobile: Hamburger menu appears

**Hero**
- Desktop: Two-column layout (text + image)
- Mobile: Single column, stacked layout

**Products Grid**
- Desktop: 3 columns
- Tablet: 2 columns
- Mobile: 1 column

**Stats**
- Desktop: 4 columns
- Mobile: 2 columns

## 🎭 Interactive Elements

### Hover Effects

```css
/* Button Hover */
- Scale: scale-105
- Duration: 300ms
- Shadow: Enhanced shadow

/* Card Hover */
- Translate: -translate-y-2 (lift up)
- Shadow: soft-lg
- Duration: 300ms

/* Link Hover */
- Color: Transition to darker shade
- Arrow: Scale/translate animation
```

### Animations

- **Bounce**: Scroll indicator (infinite)
- **Fade**: Smooth transitions on all interactive elements
- **Scale**: Buttons and cards

## 🔧 Technologies

| Technology | Version | Purpose |
|-----------|---------|---------|
| React | 18.2.0 | UI Library |
| TypeScript | 5.2.2 | Type Safety |
| Vite | 5.0.8 | Build Tool |
| Tailwind CSS | 3.3.6 | Styling |
| PostCSS | 8.4.32 | CSS Processing |

## 📦 Project Structure

```
OMKAR-AGRO-INDUSTRIES-/
├── src/
│   ├── components/
│   │   ├── Navbar.tsx
│   │   ├── Hero.tsx
│   │   ├── Stats.tsx
│   │   ├── WhyChooseUs.tsx
│   │   ├── FeaturedProducts.tsx
│   │   ├── CTA.tsx
│   │   └── Footer.tsx
│   ├── App.tsx
│   ├── main.tsx
│   ├── index.css
│   └── react-app-env.d.ts
├── dist/                    # Production build output
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
├── tailwind.config.js
├── postcss.config.js
├── .gitignore
└── README.md
```

## 🚀 Development Workflow

### Scripts

```bash
# Start development server (http://localhost:5173)
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview

# Lint code (TypeScript strict mode)
# (configured via tsconfig.json)
```

### Development Tips

1. **Hot Module Replacement**: Vite automatically refreshes on file changes
2. **TypeScript Strict Mode**: All types must be explicitly defined
3. **Tailwind IntelliSense**: VSCode will suggest Tailwind classes
4. **Component Reusability**: Each section is a self-contained component

## 🎯 Page Sections Breakdown

### 1. Navbar (Sticky)
- **Height**: 80px
- **Features**: Logo, navigation links with active indicator, responsive menu
- **Sticky**: Fixed at top with z-50

### 2. Hero
- **Full Height**: Min 100vh on desktop
- **Layout**: 2 columns (text + image)
- **Features**: Badge, gradient text, CTA buttons, scroll indicator
- **Background**: Gradient with decorative blurred shapes

### 3. Stats
- **Grid**: 4 columns (desktop), 2 columns (mobile)
- **Style**: Large green numbers with small labels
- **Spacing**: Even distribution with gap-8

### 4. Why Choose Us
- **Grid**: 4 columns (desktop), 2 columns (tablet), 1 column (mobile)
- **Cards**: Rounded with soft shadow, lift on hover
- **Features**: Icon in circle, title, hover animations

### 5. Featured Products
- **Grid**: 3 columns (desktop), responsive for mobile
- **Card Structure**: Image placeholder, badge, name, description, link
- **Hover**: Image scale, card lift
- **CTA**: "View All Products" link in header

### 6. CTA Section
- **Style**: Full-width green gradient container
- **Content**: Centered heading, paragraph, two buttons
- **Spacing**: Generous padding for prominence

### 7. Footer
- **Columns**: 4 on desktop (Company, Links, Products, Contact)
- **Bottom Bar**: Copyright, policy links
- **Dark Theme**: Dark gray background with light text

## ♿ Accessibility Features

- **Semantic HTML**: `<section>`, `<nav>`, `<footer>`, `<button>`
- **Color Contrast**: WCAG AA compliant
- **Button States**: Clear hover/focus states
- **Link Text**: Descriptive link labels
- **Navigation**: Keyboard accessible

## 🚀 Performance Optimizations

- **Vite Code Splitting**: Automatic module splitting
- **CSS Tree-Shaking**: Only used Tailwind classes included
- **Component Lazy Loading**: Ready for React.lazy() if needed
- **Image Optimization**: Gradient placeholders (no external images)
- **Bundle Size**: ~155KB JS, ~21KB CSS (gzipped ~49KB + 4KB)

## 🔐 Security & Best Practices

- **TypeScript Strict**: No implicit any types
- **No Inline Styles**: All styling via Tailwind
- **No External Dependencies**: Minimal, proven libraries only
- **XSS Protection**: React automatic escaping
- **CSRF Ready**: For backend integration

## 🌍 Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | Latest | ✅ Fully Supported |
| Firefox | Latest | ✅ Fully Supported |
| Safari | 14+ | ✅ Fully Supported |
| Edge | Latest | ✅ Fully Supported |
| IE 11 | - | ❌ Not Supported |

## 📖 Common Customizations

### Change Primary Color

Edit `tailwind.config.js`:
```js
extend: {
  colors: {
    green: {
      500: '#YOUR_COLOR' // Change primary green
    }
  }
}
```

### Add New Section

1. Create component in `src/components/`
2. Import in `App.tsx`
3. Add to JSX in correct order
4. Style with Tailwind classes

### Modify Text Content

All text is directly in component JSX. Edit the strings to customize:
- Component headings
- Descriptions
- Button labels
- Footer text

## 🤝 Contributing

When making changes:
1. Maintain component structure
2. Use Tailwind utilities only (no inline styles)
3. Keep TypeScript types strict
4. Test responsive behavior at all breakpoints
5. Run `npm run build` to verify production build

## 📜 License

© 2026 OMKAR AGRO INDUSTRIES. All rights reserved.

---

**Last Updated**: January 15, 2026
**Version**: 1.0.0
