# Library Management SPA - Design Guidelines

## Design Approach

**Selected Framework:** Clean, content-focused design inspired by Goodreads and modern library platforms, with Material Design principles for consistency and accessibility.

**Justification:** This library management system requires both professional utility (management features) and visual appeal (book browsing), warranting a balanced approach that prioritizes readability, content discovery, and trustworthiness.

---

## Core Design Elements

### A. Color Palette

**Light Mode:**
- Primary: 28 75% 42% (Deep teal-green, trustworthy library feel)
- Primary Hover: 28 75% 35%
- Background: 0 0% 100% (Pure white)
- Surface: 220 15% 97% (Soft gray for cards)
- Text Primary: 220 20% 15% (Near black)
- Text Secondary: 220 10% 45% (Medium gray)
- Accent: 25 85% 55% (Warm orange for CTAs, book actions)
- Border: 220 15% 88%

**Dark Mode:**
- Primary: 28 65% 50%
- Primary Hover: 28 65% 42%
- Background: 220 20% 10% (Deep charcoal)
- Surface: 220 15% 15% (Elevated cards)
- Text Primary: 0 0% 95%
- Text Secondary: 220 10% 65%
- Accent: 25 80% 60%
- Border: 220 15% 25%

### B. Typography

**Font Families:**
- Headings: 'Merriweather', serif (classic, literary feel via Google Fonts alternative or self-hosted)
- Body: 'Inter', sans-serif (modern, highly readable)
- UI Elements: 'Inter', sans-serif

**Type Scale:**
- Hero Quote: 48px / 56px line-height, font-weight 700
- Page Headings (H1): 36px / 44px, font-weight 700
- Section Headings (H2): 28px / 36px, font-weight 600
- Card Titles (H3): 20px / 28px, font-weight 600
- Body: 16px / 26px, font-weight 400
- Small/Meta: 14px / 20px, font-weight 400

### C. Layout System

**Spacing Primitives:** Tailwind units of 2, 4, 6, 8, 12, 16, 20 (p-2, m-4, gap-8, py-12, etc.)

**Grid System:**
- Container max-width: 1280px (max-w-7xl)
- Content sections: max-w-6xl
- Text blocks: max-w-3xl
- Gutter: 24px (gap-6)

**Responsive Breakpoints:**
- Mobile: Base (< 640px)
- Tablet: md (768px+)
- Desktop: lg (1024px+)
- Wide: xl (1280px+)

### D. Component Library

**Navigation Header:**
- Fixed position, backdrop blur with subtle shadow
- Height: 72px desktop, 64px mobile
- Logo: Left-aligned, 40px height
- Nav links: Center-aligned, 16px font-size with 2px bottom border on hover
- Auth buttons: Right-aligned, Sign Up (accent solid), Sign In (primary outline)
- User greeting: Avatar (40px circle) + "Hi, [Name]" + dropdown menu

**Modal System:**
- Auth Modal: 480px max-width, centered, glass-morphism effect
- Profile Modal: 600px max-width, centered
- Backdrop: Darkened overlay with blur
- Close button: Top-right corner, 24px icon
- Form spacing: mb-6 between fields

**Card Components:**
- Genre Cards: 320px width, 400px height, rounded-lg (8px), hover scale 1.02
- Book Cards: 240px width, aspect-ratio 3/4 cover + 80px content area
- Quote Cards: Full-width, bordered-left with 4px accent stripe
- All cards: Subtle shadow, surface color background

**Forms:**
- Input fields: 48px height, rounded-md, border-2 with focus ring
- Buttons: 48px height primary actions, 40px secondary, rounded-md
- Phone input: Country code dropdown + formatted input field
- Validation: Red-500 error text below fields

**Grid Layouts:**
- Genre Grid: 1 column mobile, 2 tablet, 3-4 desktop (grid-cols-1 md:grid-cols-2 lg:grid-cols-4)
- Book Grid: 2 columns mobile, 3 tablet, 4-5 desktop
- Gap: 24px (gap-6)

**Book Detail Page:**
- Two-column layout: 40% cover image, 60% content
- Download button: Accent color, prominent
- Preview button: Primary outline
- Contact librarian: Secondary ghost button

**Notification Bar:**
- Fixed top after header, full-width
- 56px height, sliding animation
- Info (blue), Success (green), Warning (amber), Error (red) variants

### E. Four Scroll Modules

**Home Module:**
- Full viewport height (min-h-screen)
- Two-column split: 50% quote (left), 50% animated video (right)
- Quote: Large serif typography, subtle fade-in animation
- Video: Auto-play muted, loop, subtle parallax scroll effect

**Overview Module:**
- Padding: py-20
- Horizontal scrolling cards or 3-column grid
- Quote cards with supporting images, staggered reveal on scroll
- Background: Alternating surface color sections

**About Module:**
- Padding: py-20
- Max-width prose container for text content
- Social media icons: 48px, circular, hover grow effect
- Visual cards: 3-column grid with icons and statistics

**Contact Module:**
- Padding: py-20, surface background
- Two-column: Form (60%) + Team details (40%)
- Form fields: Email, Phone with country code selector
- Submit button: Full-width accent color
- Success message: "Our team will contact you soon" in gentle green banner

### F. Animations (Minimal)

- Scroll reveals: Subtle fade-up on section entry (200ms ease-out)
- Card hovers: Scale 1.02, shadow increase (150ms ease)
- Button states: Background color transitions (150ms)
- Modal entry: Fade + scale from 0.95 to 1 (200ms)
- Page transitions: Fade between routes (300ms)
- **No** excessive parallax or distracting motion

---

## Images

**Hero Section (Home Module):**
- Animated library video: Panning shot of bookshelves or people reading (mp4, 1920x1080, muted autoplay loop)
- Alternative: Illustrated animation of books floating/opening

**Genre Cards:**
- Each genre: Representative book cover or themed illustration (320x400px)
- Source: Unsplash library/education category or book cover APIs

**Overview Module:**
- Quote cards: Background images of reading spaces, libraries (1200x800px, subtle overlay)

**About Module:**
- Impact cards: Icons or small illustrations (no photos needed)
- Social proof: Team avatars (circular, 64px)

**Book Cards:**
- Cover images: Fetched from Google Books/Open Library API
- Fallback: Placeholder with book icon if API returns no image

**Profile:**
- User avatar: Circular upload, 120px profile view, 40px header
- Default avatars: 6 illustrated options to choose from

---

## Key Design Principles

1. **Content First:** Books and reading material are the heroes; design supports discovery
2. **Accessibility:** WCAG AA contrast ratios, keyboard navigation, screen reader friendly
3. **Performance:** Lazy load images, optimized fonts, minimal animation overhead
4. **Trust & Credibility:** Professional color scheme, serif headings convey literary authority
5. **Mobile-First:** Responsive grids collapse gracefully, touch-friendly 48px targets