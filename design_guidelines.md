# Design Guidelines - Borsa Analiz ve Puanlama Platformu

## Design Approach

**Selected Approach**: Design System + Financial Platform Reference Hybrid

**Primary References**: Robinhood (clean data presentation) + Bloomberg Terminal (information density) + Notion (content hierarchy)

**Core Principle**: Build trust through clarity, professionalism, and data transparency. Financial platforms require precision, readability, and instant comprehension of complex information.

---

## Typography System

**Font Families**:
- Primary: Inter (via Google Fonts) - Exceptional readability for data-heavy interfaces
- Numeric Display: JetBrains Mono - Monospace for financial figures, stock codes, and ratings

**Type Scale**:
- Hero Headlines: 4xl to 6xl, font-weight-800
- Section Headers: 3xl, font-weight-700
- Card Titles: xl, font-weight-600
- Body Text: base, font-weight-400, leading-relaxed
- Data Labels: sm, font-weight-500, uppercase tracking-wide
- Stock Codes: base, JetBrains Mono, font-weight-600
- Ratings/Scores: 2xl to 4xl, font-weight-800, JetBrains Mono

**Turkish Language Optimization**: Ensure proper rendering of Turkish characters (ğ, ü, ş, ı, ö, ç) with adequate letter spacing

---

## Layout System

**Spacing Primitives**: Tailwind units of 2, 4, 6, 8, 12, 16, 20, 24

**Container Strategy**:
- Marketing pages: max-w-7xl, centered
- Dashboard/App: Full-width with max-w-screen-2xl
- Content cards: max-w-4xl for readability
- Analysis detail: max-w-5xl for optimal reading

**Grid Patterns**:
- Stock listing cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Feature showcase: grid-cols-1 md:grid-cols-2 lg:grid-cols-4
- Analysis metrics: grid-cols-2 md:grid-cols-4
- Pricing tiers: grid-cols-1 md:grid-cols-2

**Spacing Consistency**:
- Section padding: py-16 md:py-24 lg:py-32
- Card internal padding: p-6 md:p-8
- Component gaps: gap-4 to gap-8
- Dashboard margins: p-4 md:p-6 lg:p-8

---

## Component Library

### Navigation
**Main Header** (Sticky):
- Logo + platform name (left)
- Navigation links: Ana Sayfa, Analizler, Hakkımızda, Fiyatlandırma
- Right side: Login/Signup buttons or User avatar + dropdown menu
- Height: 16 units, backdrop blur, border-bottom
- CTA button: "Premium'a Geç" - prominent, stands out

**Dashboard Sidebar** (Desktop only):
- Width: 64 units on desktop, collapses to icon-only on tablet
- Sections: Dashboard, Tüm Analizler, Favorilerim, Profil, Ayarlar
- Active state indicator with left border accent
- Subscription status card at bottom

### Stock Analysis Cards
**Grid Card Design**:
- Stock code badge (top-left, monospace, uppercase)
- Company name (bold, truncated if needed)
- Rating score: Large circular badge (60-80px) - positioned top-right
- Rating scale indicator: Visual scale representation
- Key metrics grid: 2x2 or 3x2 layout (P/E, Fiyat, Değişim, etc.)
- Truncated analysis preview (2-3 lines)
- Action buttons: "Detayları Gör" + Heart icon for favorites
- Card states: Default, hover (subtle elevation), favorited (heart filled)

**List View Alternative**:
- Horizontal layout for denser data display
- Stock code | Company | Rating | Key metrics | Action buttons
- Sortable columns, alternating row backgrounds

### Analysis Detail Page
**Hero Section**:
- Stock code + Company name (large, prominent)
- Current price + change percentage (real-time feel)
- Rating score: Extra large display with visual gauge/progress indicator
- Quick actions: Favorile, Paylaş buttons

**Analysis Content Layout**:
- Two-column on desktop (8/4 split)
- Main column: Analysis text (max-w-prose), TradingView charts (responsive embeds)
- Sidebar: Financial metrics cards, Quick stats, Related stocks
- Chart images: Full-width responsive, with zoom capability
- Hisse Takas data: Grid layout for up to 4 PNG files, lightbox on click

**Financial Data Display**:
- Card-based metric groups
- Label-value pairs with clear hierarchy
- Use tables for comparative data
- Highlight significant changes with visual indicators

### Authentication Flows
**Login/Signup Pages**:
- Centered card layout (max-w-md)
- Logo at top
- Form fields with clear labels, generous padding (p-4)
- Social login option placeholder
- "Şifremi Unuttum" link, subtle
- Split-screen option: Form on left, benefits/testimonial on right (desktop)

**Subscription Gates**:
- Modal overlay approach for free users hitting limit
- "5 ücretsiz analiz hakkınız doldu" message
- Benefits comparison: Free vs Premium
- Prominent CTA: "Premium'a Geç - 399 TL/Ay"
- Alternative: "Geri Dön" option

### Admin Panel
**Upload Interface**:
- Step-by-step wizard: 1) Excel Upload → 2) Charts Upload → 3) Takas Data → 4) Preview → 5) Publish
- Drag-and-drop zones with file type indicators
- Progress bars for uploads
- Preview cards showing uploaded content
- Batch operations support
- Clear "Yayınla" and "Taslak Olarak Kaydet" buttons

**Data Management Table**:
- Filterable, sortable stock list
- Bulk actions: Select multiple, delete, republish
- Status indicators: Yayında, Taslak, Arşivlendi
- Quick edit inline for basic fields

### Pricing/Subscription Section
**Comparison Table** (Landing page):
- Two-column layout: Ücretsiz vs Premium
- Feature list with checkmarks/X marks
- Highlight Premium advantages: Sınırsız analiz, Öncelikli destek, etc.
- Sticky CTA button that follows scroll
- Trust indicators: "İstediğin zaman iptal edebilirsin"

### User Dashboard
**Overview Cards**:
- "Kalan Analiz Hakkı" counter (for free users)
- "Favorilerim" quick access carousel
- "Son Eklenen Analizler" grid (3-4 items)
- Activity feed: Recently viewed, trending stocks

**Favorites Management**:
- Grid/List toggle view
- Sort options: Tarih, Rating, Alfabe
- Remove from favorites action
- Empty state: Encouraging message to explore analyses

---

## Landing Page Structure

**Hero Section** (70vh):
- Headline: "Yapay Zeka Destekli Borsa Analizi" (4xl, bold)
- Subheadline: Value proposition (xl, regular)
- CTA buttons: "Ücretsiz Başla" (primary) + "Nasıl Çalışır?" (secondary)
- Hero visual: Dashboard preview mockup or abstract data visualization
- Trust badge: "1000+ Aktif Kullanıcı" or similar social proof

**How It Works** (3-4 steps):
- Horizontal timeline or card progression
- Icons representing: Veri Yükleme → AI Analizi → Sonuç Alma
- Brief description under each step

**Sample Analysis Showcase**:
- 2-3 actual stock analysis cards (preview mode)
- "Örnek Analizi İncele" links
- Demonstrates value immediately

**Features Grid** (3-column):
- AI-Powered Analysis
- Teknik + Temel Analiz
- Puanlama Sistemi
- Sınırsız Erişim (Premium)
- Favori Sistemi
- Güncel Veriler
Each with icon, title, description

**Pricing Section**:
- Side-by-side comparison as described above
- FAQ accordion below: Common questions about subscription, analysis frequency, data sources

**Trust & Credibility**:
- "Neden Bizi Seçmelisiniz?" section
- Transparency statement about AI usage and data sources
- Disclaimer: "Yatırım tavsiyesi değildir" (legal requirement)

**Footer** (Comprehensive):
- Logo + tagline
- Quick links: Platform, Hakkımızda, İletişim, Kullanım Koşulları, Gizlilik
- Social media icons
- Newsletter signup: "Haftalık analiz özetleri" checkbox
- Copyright notice

---

## Images

**Hero Image**: Dashboard mockup showing multiple stock analysis cards with ratings, charts, and clean interface. Should convey professionalism and data richness. Size: 1200x800px minimum, high quality.

**Feature Icons**: Modern line icons from Heroicons (via CDN) - chart-bar, sparkles (for AI), star (for ratings), heart (for favorites), shield-check (for security).

**Sample Charts**: Include 2-3 TradingView-style chart screenshots showing technical analysis patterns (candlesticks, moving averages). These demonstrate what users will receive.

**Testimonial Photos**: Placeholder for 3-4 user avatars (circular crops) if testimonials are added.

**Empty States**: Friendly illustrations for "Henüz favori eklemediniz" and "Analiz bulunamadı" scenarios.

---

## Animations & Interactions

**Minimal & Purposeful**:
- Card hover: Subtle elevation increase (shadow transition)
- Button press: Scale down to 0.98
- Page transitions: Gentle fade-in for new content
- Rating score: Animated count-up on first view (optional, not distracting)
- Loading states: Skeleton screens for data-heavy components
- Success feedback: Checkmark animation on favorite add

**Performance Priority**: No scroll-triggered animations, no parallax effects. Keep it crisp and fast.

---

## Accessibility & Localization

- All interactive elements have 44x44px minimum touch targets
- Form labels always visible (no placeholder-only inputs)
- Error messages in Turkish, clear and actionable
- Focus states: Visible outline on keyboard navigation
- Color contrast: Ensure WCAG AA compliance minimum
- Turkish sorting: Alphabetical sorting respects Turkish alphabet order (Ç after C, etc.)

---

## Responsive Breakpoints

- Mobile: < 768px - Single column, stacked navigation
- Tablet: 768px - 1024px - Two columns, collapsible sidebar
- Desktop: > 1024px - Full layout with permanent sidebar
- Large: > 1536px - Wider containers, more breathing room

---

This design system creates a professional, trustworthy financial platform that balances information density with visual clarity, optimized for Turkish users while maintaining international UX standards.