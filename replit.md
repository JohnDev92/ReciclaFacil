# ReciclaFácil - Santa Cruz da Serra

## Overview

ReciclaFácil is a web-based interactive mapping application designed for the Santa Cruz da Serra community to facilitate recycling efforts. The application provides an interactive map interface where users can view, add, and manage recycling collection points. It features a location-based service that helps residents find nearby recycling facilities and contribute to the community's environmental initiatives.

The application is built as a lightweight, client-side web application with no backend server requirements, making it easy to deploy and maintain.

## User Preferences

Preferred communication style: Simple, everyday language.
Preferred language: Portuguese (Brazilian).

## System Architecture

### Frontend Architecture

**Technology Stack:**
- Pure HTML/CSS/JavaScript (vanilla JS, no framework dependencies)
- Leaflet.js for interactive mapping functionality
- Leaflet MarkerCluster plugin for efficient marker grouping
- Mobile-responsive design with flexbox layout

**UI Components:**
1. **Interactive Map Container** - Full-viewport map display using Leaflet with 100px bottom padding to accommodate control bar
2. **Form Container** - Overlay form for adding new recycling points (initially hidden)
3. **Sidebar Panel** - Slide-out panel for managing existing locations with add/delete functionality
4. **Control Bar** - Fixed bottom bar (16px from edges) containing:
   - Contact buttons (left): WhatsApp Disk Entulho and Prefeitura phone
   - Map controls (right): Layer toggle and Points sidebar toggle

**Design Decisions:**
- Single-page application architecture for simplicity and fast load times
- Absolute positioning with z-index layering for UI elements (form: 1000, sidebar: 900, control bar: 1001)
- Responsive design using viewport units (100vh) and flexbox
- Transition animations for smooth UI interactions (sidebar slide: 0.3s ease)
- Mobile-first responsive control bar (stacked buttons on mobile <768px, horizontal layout on desktop)
- Map padding ensures Leaflet attribution remains visible below control bar

**State Management:**
- Client-side state management (likely using JavaScript variables)
- No persistent storage solution currently implemented in the provided code
- Future implementation would likely use localStorage or IndexedDB for offline persistence

### Map Architecture

**Leaflet Integration:**
- Core mapping library for tile rendering and interaction
- MarkerCluster plugin for performance optimization when displaying multiple points
- Custom marker styling and popup functionality for location details

**Map Features:**
- Interactive marker placement
- Clustering for dense marker areas
- Pan and zoom controls
- Location-based services integration (expected)

### Data Model

**Recycling Points:**
Expected structure includes:
- Location name/description
- Geographic coordinates (latitude/longitude)
- Marker metadata (type, status, etc.)

The data model appears to support CRUD operations through the sidebar interface (Create via form, Read via map display, Update implicitly, Delete via "excluir" button).

### Communication Features

**Contact Integration:**
- **WhatsApp Disk Entulho**: Direct link to (21) 99019-1331 via https://wa.me/5521990191331 
  - Green button (#25D366 brand color) with phone emoji
  - Opens WhatsApp app/web with pre-configured number
  
- **Prefeitura Phone**: Direct call to (21) 3900-1651 via tel:+552139001651
  - Blue button (#2196F3) with phone emoji
  - Displays service hours: seg-sex 8h-17h (Monday-Friday 8am-5pm)
  - Opens native phone dialer on mobile devices

- Buttons positioned in fixed control bar (bottom-left) for easy access
- Responsive layout: side-by-side on desktop, stacked on mobile

## External Dependencies

### Third-Party Libraries

1. **Leaflet.js** (unpkg CDN)
   - Purpose: Core interactive mapping functionality
   - Provides: Tile rendering, marker management, user interactions
   - Rationale: Industry-standard, lightweight, open-source mapping library

2. **Leaflet MarkerCluster** (unpkg CDN)
   - Purpose: Efficient marker grouping and performance optimization
   - Provides: Automatic clustering of nearby markers, dynamic cluster sizing
   - Rationale: Essential for handling multiple recycling points without performance degradation

### CDN Strategy

**Decision:** Using unpkg CDN for all external dependencies
- **Pros:** No build process required, faster initial setup, automatic caching, reduced hosting requirements
- **Cons:** Dependency on external service availability, potential version conflicts, no offline functionality
- **Rationale:** Appropriate for lightweight community application with expected stable internet connectivity

### Map Tile Provider

**Implementation:** Leaflet typically uses OpenStreetMap or similar tile providers
- **Expected:** Default OpenStreetMap tiles or custom tile layer
- **Data Flow:** Tiles loaded on-demand as users pan/zoom
- **Performance:** Browser caching handles repeat tile requests

### Contact Services

1. **WhatsApp Integration**
   - Direct WhatsApp link using `wa.me` protocol
   - Format: https://wa.me/5521990191331 (international format with country code)
   - Opens WhatsApp client for "Disk Entulho" service
   - Target: _blank (opens in new tab/window)

2. **Tel Protocol**
   - Native phone dialer integration using `tel:` protocol
   - Format: tel:+552139001651 (full international format)
   - Direct call initiation to Prefeitura on mobile devices
   - Service hours displayed: Monday-Friday 8am-5pm

### Future Considerations

The current implementation is entirely client-side. Potential future integrations may include:
- Backend API for persistent data storage
- Authentication service for user management
- Geolocation API for automatic user positioning
- Social sharing integrations
- Analytics tracking (Google Analytics or similar)