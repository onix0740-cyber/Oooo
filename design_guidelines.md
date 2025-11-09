# Design Guidelines: Agricultural Management Platform

## Design Approach

**Selected System:** Material Design 3 principles adapted for agricultural context
**Rationale:** Information-dense application requiring consistent patterns for data visualization, forms, and dashboards while maintaining agricultural aesthetic through imagery and thematic elements.

## Typography Hierarchy

**Font Families:**
- Primary: Inter (UI elements, data, forms)
- Accent: Outfit (headings, hero text)

**Scale:**
- Hero/Display: text-5xl to text-6xl, font-bold
- Page Headings: text-3xl to text-4xl, font-semibold
- Section Headers: text-xl to text-2xl, font-semibold
- Body Text: text-base, font-normal
- Small Text/Labels: text-sm, font-medium
- Data/Metrics: text-lg to text-2xl, font-bold (for numbers)

## Layout System

**Spacing Units:** Consistent use of Tailwind units: 2, 4, 6, 8, 12, 16, 20, 24
- Component padding: p-4 to p-6
- Section spacing: py-8 to py-12
- Page margins: px-4 md:px-8 lg:px-12
- Card gaps: gap-4 to gap-6

**Grid System:**
- Dashboard: 3-column grid on desktop (grid-cols-1 md:grid-cols-2 lg:grid-cols-3)
- Data tables: Full-width with responsive horizontal scroll
- Map interface: 70/30 split (map + sidebar for plot selection)
- Profile editing: 2-column on desktop (avatar/preview + form fields)

## Core Navigation Structure

**Burger Menu (Main Page):**
- Centered button triggers dual side panels (slide from left and right)
- Left panel: Primary navigation (Dashboard, Fields, Resources, Analytics)
- Right panel: Quick actions (AI Assistant, Weather, Notifications, Profile)
- Backdrop blur with overlay when active

**Top Bar:**
- Logo (left)
- Language switcher (RU/EN/UA flags, top-right)
- User avatar + name (clickable to profile)
- Notification bell icon

**Main Navigation Tabs:**
- Horizontal tabs on desktop, collapsible menu on mobile
- Active state with underline indicator
- Icons + text labels for: Monitoring, Resources, Forecasting, Reports, Communication

## Key Components

### Farm Map Interface
- Full-height interactive map (Leaflet.js or Mapbox)
- Fixed sidebar (w-80): Plot list with status indicators, search/filter
- Plot markers with conditional styling (healthy/warning/alert states)
- Click plot → opens detail modal with metrics, weather, and timeline

### AI Assistant Widget
- Fixed position: bottom-right corner (like chat widget)
- Collapsed state: circular button with pulsing indicator
- Expanded state: 400px wide chat panel
- Header: "AI Farm Assistant" + voice toggle button
- Chat messages with avatar (AI uses agricultural icon)
- Input field with microphone icon for voice input
- Voice playback controls for AI responses

### Weather Forecast Widget
- Card-based 7-day horizontal scroll
- Each day: date, icon, temp range, precipitation %
- Expandable for hourly details
- Location selector tied to farm plots

### Profile Editing Page
- Two-column layout: Left (avatar + preview), Right (edit forms)
- Avatar upload: circular preview (150px) with upload overlay
- Tabbed sections: Personal Info, Contact Details, Preferences, Security
- Form fields: Standard input styling with floating labels
- Save button: fixed bottom-right

### Dashboard Cards
- Rounded corners (rounded-xl)
- Subtle elevation (shadow-md)
- Header with icon + title + action button
- Content area: charts, tables, or metrics
- Standard card size: min-h-64, responsive width

### Data Visualization
- Charts: Clean line/bar charts with grid backgrounds
- Tables: Striped rows, sticky headers, sortable columns
- Metrics: Large numbers with small trend indicators (+/- arrows)

## Page-Specific Layouts

**Field Monitoring:**
- Grid of field cards with thumbnails (aerial view images)
- Status badges, key metrics overlay
- Filter bar at top (crop type, health status, area)

**Resource Management:**
- Tabbed interface (Equipment, Water, Fertilizers, Feed)
- Inventory tables with allocation tracking
- Quick action buttons for resource distribution

**Analytics & Reports:**
- Date range selector
- Export buttons (PDF, CSV)
- 2-column metric cards above main chart
- Data table below with pagination

## Iconography
**Icon Library:** Heroicons (outline for navigation, solid for status indicators)
**Agricultural Icons:** Use custom SVG placeholders for farm-specific elements (tractor, crop, livestock)

## Images
- Hero section (homepage): Wide agricultural landscape (field at golden hour, 100vh with gradient overlay)
- Field cards: Aerial/satellite imagery of actual plots
- Empty states: Illustrated farming scenes (friendly, not photorealistic)
- Profile placeholder: Generic avatar with farm icon

## Accessibility
- ARIA labels on all interactive map elements
- Keyboard navigation for map plot selection
- Voice input provides visual feedback during recording
- Language switcher maintains state across sessions
- High contrast for data visualization elements

## Responsive Breakpoints
- Mobile: Single column, stacked navigation, collapsible tables
- Tablet (md): 2-column grids, side-by-side forms
- Desktop (lg): 3-column grids, full feature layouts