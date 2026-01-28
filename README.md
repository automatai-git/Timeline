# Life Journey - Timeline & Mobility Tracker

A Progressive Web App combining milestone timeline tracking with daily mobility workout management.

## New Files for Mobility Tracker Extension

### File Placement in Repository

Place these files in the **root directory** of your existing timeline repository:

```
your-repo/
├── index.html          ← NEW: Landing page (replaces or renames old index)
├── timeline.html       ← RENAME your existing index.html to this
├── mobility.html       ← NEW: Mobility tracker page
├── mobility.css        ← NEW: Mobility tracker styles
├── mobility-data.js    ← NEW: Workout data from your training plan
├── mobility.js         ← NEW: Mobility tracker functionality
├── manifest.json       ← UPDATE: New manifest with both features
├── sw.js              ← KEEP: Existing service worker (update cache list)
├── icon-192.png       ← KEEP: Existing icon
├── icon-512.png       ← KEEP: Existing icon
└── (your existing timeline files...)
```

### Step-by-Step Integration

1. **Rename your existing `index.html`** to `timeline.html`

2. **Copy new files** to the repository root:
   - `index.html` (new landing page)
   - `mobility.html`
   - `mobility.css`
   - `mobility-data.js`
   - `mobility.js`

3. **Replace `manifest.json`** with the updated version

4. **Update your service worker** (`sw.js`) to cache the new files:
   ```javascript
   const CACHE_FILES = [
       '/',
       '/index.html',
       '/timeline.html',      // renamed from index.html
       '/mobility.html',
       '/mobility.css',
       '/mobility-data.js',
       '/mobility.js',
       // ... your existing files
   ];
   ```

5. **Update any internal links** in your timeline files:
   - Change any `href="index.html"` to `href="timeline.html"` if needed
   - Add a back link to the landing page if desired

### Features

#### Landing Page (`index.html`)
- Clean selection between Timeline and Mobility tracker
- Consistent visual style with existing app

#### Mobility Tracker (`mobility.html`)
- **Day Selection**: Quick access to any day's workout
- **Routine Selection**: Pre-workout, Post-workout, or Full sessions
- **Exercise Tracking**: Tap to mark exercises complete
- **Progress Bar**: Visual completion tracking
- **History**: Last 10 sessions displayed
- **Export**: CSV or JSON export for external tracking

### Export Format

The CSV export includes these columns for compatibility with other tracking services:

| Column | Description |
|--------|-------------|
| Date | Formatted date (e.g., "Mon, Jan 27, 2025") |
| Block | Training block number |
| Week | Week of year |
| Day | Day name |
| Routine | Routine name |
| Exercises Completed | Semicolon-separated list |
| Exercises Not Completed | Semicolon-separated list |

### Data Storage

- Workout history is stored in `localStorage` under key `mobilityHistory`
- Data persists across sessions on the same device
- Use export feature for backup or cross-device transfer

### Customization

To modify workouts, edit `mobility-data.js`:

```javascript
const MOBILITY_DATA = {
    monday: {
        name: "Monday - Strength",
        routines: {
            "pre-workout": {
                name: "Pre-Workout Support",
                exercises: [
                    { 
                        order: 1, 
                        name: "Exercise Name", 
                        sets: "2x10", 
                        load: "10kg", 
                        purpose: "Why", 
                        cue: "How to perform" 
                    },
                    // ... more exercises
                ]
            }
        }
    },
    // ... other days
};
```

### PWA Installation

The app works as a PWA on mobile devices:

1. Open in Safari (iOS) or Chrome (Android)
2. Tap "Share" → "Add to Home Screen"
3. The app icon will appear on your home screen
4. App works offline after first load
