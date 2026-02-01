# Life & Training Hub

A personal productivity ecosystem featuring three integrated web applications for milestone tracking, mobility workouts, and training plan management.

## Features

### 📍 Milestone Timeline
- Beautiful snaking timeline visualization of life events
- Track past and future milestones with detailed "what, when, why, results" fields
- Organic flow design with years marked at turning points
- Full data export/import capabilities

### 🧘 Mobility Tracker
- Structured weekly mobility workout plans
- Progress tracking with completion percentages
- Detailed exercise guidance and protocols
- Day-by-day workout organization

### 💪 Workout Finder
- Quick access to Block 3 training plan (12 weeks)
- RPE targets and support protocols for each session
- Three training phases: Speed Development, Peak Speed, HM Transition
- Minimal clicks to reach any workout information

## Technology Stack

- **HTML5/CSS3/JavaScript** - Pure vanilla implementation
- **Progressive Web App (PWA)** - Installable on any device
- **localStorage** - Client-side data persistence
- **Responsive Design** - Optimized for mobile and desktop

## Getting Started

### Deployment to GitHub Pages

1. **Create a new GitHub repository**
   ```bash
   # Initialize your repository
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/yourusername/your-repo-name.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository Settings
   - Navigate to "Pages" in the left sidebar
   - Under "Source", select "main" branch
   - Click "Save"
   - Your site will be live at: `https://yourusername.github.io/your-repo-name/`

### Local Development

Simply open `index.html` in a web browser. For best results, use a local server:

```bash
# Python 3
python -m http.server 8000

# Node.js (with npx)
npx serve

# Then open http://localhost:8000
```

## Installation as PWA

### On iPhone/iPad:
1. Open the site in Safari
2. Tap the Share button
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add"

### On Android:
1. Open the site in Chrome
2. Tap the three-dot menu
3. Tap "Add to Home Screen"
4. Tap "Add"

### On Desktop (Chrome/Edge):
1. Look for the install icon in the address bar
2. Click "Install"

## File Structure

```
.
├── index.html              # Main landing page
├── milestone-timeline.html # Timeline application
├── mobility-tracker.html   # Mobility workout tracker
├── workout-finder.html     # Training plan finder
├── manifest.json          # PWA manifest
├── service-worker.js      # PWA service worker for offline support
└── README.md             # This file
```

## Data Storage

All applications use browser localStorage for data persistence:
- **Milestones**: Stored as JSON array in `milestones` key
- **Mobility Progress**: Stored per workout in `workout_[day]_progress` keys
- **Training Data**: Embedded in workout-finder.html (Block 3 data)

## Customization

### Colors
The apps use a warm color palette with sage green accents:
- Primary: `#8b9d83` (sage green)
- Background: `#f5f3f0` to `#e8e4df` gradient
- Text: `#2c3e50` (dark blue-gray)

### Fonts
- **Headings**: Cormorant Garamond (serif)
- **Body**: Nunito Sans (sans-serif)

### Training Data
To update the workout finder with different training blocks, edit the `trainingData` object in `workout-finder.html`.

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari 14+
- iOS Safari 14+
- Chrome for Android

## Privacy

All data is stored locally in your browser. No data is sent to external servers. Data export/import features allow you to back up your information.

## License

Personal use project. Feel free to adapt for your own needs.

## Version

Current version: 1.0.0

---

Built with care for personal productivity and wellness tracking.
