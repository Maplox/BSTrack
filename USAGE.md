# Blood Glucose Monitor - Usage Guide

## Overview
This is a comprehensive, single-file Single Page Application (SPA) for blood glucose monitoring that follows American Diabetes Association (ADA) guidelines for diabetes management.

## Opening the Application

### Method 1: Direct Browser Opening
1. Simply double-click the `glucose_monitor.html` file
2. It will open in your default web browser
3. All functionality works offline after the CDN libraries are loaded once

### Method 2: Using a Local Server (Recommended for Development)
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Then navigate to: http://localhost:8000/glucose_monitor.html
```

## Features

### 1. Dashboard Statistics
- **Average Glucose**: Shows your average blood glucose level
- **Highest Reading**: Displays your peak glucose value
- **Lowest Reading**: Shows your minimum glucose value
- **Total Readings**: Count of all recorded measurements

**Color Coding (ADA Guidelines)**:
- �� **Green (Target)**: 70-180 mg/dL (3.9-10.0 mmol/L) - Good control
- 🟠 **Orange (Hyperglycemia)**: >180 mg/dL (>10.0 mmol/L) - High, may need adjustment
- 🔴 **Red (Hypoglycemia)**: <70 mg/dL (<3.9 mmol/L) - Low, needs immediate attention

### 2. Add New Reading
**Required Fields**:
- **Date**: Select the date of measurement
- **Time**: Select time (precision to the minute)
- **Glucose Value**: Enter your blood glucose reading
  - Valid range: 20-600 mg/dL or 1.1-33.3 mmol/L
- **Measurement Context**: Critical for medical interpretation
  - Fasting: First thing in the morning, before eating
  - Pre-meal: Before lunch or dinner
  - Post-meal (1hr): 1 hour after eating
  - Post-meal (2hr): 2 hours after eating (ADA standard)
  - Bedtime: Before going to sleep
  - Random: Any other time

**Optional Fields**:
- **Notes**: Add context about diet, medication, exercise, or how you feel

**Unit Toggle**:
- mg/dL (US Standard): Default, common in the United States
- mmol/L (International): Used in most other countries

### 3. Interactive Graph
- Line chart showing glucose trends over time
- Different colors for different measurement contexts
- Helps visualize patterns and trends
- Reference lines show target range boundaries

### 4. Reading History Table
- Complete log of all measurements
- Sorted by date (newest first)
- Color-coded glucose values for quick assessment
- Delete button to remove erroneous entries

### 5. Export to Excel
- Click "📥 Export to Excel" button
- Downloads a .xlsx file with all your data
- Includes both mg/dL and mmol/L values
- Contains date, time, context, and notes
- Filename includes current date for easy organization

## Medical Guidelines Implemented

### ADA Target Ranges
- **Fasting/Pre-meal**: 80-130 mg/dL (4.4-7.2 mmol/L)
- **Post-meal (2hr)**: <180 mg/dL (<10.0 mmol/L)
- **General Target**: 70-180 mg/dL (3.9-10.0 mmol/L)

### Alert Thresholds
- **Hypoglycemia**: <70 mg/dL (<3.9 mmol/L) - Requires immediate treatment
- **Target Range**: 70-180 mg/dL (3.9-10.0 mmol/L) - Good glucose control
- **Hyperglycemia**: 180-300 mg/dL (10.0-16.7 mmol/L) - May need insulin adjustment
- **Severe**: >300 mg/dL (>16.7 mmol/L) - Urgent medical attention needed

## Data Storage

### IndexedDB (via Dexie.js)
- All data stored locally in your browser
- Persistent across sessions
- No size limits (unlike LocalStorage)
- Data never leaves your device
- HIPAA-friendly (no server transmission)

### Data Privacy
- ✅ 100% local storage
- ✅ No external servers
- ✅ No user accounts required
- ✅ No internet needed (after first load)
- ✅ You control your data

## Browser Compatibility
- Chrome/Edge: Full support
- Firefox: Full support
- Safari: Full support
- Opera: Full support
- Mobile browsers: Fully responsive

## Tips for Best Results

1. **Consistency**: Measure at consistent times daily
2. **Context Matters**: Always select the correct measurement context
3. **Record Notes**: Document meals, medications, or activities
4. **Regular Monitoring**: Check patterns in the graph weekly
5. **Backup Data**: Export to Excel regularly for backup
6. **Consult Healthcare Provider**: Share exports with your doctor

## Troubleshooting

### CDN Libraries Not Loading
- Check your internet connection
- Try refreshing the page
- Ensure no browser extensions are blocking CDN requests
- Try a different browser

### Data Not Saving
- Check browser console for errors (F12)
- Ensure IndexedDB is enabled in browser settings
- Clear browser cache and try again

### Export Not Working
- Ensure popup blockers are disabled
- Try a different browser
- Check if downloads are allowed for the site

## Technical Details

### Technologies Used
- **Dexie.js**: IndexedDB wrapper for robust data storage
- **Chart.js**: Interactive data visualization
- **SheetJS (xlsx)**: Excel export functionality
- **ES6+ JavaScript**: Modern, clean code
- **CSS3**: Responsive, mobile-first design

### File Size
- Single HTML file: ~41 KB
- No external dependencies (except CDN libraries)
- Works completely offline after initial load

## Medical Disclaimer
This application is for tracking and visualization purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult with your healthcare provider regarding your diabetes management plan.
