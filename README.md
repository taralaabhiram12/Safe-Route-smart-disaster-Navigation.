# SafeRoute - Smart Disaster Navigation System

A complete, static web application for disaster navigation, emergency coordination, and community aid management. **Zero dependencies, works offline, pure HTML/CSS/JavaScript.**

## 📁 Project Structure

```
SafeRoute/
├── index.html              # Professional landing page
├── login.html              # Dual-tab login (Users & Donors)
├── map.html                # Interactive live map with navigation
├── emergency.html          # Emergency coordination center
├── assets/
│   ├── style.css           # Global styling (modern dark theme)
│   ├── home.js             # Homepage logic
│   ├── login.js            # Login functionality
│   ├── map.js              # Map & disaster features
│   └── emergency.js        # Emergency coordination logic
└── images/
    └── logo.png            # SVG logo
```

## 🚀 Getting Started

1. **Clone/Download** the SafeRoute folder
2. **Open `index.html`** in any modern browser
3. No installation, no build tools, no backend needed!

## 📄 Page Guide

### 1. **Homepage** (`index.html`)
Professional landing page with:
- Sticky navigation bar
- Animated hero section with map preview
- 6 feature cards (Location, Shelters, Hazards, Routing, Safety, Offline)
- Step-by-step "How It Works" section
- About SafeRoute with phone mockup
- Call-to-action section
- Login prompt for donors
- Footer

**Navigate to:** `login.html` or `map.html`

---

### 2. **Login Page** (`login.html`)
Dual-tab authentication system:

#### Tab 1: **User Login**
- Email & password fields
- "Remember me" option
- Forgot password link
- **Continue as Guest** button (anonymous access to map)
- Sign-up prompt

#### Tab 2: **Donor Portal**
- Organization email & password
- Donor registration prompt
- Leads to Emergency Coordination Center

**Features:**
- Split design (branding on left, form on right)
- Smooth tab switching
- Responsive on mobile
- All data stored in localStorage (demo)

---

### 3. **Live Map Page** (`map.html`)
Interactive disaster navigation with:

#### Left Panel Controls:
- **Search Bar** - Find cities, places, or type "shelter"
- **Nearest Shelter** - Auto-route to closest shelter
- **Report Hazard** - Submit fire, flood, blocked road, earthquake, other
- **I'm Safe** - Mark yourself as safe
- **Route Summary** - Shows distance (km) & ETA (minutes)
- **Hazard Alerts** - Real-time hazard feed
- **Back to Home** - Return to homepage

#### Map Features:
- **Your Location** - Green pulsing marker (auto-detected)
- **Shelters** - 3 cyan shelter icons (auto-generated)
- **Hazards** - Color-coded hazard markers (fire=red, flood=blue, etc.)
- **Routes** - Green route lines with distance/ETA
- **Search** - Nominatim API for geocoding
- **Routing** - OSRM public API for driving routes

#### Technology:
- **Leaflet.js** - Interactive map library
- **OpenStreetMap** - Free map tiles
- **Nominatim API** - Free geocoding
- **OSRM** - Free routing API
- **localStorage** - Offline hazard persistence

---

### 4. **Emergency Coordination Center** (`emergency.html`)
Professional disaster management dashboard for donors/organizations:

#### Sidebar Navigation:
1. **Dashboard** - Overview stats & active emergencies
2. **Active Incidents** - Filterable incident table
3. **Aid Requests** - Emergency supply requests from communities
4. **Manage Resources** - Track inventory (medical, shelter, food, transport)
5. **Volunteers** - Coordinate volunteer network
6. **Analytics** - Response metrics & breakdowns

#### Dashboard Features:
- **Real-time Stats** - Emergencies, affected people, resources
- **Emergency Cards** - Click to view details or offer help
- **Quick Actions** - Alert network, create requests, allocate resources
- **Incident Table** - Sortable by type, location, status
- **Aid Requests** - Urgent resources needed (fulfillment tracking)
- **Resource Inventory** - 4 categories with sub-items
- **Volunteer Cards** - Assignment & status tracking
- **Analytics** - Response times, efficiency, incident breakdown

#### Use Cases:
- NGOs coordinate disaster response
- Hospitals request medical supplies
- Food banks provide rations
- Community centers offer shelter
- Volunteers get real-time task assignments

---

## 🎨 Design System

### Color Palette
```
Primary (Green):     #10b981
Secondary (Cyan):    #06b6d4
Success:             #10b981
Warning (Amber):     #f59e0b
Danger (Red):        #ef4444
Info (Cyan):         #06b6d4
Dark Background:     #0f172a
Dark Surface:        #1e293b
Text Primary:        #f1f5f9
Text Secondary:      #cbd5e1
```

### Typography
- **Sans-serif:** System fonts (Apple, Segoe UI, Roboto)
- **Hero Title:** 3.5rem, 900 weight
- **Section Title:** 2.5rem, 800 weight
- **Body:** 1rem, normal weight

### Responsive Breakpoints
- **Desktop:** 1200px+
- **Tablet:** 768px - 1199px
- **Mobile:** 320px - 767px

---

## 🔧 Technical Details

### Frontend Stack
- **HTML5** - Semantic structure
- **CSS3** - Grid, Flexbox, Gradients, Animations
- **JavaScript (Vanilla)** - No frameworks
- **Leaflet 1.9.4** - Map rendering
- **OpenStreetMap** - Tile data (free)
- **Nominatim** - Geocoding API (free)
- **OSRM** - Routing API (free)

### Browser Support
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

### Storage
- **localStorage** - Hazard reports, user sessions, preferences
- **sessionStorage** - Temporary navigation state

### API Integrations (Free & Public)
```
1. OpenStreetMap Tiles
   https://tile.openstreetmap.org/{z}/{x}/{y}.png

2. Nominatim Geocoding
   https://nominatim.openstreetmap.org/search?format=json&q=...

3. OSRM Routing
   https://router.project-osrm.org/route/v1/driving/...
```

---

## 🌍 Features

### For Users
✅ Real-time location tracking  
✅ Find nearby shelters (3-5km radius)  
✅ Smart routing with ETA  
✅ Report hazards (5 types)  
✅ Mark yourself safe  
✅ View community hazard alerts  
✅ Works offline (core features)  
✅ No login required (guest mode)  
✅ Mobile responsive  

### For Donors
✅ View active emergencies  
✅ Filter by incident type  
✅ Respond to aid requests  
✅ Manage resource inventory  
✅ Coordinate volunteers  
✅ Send network-wide alerts  
✅ Real-time analytics  
✅ Task assignment  
✅ Impact tracking  

---

## 📊 Data Flow

### User Emergency Flow
1. User opens `index.html` → clicks "Open Live Map"
2. Browser requests geolocation → shows "You are here" marker
3. 3 shelters auto-generated around user location
4. User searches for shelter or hazard type
5. User clicks shelter → routing calculates path → shows ETA
6. User encounters hazard → submits report
7. Report saved in localStorage → rendered as marker
8. Other users see hazard marker & alert

### Donor Coordination Flow
1. Donor opens `login.html` → enters organization credentials
2. Redirected to `emergency.html` dashboard
3. Views active emergencies in region
4. Creates/fulfills aid requests
5. Allocates resources from inventory
6. Assigns volunteers to tasks
7. Monitors response metrics
8. Sends network-wide alerts

---

## 💾 Local Storage Keys

```javascript
// User Sessions
'user_logged_in'      // {email, type, loginTime}
'user_guest'          // {type: 'guest', loginTime}

// Donor Sessions
'donor_logged_in'     // {email, type, organization, loginTime}

// Disaster Data
'saferoute_hazards'   // Array of hazard objects
                      // [{id, type, description, lat, lng, timestamp}]
```

---

## 🐛 Known Limitations

1. **Offline Mode** - Search/Routing requires internet (Nominatim & OSRM are online APIs)
2. **Geolocation** - Browser must allow location access (can use default NYC if denied)
3. **Data Persistence** - Uses only localStorage (not synced to backend)
4. **Mobile Keyboard** - Search bar may be hidden by mobile keyboard
5. **No Real-time Sync** - Hazards not synced across users (use backend for this)

---

## 🚀 Future Enhancements

1. **Backend Integration**
   - Real-time hazard sync via WebSocket
   - User authentication
   - Database persistence

2. **Advanced Features**
   - Voice commands
   - Real evacuation routes
   - Government agency integration
   - SMS alerts
   - Multi-language support

3. **Analytics**
   - Heatmaps of hazards
   - Response time analysis
   - Resource optimization

4. **Social**
   - User profile pages
   - Community forums
   - Volunteer leaderboards

---

## 📱 Mobile Optimization

- **Responsive grid layouts** (1 → 2 → 3 columns)
- **Touch-friendly buttons** (48px minimum)
- **Optimized control panel** (90vw width on mobile)
- **Adaptive typography** (smaller on mobile)
- **Offscreen navigation** (collapse on <768px)
- **Landscape/portrait modes** supported

---

## 🔐 Security Notes

⚠️ **This is a demo application. For production:**
- Never store sensitive data in localStorage
- Implement proper authentication (JWT, OAuth)
- Use HTTPS for all communications
- Validate all user inputs server-side
- Implement rate limiting on APIs
- Add CORS headers appropriately
- Encrypt sensitive data in transit

---

## 📝 Usage Examples

### Report a Flood
1. Open map page
2. Click "Report Hazard"
3. Select "💧 Flood"
4. Add description
5. Submit → marker appears on map

### Find Nearest Shelter
1. Open map page
2. Click "Nearest Shelter"
3. Green route line appears
4. ETA shows in route summary
5. Click shelter marker for details

### Donate Emergency Supplies
1. Open login page
2. Click "Donor Portal" tab
3. Enter organization credentials
4. View dashboard → browse aid requests
5. Click "I Can Provide"
6. Specify quantities & delivery time

---

## 📞 Support

For issues or questions:
- Check browser console (F12) for errors
- Ensure location permission granted
- Clear localStorage if data corrupted
- Try in different browser
- Check internet connection (for geocoding)

---

## 📄 License

This project is provided as-is for educational and humanitarian purposes.

---

## 🙏 Acknowledgments

- **Leaflet** - OpenStreetMap integration
- **OpenStreetMap** - Free map data
- **Nominatim** - Geocoding service
- **OSRM** - Open routing service
- Built with ❤️ for disaster resilience

---

**SafeRoute v1.0** | Last Updated: November 2025
