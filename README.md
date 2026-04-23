# Flexible Work Timesheet

A modern, responsive React-based timesheet application with flexible work hour tracking, featuring:

- ✅ **15-minute increments** - Precise time tracking
- ✅ **Flexible work hours** - Track work between 07:00–19:00
- ✅ **Auto-save** - LocalStorage persistence
- ✅ **Balance tracking** - Weekly and cumulative balance calculations
- ✅ **Export functionality** - CSV and Excel (.xls) export
- ✅ **Mobile responsive** - Works on desktop, tablet, and mobile devices
- ✅ **Accessible** - ARIA labels for screen readers

## Quick Start

### Option 1: Using Node.js & npm

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

Then open `http://localhost:5173` in your browser.

### Option 2: Direct HTML (No build required)

1. Open `index.html` directly in a browser
2. The app will work immediately with Tailwind CSS via CDN

## Project Structure

```
Time-sheet/
├── index.html              # Main HTML file
├── package.json            # Dependencies & scripts
├── src/
│   ├── main.jsx           # React entry point
│   ├── App.jsx            # Main timesheet component
├── README.md              # This file
└── .gitignore
```

## Features

### Time Entry
- Date input for each work day
- Start and finish time selectors (15-minute increments)
- Automatic lunch deduction (30 minutes)
- Automatic validation (finish time cannot be before start time)

### Balance Tracking
- **Carry-in**: Balance from previous weeks
- **This week**: Current week balance
- **Carry-out**: Total balance including this week
- **Total balance**: Cumulative across all weeks

### Data Management
- **Add day**: Add new timesheet entries
- **Delete day**: Remove entries (minimum 1 entry always remains)
- **New Week**: Create a new week for tracking
- **Reset**: Clear all saved data

### Export Options
- **CSV Export**: Compatible with Excel, Google Sheets, Numbers
- **XLS Export**: Direct Excel format with formatting

## How It Works

### Time Calculation
- Work hours = (Finish time - Start time) - 0.5 (lunch)
- Daily balance = Work hours - 7.25 (standard hours)
- Weekly balance = Sum of all daily balances
- Total balance = Sum of all weekly balances

### Data Storage
- All data is saved to browser's LocalStorage
- Data persists across sessions
- No data is sent to any server

## Configuration

Modify these constants in `src/App.jsx`:

```javascript
const DAILY_HOURS = 7.25;      // Standard work hours per day
const LUNCH_HOURS = 0.5;       // Lunch break hours
const STORAGE_KEY = "flex_timesheet_v2";  // LocalStorage key
```

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Technologies Used

- **React 18** - UI framework
- **Tailwind CSS** - Styling
- **Vite** - Build tool
- **LocalStorage** - Data persistence

## Accessibility

- ARIA labels on all inputs
- Semantic HTML structure
- Keyboard navigation support
- Screen reader compatible

## License

Open source - Feel free to use and modify!

## Support

For issues or suggestions, please create an issue in the GitHub repository.
