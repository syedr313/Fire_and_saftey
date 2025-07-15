# TimeTrak Pro - Professional Time & Earnings Tracker

A sleek, ultra-fast Chrome extension for tracking work time, managing flexible sessions, and calculating real-time earnings. Perfect for freelancers, remote workers, and consultants.

## ✨ Features

### Core Functionality
- **One-Click Time Tracking** - Instantly start/stop sessions with a single button
- **Call Outcome Tracking** - Mark sessions as Completed, Disconnected, or Ignored
- **Real-Time Earnings** - Live calculation based on your hourly rate
- **Session Data Logging** - Secure storage of all session data with timestamps

### Advanced Features
- **Smart Calendar Filters** - Filter by last 7, 10, 15, 30 days or custom date ranges
- **Manual Session Addition** - Add forgotten sessions with custom duration and details
- **Beautiful Analytics** - Visual statistics showing calls, hours, and earnings
- **Streamlined UX** - Welcome prompts and intuitive session management
- **Persistent Data** - All data saved locally with Chrome storage backup

### UI/UX Highlights
- Modern, clean design with soft shadows and gradients
- Responsive layout for all screen sizes
- Elegant animations and visual feedback
- Professional watermark branding
- Subtle "Created by Syed" attribution

## 🚀 Installation

### Step 1: Download Files
1. Download or clone this repository
2. Ensure you have both `index.html` and `manifest.json` files

### Step 2: Load Extension in Chrome
1. Open Chrome and navigate to `chrome://extensions/`
2. Enable **Developer mode** (toggle in top right corner)
3. Click **"Load unpacked"**
4. Select the folder containing your TimeTrak Pro files
5. The extension should now appear in your extensions list

### Step 3: Pin Extension
1. Click the extensions icon (puzzle piece) in Chrome toolbar
2. Find "TimeTrak Pro" and click the pin icon
3. The extension icon will now be visible in your toolbar

## 📖 How to Use

### First Time Setup
1. Click the TimeTrak Pro extension icon
2. You'll see a welcome prompt: "Would you like to enable tracking?"
3. Click **"Yes"** to proceed with setup
4. Enter your name and hourly rate (e.g., $25.00)
5. Click **"Start Tracking"** to complete setup

### Starting a Session
- **From Welcome Screen**: Click "Yes" to immediately start tracking
- **From Dashboard**: Click the green "Start Session" button
- The timer will begin running and show real-time earnings

### Ending a Session
1. Click the red "Stop Session" button
2. Choose the session outcome:
   - ✅ **Completed** - Session counts toward earnings
   - ❌ **Disconnected** - Session logged but no earnings
   - 🚫 **Ignore** - Session discarded

### Viewing Analytics
- **Statistics Section**: Shows calls, hours, and earnings for selected period
- **Filter Options**: Last 7/10/15/30 days or custom date range
- **Recent Calls**: Detailed log of recent sessions with timestamps

### Adding Manual Sessions
1. Click the **"+ Add"** button in the Recent Calls section
2. Select the date of the session
3. Enter duration (hours, minutes, seconds)
4. Choose session status (Completed/Disconnected/Ignored)
5. Click **"Add Session"**

## 🎯 Usage Scenarios

### For Freelancers
- Track client calls and consultations
- Generate accurate time reports
- Monitor daily/weekly earnings
- Add missed sessions retroactively

### For Remote Workers
- Track productive work sessions
- Monitor break patterns
- Calculate hourly productivity
- Generate timesheet data

### For Consultants
- Track billable hours per project
- Monitor call completion rates
- Calculate session-based earnings
- Export time logs for invoicing

## 🛠️ Technical Details

### Data Storage
- **Primary**: Chrome Extension Storage API
- **Fallback**: Browser Local Storage
- **Data Persistence**: Automatic saving on all changes
- **Privacy**: All data stored locally on your device

### Browser Compatibility
- Chrome (Manifest V3)
- Chromium-based browsers (Edge, Brave, etc.)
- Minimum Chrome version: 88+

### Performance
- **Load Time**: < 100ms
- **Memory Usage**: < 5MB
- **Storage**: < 1MB per 1000 sessions
- **Offline Support**: Fully functional offline

## 📊 Data Structure

Each session contains:
```javascript
{
    id: timestamp,
    startTime: Date,
    endTime: Date,
    duration: milliseconds,
    status: "completed|disconnected|ignored",
    earnings: number,
    manual: boolean (if manually added)
}
```

## 🔧 Customization

### Hourly Rate Changes
1. The extension doesn't currently support changing hourly rates
2. To modify rates, you can edit the localStorage data:
   - Open Developer Tools (F12)
   - Go to Application > Local Storage
   - Edit the `timetrackPro` entry

### Backup & Export
- **Manual Backup**: Copy localStorage data from Developer Tools
- **Data Export**: Feature planned for future versions

## 🐛 Troubleshooting

### Extension Not Loading
1. Ensure both `index.html` and `manifest.json` are in the same folder
2. Check that Developer mode is enabled
3. Try reloading the extension from `chrome://extensions/`

### Timer Not Working
1. Refresh the extension popup
2. Check browser console for errors (F12)
3. Reload the extension if issues persist

### Data Not Saving
1. Check that Chrome has storage permissions
2. Ensure you're not in Incognito mode
3. Clear browser cache and reload extension

### Common Issues
- **Popup closing**: This is normal Chrome behavior - data is saved automatically
- **Timer stops**: Reopen popup to resume timer display
- **Missing sessions**: Check filter settings - you might be viewing a limited time range

## 🔮 Future Enhancements

### Planned Features
- [ ] Export to CSV/PDF
- [ ] Multiple hourly rates per project
- [ ] Weekly/Monthly reports
- [ ] Dark mode theme
- [ ] Keyboard shortcuts
- [ ] Chrome sync across devices

### Advanced Features (Roadmap)
- [ ] Project categorization
- [ ] Team collaboration
- [ ] API integrations
- [ ] Advanced analytics
- [ ] Mobile companion app

## 📄 License

This project is created for educational and professional use. Feel free to modify and distribute according to your needs.

## 👨‍💻 About

**Created by Syed** - A professional Chrome extension developer focused on productivity tools and user experience design.

### Development Philosophy
- **Minimalism**: Clean, distraction-free interface
- **Performance**: Ultra-fast load times and smooth interactions
- **Reliability**: Robust data handling and error management
- **Accessibility**: Intuitive design for users of all technical levels

---

## 🆘 Support

For issues, feature requests, or questions:
1. Check the troubleshooting section above
2. Review the console logs for error messages
3. Ensure you're using the latest version

**Version**: 1.0  
**Last Updated**: December 2024  
**Manifest Version**: 3 (Latest Chrome Standard)

---

*TimeTrak Pro - Where every second counts towards your success* ⏰💰
