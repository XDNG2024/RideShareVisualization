# RideShareVisualization
Create detailed components with these requirements:
1. Use 'use client' directive for client-side components
2. Style with Tailwind CSS utility classes for responsive design
3. Use Lucide React for icons (from lucide-react package). Do NOT use other UI libraries unless requested
4. Use stock photos from picsum.photos where appropriate, only valid URLs you know exist
5. Configure next.config.js image remotePatterns to enable stock photos from picsum.photos
6. Create root layout.tsx page that wraps necessary navigation items to all pages
7. MUST implement the navigation elements items in their rightful place i.e. Left sidebar, Top header
8. Accurately implement necessary grid layouts
9. Follow proper import practices:
   - Use @/ path aliases
   - Keep component imports organized
   - Update current src/app/page.tsx with new comprehensive code
   - Don't forget root route (page.tsx) handling
   - You MUST complete the entire prompt before stopping

NYC Taxi & Ridehailing Analytics Dashboard
</summary_title>

<image_analysis>

1. Navigation Elements:
- Top navigation with: New York, Chicago city selector
- Filter search bar in main content area


2. Layout Components:
- Header section: ~100px height
- Main content: 8-panel grid layout
- Each chart panel: ~400x300px
- 15px padding between panels


3. Content Sections:
- Title and description header
- Data update information
- 8 analytical charts:
  - Trips per day
  - Market share
  - Ridehailing trips per day
  - Ridehailing market share
  - Farebox per trip
  - Monthly farebox per driver
  - Unique vehicles per month
  - Unique drivers per month


4. Interactive Controls:
- City selector buttons
- Filter search input
- Interactive charts with hover states
- Timeline navigation on charts


5. Colors:
- Yellow: #FFD700 (Taxi indicators)
- Blue: #0066CC (Ridehailing indicators)
- Pink: #FF69B4 (Lyft)
- Gray: #808080 (Background elements)
- White: #FFFFFF (Background)


6. Grid/Layout Structure:
- 2x4 grid layout for charts
- Responsive breakpoints at 768px, 1024px, 1440px
- 15px grid gap
- Full-width container with max-width 1440px
</image_analysis>

<development_planning>

1. Project Structure:
```
src/
├── components/
│   ├── layout/
│   │   ├── Header
│   │   ├── ChartGrid
│   │   └── FilterBar
│   ├── features/
│   │   ├── charts/
│   │   └── citySelector/
│   └── shared/
├── assets/
├── styles/
├── hooks/
└── utils/
```


2. Key Features:
- Real-time data visualization
- City-based data filtering
- Interactive chart components
- Data export capabilities
- Responsive layout system


3. State Management:
```typescript
interface AppState {
├── cityData: {
│   ├── selectedCity: string
│   ├── timeRange: DateRange
│   ├── filterQuery: string
├── }
├── chartData: {
│   ├── trips: TripData[]
│   ├── market: MarketData[]
│   └── drivers: DriverData[]
├── }
}
```


4. Routes:
```typescript
const routes = [
├── '/',
├── '/city/:cityId',
├── '/analytics/:metric',
└── '/compare/:cities'
]
```


5. Component Architecture:
- ChartContainer (HOC)
- LineChart
- AreaChart
- FilterComponent
- CitySelector
- DataTable


6. Responsive Breakpoints:
```scss
$breakpoints: (
├── 'mobile': 320px,
├── 'tablet': 768px,
├── 'desktop': 1024px,
└── 'wide': 1440px
);
```
</development_planning>





Next.js route structure based on navigation menu items (excluding main route). Make sure to wrap all routes with the component:

Routes:
- /new-york
- /chicago-city-selector

Page Implementations:
/new-york:
Core Purpose: Display comprehensive information about New York City, including attractions, neighborhoods, and local information
Key Components
- Hero section with dynamic NYC skyline imagery
- Borough selector with interactive map
- Attraction cards grid with filtering options
- Weather widget showing current NYC conditions
- Transit status indicator for subway lines
- Neighborhood guide with search functionality
Layout Structure
- Full-width hero section at top
- Two-column layout for main content (desktop)
- Single column stack for mobile
- Sticky navigation for borough selection
- Grid-based attraction cards (3 columns desktop, 2 tablet, 1 mobile)

/chicago-city-selector:
Core Purpose: Interactive tool for exploring Chicago neighborhoods and selecting areas of interest
Key Components
- Interactive Chicago map with clickable districts
- Neighborhood comparison tool
- Property availability counter
- Transit accessibility scorer
- Community statistics dashboard
- Favorite neighborhood bookmarking system
Layout Structure
- Split screen design (map left, details right) on desktop
- Stackable sections for mobile viewing
- Floating action buttons for key functions
- Collapsible neighborhood information panels
- Bottom sheet navigation on mobile

Layouts:
CityLayout:
Applicable routes
- /new-york
- /chicago-city-selector
Core components
- Global navigation header
- City-specific search bar
- Emergency information banner
- Footer with city resources
- Social sharing buttons
Responsive behavior
- Collapsible navigation menu on mobile
- Adjustable content width based on screen size
- Dynamic font scaling
- Flexible grid system
- Touch-friendly interactive elements on mobile
- Sticky header with scroll behavior
