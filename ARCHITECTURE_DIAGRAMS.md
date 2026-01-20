# OMKAR AGRO INDUSTRIES - Architecture & Flow Diagrams

## 🏗️ Component Architecture

```
┌─────────────────────────────────────────────────────────┐
│                      App.tsx                             │
│  (Main Component - State Management)                     │
│                                                          │
│  State: activeSection = 'home'                          │
│  Function: renderSection()                              │
└────────────────────┬────────────────────────────────────┘
                     │
        ┌────────────┼────────────┐
        │            │            │
        ↓            ↓            ↓
    ┌──────────┐ ┌──────────┐ ┌─────────────┐
    │ Navbar   │ │  Main    │ │   Footer    │
    │(Input)   │ │ Content  │ │ (Passive)   │
    │          │ │(Display) │ │             │
    └──────────┘ └──────────┘ └─────────────┘
        │            │
        └──→ onSection  ←─────┐
             Change()         │
                              │
    ┌─────────────────────────┘
    │
    ↓
Main Content Renders Based on activeSection:

activeSection === 'home'
        ↓
    ┌──────────────────────────────────┐
    │         HOME SECTION             │
    ├──────────────────────────────────┤
    │ 1. Hero Section                  │
    │ 2. Stats Section                 │
    │ 3. Why Choose Us                 │
    │ 4. Featured Products             │
    │ 5. CTA Section                   │
    └──────────────────────────────────┘

activeSection === 'about'
        ↓
    ┌──────────────────────────────────┐
    │        ABOUT SECTION             │
    ├──────────────────────────────────┤
    │ 1. Hero with Heading             │
    │ 2. Vision & Mission              │
    │ 3. Timeline/Journey              │
    │ 4. Core Values                   │
    │ 5. Closing CTA                   │
    └──────────────────────────────────┘

activeSection === 'applications'
        ↓
    ┌──────────────────────────────────┐
    │    APPLICATIONS SECTION          │
    ├──────────────────────────────────┤
    │ 1. Hero Section                  │
    │ 2. Crop Solutions (4 Cards)      │
    │ 3. Soil Health Benefits (3)      │
    │ 4. How to Apply (4 Steps)        │
    │ 5. Expert Guidance CTA           │
    └──────────────────────────────────┘

activeSection === 'products'
        ↓
    ┌──────────────────────────────────┐
    │     PRODUCTS SECTION             │
    ├──────────────────────────────────┤
    │ 1. Hero Section                  │
    │ 2. Product Cards (6)             │
    │ 3. Why Choose Us (6 Features)    │
    │ 4. CTA Section                   │
    └──────────────────────────────────┘

activeSection === 'contact'
        ↓
    ┌──────────────────────────────────┐
    │      CONTACT SECTION             │
    ├──────────────────────────────────┤
    │ 1. Hero Section                  │
    │ 2. Contact Info Cards (4)        │
    │ 3. Contact Form                  │
    │ 4. Why Partner With Us           │
    │ 5. FAQ Section (4)               │
    └──────────────────────────────────┘
```

## 🔄 State Flow Diagram

```
User Interaction
      │
      ↓
┌──────────────────────┐
│ Click Navbar Button  │
│ (e.g., "About")      │
└──────────┬───────────┘
           │
           ↓
┌──────────────────────────────────┐
│ Navbar.handleNavClick('about')   │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ Call onSectionChange('about')    │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ App.setActiveSection('about')    │
│ (State updates)                  │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ App.renderSection() called       │
│ switch(activeSection) {...}      │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ case 'about':                    │
│   return <About />               │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ React re-renders main area       │
│ Shows About component            │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ Navbar indicator updates:        │
│ - Active: 'about'                │
│ - Green text + dot shows         │
└──────────┬───────────────────────┘
           │
           ↓
┌──────────────────────────────────┐
│ Animations trigger:              │
│ - Fade-in                        │
│ - Stagger animations             │
│ - Smooth transitions             │
└──────────────────────────────────┘
```

## 🎨 Color & Styling Flow

```
┌─────────────────────────────────────┐
│     Design System                   │
├─────────────────────────────────────┤
│                                     │
│ Primary Colors:                     │
│  ├─ Green-600: #16A34A (dark)      │
│  ├─ Green-500: #22C55E (light)     │
│  └─ Green-50: #ECFDF5 (bg)         │
│                                     │
│ Text Colors:                        │
│  ├─ Gray-900: Headings             │
│  └─ Gray-600: Body text            │
│                                     │
│ Components:                         │
│  ├─ rounded-2xl: Cards             │
│  ├─ rounded-full: Buttons          │
│  └─ shadow-md/lg: Soft shadows     │
│                                     │
│ Spacing (Tailwind):                │
│  └─ p-4 to p-12: Padding           │
│  └─ gap-4 to gap-12: Gaps          │
└─────────────────────────────────────┘
         │
         ├─→ Applied to Cards
         ├─→ Applied to Buttons
         ├─→ Applied to Sections
         └─→ Applied to All Components
```

## 📱 Responsive Breakpoints

```
Mobile (< 768px)              Tablet (768px - 1024px)        Desktop (> 1024px)
├─ Single column             ├─ 2 columns                   ├─ 3+ columns
├─ Hamburger menu            ├─ Adjusted spacing            ├─ Full horizontal nav
├─ Stack vertically          ├─ Optimized grid              ├─ Premium spacing
├─ Touch-friendly size       ├─ Side-by-side layout         ├─ Large hover effects
└─ Simplified form           └─ Balanced design              └─ Full feature set

Example Card Layout:
Mobile:        Tablet:        Desktop:
┌─────────┐   ┌──────┬──────┐ ┌────┬────┬────┐
│ Card 1  │   │Card 1│Card 2│ │ C1 │ C2 │ C3 │
├─────────┤   ├──────┼──────┤ ├────┼────┼────┤
│ Card 2  │   │Card 3│Card 4│ │ C4 │ C5 │ C6 │
├─────────┤   └──────┴──────┘ └────┴────┴────┘
│ Card 3  │
├─────────┤
│ Card 4  │
└─────────┘
```

## 🎬 Animation Flow

```
Component Load
      │
      ↓
┌────────────────────────┐
│ Initial: hidden        │
│ opacity: 0, y: 20      │
└────────┬───────────────┘
         │
         ↓ (Initial animation)
┌────────────────────────┐
│ Animate: visible       │
│ opacity: 1, y: 0       │
│ duration: 600ms        │
└────────┬───────────────┘
         │
         ↓ (On hover - cards)
┌────────────────────────┐
│ WhileHover: scale up   │
│ y: -10 (lift)          │
│ shadow: increased      │
└────────┬───────────────┘
         │
         ↓ (Staggered children)
┌────────────────────────┐
│ Container variant:     │
│ staggerChildren: 0.2   │
│ Each child delayed 0.2s│
└────────────────────────┘
```

## 📊 Section Hierarchy

```
HOME (Default Section)
├── Hero
│   ├── Badge: "Premium Agricultural Solutions"
│   ├── Main Heading with gradient
│   ├── Description
│   ├── CTA Buttons (2)
│   └── Scroll Indicator
├── Stats
│   ├── Metric cards (3-4)
│   └── Company achievements
├── WhyChooseUs
│   ├── Section title
│   ├── Feature cards
│   └── Hover effects
├── FeaturedProducts
│   ├── Product showcase
│   ├── Product details
│   └── Links
└── CTA
    ├── Large call-to-action
    ├── Primary button
    └── Secondary button

ABOUT Section
├── Hero Intro
│   ├── Badge: "About Us"
│   ├── Company heading
│   └── Brief description
├── Vision & Mission
│   ├── Vision card with icon
│   └── Mission card with icon
├── Journey Timeline
│   ├── Timeline line (vertical)
│   ├── 4 Milestone points
│   └── Animation dots
├── Core Values
│   ├── 4 Value cards
│   ├── Icon + title + description
│   └── Hover effects
└── Closing CTA
    └── Button to explore

APPLICATIONS Section
├── Hero Area
│   ├── Badge: "Applications"
│   ├── Heading: "Nutrient Solutions..."
│   └── Green highlight on "Every Crop"
├── Crop-Specific Solutions
│   ├── 4 crop category cards:
│   │   ├── Cereal Crops
│   │   ├── Vegetable Crops
│   │   ├── Fruit Orchards
│   │   └── Cash Crops
│   └── Each with crop list
├── Benefits for Soil Health
│   ├── 3 benefit cards
│   ├── Improved Soil Health
│   ├── Enhanced Nutrient Uptake
│   └── Sustainable Agriculture
├── How to Apply
│   ├── 01 Soil Analysis
│   ├── 02 Product Selection
│   ├── 03 Proper Mixing
│   └── 04 Timely Application
└── Expert Guidance CTA
    ├── Title
    ├── Description
    ├── Primary button: "Talk to Expert"
    └── Secondary button: "View Products"

PRODUCTS Section
├── Hero
├── Product Cards (6)
│   ├── Product name
│   ├── Category badge
│   ├── Icon
│   ├── Description
│   ├── Benefits (3 items)
│   └── Button: "Learn More"
├── Why Choose Us (6 Features)
└── CTA: "Ready to Transform?"

CONTACT Section
├── Hero
├── Contact Info Cards (4)
│   ├── Address
│   ├── Phone
│   ├── Email
│   └── Business Hours
├── Contact Form
│   ├── Name
│   ├── Email
│   ├── Phone
│   ├── Subject
│   ├── Message
│   └── Submit
├── Why Partner With Us (6 Benefits)
└── FAQ (4 Q&A pairs)
```

## 🔗 Navigation Map

```
┌─────────────────────────────────────────────────────────┐
│                   NAVBAR                                 │
│  Logo  │ Home │ About │ Products │ Applications │ Contact│
└──────┬──────┬──────┬──────┬──────────┬───────────┬────────┘
       │      │      │      │          │           │
       ↓      ↓      ↓      ↓          ↓           ↓
    HOME   ABOUT PRODUCTS  APPLS    CONTACT      LOGIN
     │
     ├─→ Section Switch
     ├─→ No URL change
     ├─→ No page reload
     └─→ Smooth animation

Active Indicator:
    ┌─────────────┐
    │ Home (Active)
    │ Green text  │
    │ Green dot   │
    │ Green line  │
    └─────────────┘
```

## 🎯 User Journey

```
1. Visit Website
   ↓
2. Home Section Displays (Default)
   ├─ Hero
   ├─ Stats
   ├─ WhyChooseUs
   ├─ FeaturedProducts
   ├─ CTA
   └─ Footer
   ↓
3. User Clicks "Applications"
   ↓
4. Navbar Indicator Updates
   ├─ "Home" text: gray
   ├─ "Applications" text: green
   ├─ "Applications" shows dot
   └─ "Applications" shows underline
   ↓
5. Content Switches to Applications
   ├─ Hero
   ├─ Crop Solutions (4 cards)
   ├─ Benefits (3 cards)
   ├─ How to Apply (4 steps)
   ├─ Expert Guidance CTA
   └─ Footer (remains visible)
   ↓
6. User Clicks "Contact"
   ↓
7. Contact Form Appears
   ├─ Contact info cards
   ├─ Form fields
   ├─ FAQ section
   └─ CTA buttons
   ↓
8. User Submits Form
   ↓
9. Form Validated & Processed
```

## 🧩 Data Flow

```
User Action
    │
    ↓
Event Handler (onClick)
    │
    ↓
Call Callback Function
    │ onSectionChange('about')
    ↓
Update React State
    │ setActiveSection('about')
    ↓
Trigger Re-render
    │ React detects state change
    ↓
Call renderSection()
    │ switch(activeSection)
    ↓
Return New Component
    │ return <About />
    ↓
React Updates DOM
    │ Replaces old component
    ↓
Animations Start
    │ Framer Motion
    ↓
User Sees New Section
    │ Smooth transition
    ↓
✅ Complete
```

---

These diagrams illustrate the complete architecture and flow of the OMKAR AGRO INDUSTRIES SPA implementation.
