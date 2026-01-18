# Nandus Lead Tracker - Chrome Extension

A lightweight Chrome extension for tracking and managing important leads and URLs directly from your browser.

## 📋 Features

- **Save Custom Leads**: Manually input and save any important leads or URLs
- **Save Current Tab**: Quickly save the URL of your currently active tab
- **Persistent Storage**: All leads are saved to localStorage and persist between browser sessions
- **Clean Interface**: Simple, intuitive user interface with easy-to-use buttons
- **One-Click Access**: All saved leads open in new tabs with a single click
- **Bulk Delete**: Double-click to delete all saved leads at once

## 🛠️ Installation

### Local Installation (Developer Mode)

1. Download or clone this repository
2. Open Chrome and navigate to `chrome://extensions/`
3. Enable "Developer mode" (toggle in top-right corner)
4. Click "Load unpacked" button
5. Select the folder containing the extension files

### Files Included

- `manifest.json` - Extension configuration
- `index.html` - Main popup interface
- `index.js` - Core JavaScript functionality
- `index.css` - Styling
- `icon.png` - Extension icon (multiple sizes)

## 🚀 How to Use

### Using the Extension

1. Click the extension icon in your Chrome toolbar
2. The popup window will appear with three main sections:
   - Input field for manual lead entry
   - Action buttons
   - List of saved leads

### Main Functions

#### Save a Custom Lead
1. Type your lead/URL in the input field
2. Click "SAVE INPUT" button
3. The lead will appear in the list below

#### Save Current Tab
1. Navigate to any webpage you want to save
2. Click the extension icon
3. Click "SAVE TAB" button
4. The current page URL will be saved to your leads

#### Delete All Leads
1. **Double-click** the "DELETE ALL" button
2. All saved leads will be permanently removed
3. Confirmation dialog is shown

#### Opening Saved Leads
- Click any lead in the list to open it in a new tab

## 🎯 Technical Details

### Browser Permissions
- `tabs`: Required to capture and save current tab URLs

### Storage
- Uses Chrome's `localStorage` API
- Data persists across browser sessions
- Stored as JSON string for easy parsing

### Key Components

#### Manifest Configuration (`manifest.json`)
- Manifest version 3 (modern Chrome extension standard)
- Browser action popup interface
- Tab permissions for URL capture
- Multi-size icon support

#### JavaScript Functions (`index.js`)
- `render(leads)`: Displays all leads in a formatted list
- Event listeners for all button actions
- localStorage integration for data persistence
- Chrome tabs API integration

#### Styling (`index.css`)
- Responsive design with minimum width/height constraints
- Green (#5f9341) primary color scheme
- Clean, modern button styling
- Proper spacing and typography

### Event Handlers

| Button | Event | Function |
|--------|-------|----------|
| SAVE INPUT | Click | Saves input field value to leads |
| DELETE ALL | Double-click | Clears all saved leads |
| SAVE TAB | Click | Saves current tab URL to leads |

## 🔧 Development

### Code Structure

```javascript
// Main data storage
let myLeads = []  // Array of current leads
let oldLeads = ["nandalal"]  // Example initial data

// DOM Elements
const inputEl, inputBtn, ulEl, deleteBtn, tabBtn

// Event Listeners
// - inputBtn: Add new lead from input
// - deleteBtn: Clear all leads (double-click)
// - tabBtn: Save current tab URL
```

### Extending Functionality

To add new features:

1. **Add Export Feature**:
```javascript
const exportBtn = document.getElementById("export-btn")
exportBtn.addEventListener("click", function() {
    // Export leads as JSON or text file
})
```

2. **Add Categories/Tags**:
```javascript
myLeads.push({
    url: url,
    title: title,
    category: "work",
    tags: ["important", "followup"]
})
```

3. **Add Search Filter**:
```javascript
function filterLeads(searchTerm) {
    return myLeads.filter(lead => lead.includes(searchTerm))
}
```

## 📁 File Structure

```
nandus-lead-tracker/
├── manifest.json      # Extension configuration
├── index.html        # Popup interface
├── index.js          # Core functionality
├── index.css         # Styling
└── icon.png          # Extension icon
```

## ⚠️ Limitations

- No cloud sync (leads are browser-specific)
- No backup/export functionality (planned feature)
- No categorization or tagging (planned feature)
- Simple search functionality (planned feature)

## 🔮 Planned Features

- [ ] Export leads to CSV/JSON
- [ ] Import leads from file
- [ ] Categorize leads with tags
- [ ] Search/filter functionality
- [ ] Lead notes/descriptions
- [ ] Keyboard shortcuts
- [ ] Sync across devices (using Chrome sync storage)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is open source and available for personal and commercial use.

## 🐛 Troubleshooting

### Common Issues

**Extension not appearing in toolbar:**
- Restart Chrome after installation
- Check if extension is enabled in `chrome://extensions/`

**Leads not saving:**
- Ensure you have storage permissions enabled
- Check Chrome console for errors (F12)

**Save Tab not working:**
- Verify the extension has "tabs" permission
- Check if you're on a valid webpage (not chrome:// pages)

## 📞 Support

For issues or questions, please:
1. Check the troubleshooting section above
2. Review the Chrome developer documentation
3. Submit an issue on the repository

---

**Note**: This extension stores all data locally in your browser. Uninstalling the extension will permanently delete all saved leads.
