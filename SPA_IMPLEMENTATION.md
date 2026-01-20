# OMKAR AGRO INDUSTRIES - SPA Implementation Guide

## Overview
This is a modern Single Page Application (SPA) for OMKAR AGRO INDUSTRIES built with React + TypeScript + Tailwind CSS. The website uses **section-based content rendering** instead of page routing or scroll navigation.

## Core Architecture

### Section-Based Navigation (NOT URL Routing)
The application uses React state management to switch between sections without:
- ❌ URL changes (no `/about`, `/products`, etc.)
- ❌ Page scrolling (no `scrollIntoView` or scroll navigation)
- ✅ Dynamic content replacement (state-driven tab switching)

### How It Works

1. **App.tsx** maintains a single `activeSection` state
2. **Navbar** buttons trigger `onSectionChange()` to update the active section
3. **App.tsx** conditionally renders the appropriate section component
4. **Footer** remains visible on all sections

```
App.tsx
├── activeSection: 'home' | 'about' | 'products' | 'applications' | 'contact'
├── Navbar (triggers onSectionChange)
├── Main Content Area (switches based on activeSection)
│   ├── Home Section (Hero + Stats + WhyChooseUs + FeaturedProducts + CTA)
│   ├── About Section
│   ├── Applications Section
│   ├── Products Section
│   └── Contact Section
└── Footer (always visible)
```

## Sections

### 1. Home (Default)
- Hero section with product overview
- Stats section with company metrics
- Why Choose Us section
- Featured Products showcase
- Call-to-action section
- **Visibility**: Shown by default when app loads

### 2. About
- Company hero with "Growing Together with Indian Farmers"
- Vision & Mission cards
- Timeline of company journey
- Core values section
- Closing CTA
- **No scrolling required** - all content visible in section area

### 3. Applications
Displays nutrient solutions matched exactly to design specifications:

#### Structure:
- **Hero Area**
  - Badge: "Applications"
  - Heading: "Nutrient Solutions for Every Crop" (green highlight)
  - Description text

- **Crop-Specific Solutions** (4 Cards)
  - Cereal Crops (Rice, Wheat, Maize, Barley)
  - Vegetable Crops (Tomato, Potato, Onion, Chili)
  - Fruit Orchards (Mango, Citrus, Grapes, Pomegranate)
  - Cash Crops (Cotton, Sugarcane, Soybean, Groundnut)
  - Card styling: Rounded corners, soft shadow, light gray background, green icons

- **Benefits for Soil Health** (3 Cards)
  - Improved Soil Health
  - Enhanced Nutrient Uptake
  - Sustainable Agriculture

- **How to Apply** (Vertical Steps)
  - 01 Soil Analysis
  - 02 Product Selection
  - 03 Proper Mixing
  - 04 Timely Application
  - Number badges: Green with white text

- **Get Expert Guidance CTA**
  - Primary button: "Talk to an Expert"
  - Secondary button: "View Products"

### 4. Products
- Product showcase with 6 product cards
- Each product displays:
  - Icon
  - Category badge
  - Description
  - Benefits list
  - "Learn More" button
- "Why Choose Our Products" feature section
- CTA: "Contact Our Experts"

### 5. Contact
- Contact information cards (Address, Phone, Email, Hours)
- Contact form with validation
- "Why Partner with Us" benefits section
- FAQ section
- "Schedule a Call" CTA

## Navbar Design

### Desktop Navigation
- Logo (left)
- Nav items: Home | About | Products | Applications | Contact
- Active indicator:
  - **Green text** (#16A34A / #22C55E)
  - **Small green dot** above active item
  - **Green underline** on hover/active

### Mobile Navigation
- Hamburger menu
- Dropdown menu with green background highlight for active item
- Login button in mobile menu

## Color Palette (Strict)

| Element | Color |
|---------|-------|
| Primary Green | `#16A34A` or `#22C55E` |
| Light Green BG | `#ECFDF5` |
| Text Headings | Near black |
| Text Body | `#4B5563` (gray-600) |
| Shadows | Soft, blurred, modern |
| Border Radius | Large (xl) |

### Tailwind Classes Used:
- `text-green-600`, `text-green-500`
- `bg-green-50`, `bg-green-100`, `bg-green-200`
- `border-green-200`, `border-green-500`
- `rounded-2xl`, `rounded-full` (large radius)
- `shadow-md`, `shadow-lg` (soft shadows)

## Technical Implementation Details

### State Management
```typescript
// App.tsx
const [activeSection, setActiveSection] = useState('home')

const renderSection = () => {
  switch (activeSection) {
    case 'home': return <Home />
    case 'about': return <About />
    case 'applications': return <Applications />
    case 'products': return <Products />
    case 'contact': return <Contact />
  }
}
```

### Navbar Props
```typescript
interface NavbarProps {
  activeSection: string          // Current active section
  onSectionChange: (section: string) => void  // Callback to change section
}
```

### No Anchor Links
- ❌ NO `<a href="#about">` links
- ❌ NO `scrollIntoView()` calls
- ✅ Button click → `onSectionChange('about')`

### Animation Library
- Uses **Framer Motion** for smooth animations
- Variants for different animation patterns:
  - `containerVariants` - staggered children
  - `itemVariants` - fade-in + y-offset
  - `scaleVariants` - scale + opacity
  - `timelineVariants` - timeline animations

### Section-Specific Styling
Each section has:
- Hero area with gradient background
- Badge and heading
- Smooth animations on scroll-into-view
- Responsive grid layouts
- Consistent spacing and typography

## File Structure

```
src/
├── App.tsx                           # Main app with section switching logic
├── index.css                         # Global styles
├── main.tsx                          # Entry point
├── components/
│   ├── Navbar.tsx                   # Navigation bar (UPDATED)
│   ├── Hero.tsx                     # Home hero section
│   ├── Stats.tsx                    # Stats section
│   ├── WhyChooseUs.tsx              # Why choose us section
│   ├── FeaturedProducts.tsx         # Featured products
│   ├── CTA.tsx                      # Call-to-action
│   ├── About.tsx                    # About section (UPDATED)
│   ├── Applications.tsx             # Applications section (NEW)
│   ├── Products.tsx                 # Products section (NEW)
│   ├── Contact.tsx                  # Contact section (NEW)
│   └── Footer.tsx                   # Footer (always visible)
```

## Key Features

1. **No Page Reloads**: Entire site loads once, sections switch via React state
2. **No URL Changes**: Active section managed in state only
3. **No Scroll Navigation**: All sections fit within viewport or scroll naturally
4. **Smooth Animations**: Framer Motion provides transition effects
5. **Mobile Responsive**: Fully responsive design with mobile menu
6. **Accessible**: Proper semantic HTML and ARIA labels
7. **Fast**: No network requests between sections
8. **Professional**: Premium animations and design

## Usage

### Start Development
```bash
npm run dev
```

### Build for Production
```bash
npm run build
```

### Click Navigation Example
```
User clicks "Applications" in navbar
  ↓
Navbar calls onSectionChange('applications')
  ↓
App.tsx sets activeSection = 'applications'
  ↓
renderSection() switches to <Applications />
  ↓
Applications component renders with smooth animations
  ↓
Footer remains visible below
```

## Important Notes

✅ **DO**:
- Use `onSectionChange()` for navigation
- Render sections conditionally based on `activeSection`
- Keep footer outside section switching
- Use state management for active section
- Test all navbar buttons

❌ **DON'T**:
- Add React Router or URL routing
- Use `scrollIntoView()` or scroll behavior
- Create anchor links
- Change window location
- Use hash-based navigation

## Future Enhancements

- Add "Contact Form" functionality
- Integrate backend for product listings
- Add animation transitions between sections
- Implement search functionality
- Add blog/news section
- Multi-language support

## Support

For questions about the SPA implementation or technical details, refer to this documentation or examine the component files directly.
