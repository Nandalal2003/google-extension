# Lead Tracker Chrome Extension

A simple Chrome extension for tracking and managing leads by saving URLs and custom notes.

## Features

- **Save Tab**: Save the current active tab's URL with a timestamp
- **Save Input**: Save custom lead information from text input
- **Delete All**: Clear all saved leads with one click
- **Persistent Storage**: Leads are saved locally and persist across browser sessions
- **Easy Export**: Copy leads to clipboard for easy sharing

## Installation

### Load as Unpacked Extension (Development)

1. Clone or download this repository
2. Open Chrome and go to `chrome://extensions/`
3. Enable **Developer mode** (toggle in top right corner)
4. Click **Load unpacked**
5. Select the extension folder containing `manifest.json`

## How to Use

### Save Current Tab
1. Navigate to any webpage you want to save as a lead
2. Click the Lead Tracker extension icon in your toolbar
3. Click the **SAVE TAB** button
4. The current page URL will be saved with a timestamp

### Save Custom Input
1. Type any lead information in the text input field
   - Name and contact details
   - Company information
   - Notes or reminders
   - Any other relevant lead data
2. Click the **SAVE INPUT** button
3. The text will be saved as a new lead

### Manage Saved Leads
- Each lead appears as a list item with its content and timestamp
- Click any saved lead to open the URL (if it's a web link)
- Use **DELETE ALL** to remove all saved leads
- Click **COPY ALL** to copy all leads to clipboard

## Files Structure

```
lead-tracker-extension/
├── manifest.json          # Extension configuration
├── index.html            # Popup interface
├── style.css             # Styling for the popup
├── script.js             # Main JavaScript functionality
├── icon.png              # Extension icon (16x16, 48x48, 128x128)
└── README.md             # This documentation
```

## Technical Details

### Technologies Used
- HTML5, CSS3, JavaScript (ES6+)
- Chrome Extension Manifest V3
- Chrome Storage API for data persistence
- Chrome Tabs API for accessing current tab information

### Key Functions
- `saveTab()`: Captures and saves the current active tab
- `saveInput()`: Saves user-input text as a lead
- `renderLeads()`: Displays all saved leads
- `deleteAll()`: Clears all saved leads from storage

### Data Storage
Leads are stored using Chrome's `chrome.storage.local` API with the following structure:
```javascript
{
  "leads": [
    {
      "content": "https://example.com",
      "timestamp": "2024-01-17T10:30:00Z",
      "type": "tab"
    },
    {
      "content": "John Doe - john@example.com",
      "timestamp": "2024-01-17T10:35:00Z",
      "type": "input"
    }
  ]
}
```

## Permissions

This extension requires:
- `activeTab`: To access the current tab's URL
- `storage`: To save leads locally in your browser

## Customization

### Changing Styling
Edit `style.css` to modify:
- Color scheme
- Button styles
- Fonts and typography
- Popup dimensions

### Adding Features
Modify `script.js` to add:
- Lead categorization/tags
- Search functionality
- Export to CSV/JSON
- Lead editing capabilities
- Integration with CRM systems

## Troubleshooting

### Extension Not Appearing
1. Ensure Developer mode is enabled in `chrome://extensions`
2. Reload the extension after making changes
3. Restart Chrome if issues persist

### Leads Not Saving
1. Check browser console for errors (right-click popup → Inspect)
2. Ensure you have sufficient storage space
3. Try clearing extension data and reinstalling

### Buttons Not Working
1. Verify all JavaScript files are loaded correctly
2. Check for JavaScript errors in the console
3. Ensure manifest.json permissions are correctly set

## Development

### Building from Source
1. Clone the repository
2. Make your changes to the source files
3. Test locally by loading as unpacked extension
4. Package for distribution if needed

### Testing
1. Load the extension in Chrome
2. Test all functionality:
   - Save tabs from different websites
   - Save various input types
   - Delete functionality
   - Data persistence after browser restart

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the MIT License.

## Support

For issues, questions, or suggestions:
1. Check the [Issues](../../issues) page
2. Submit a detailed bug report
3. Contact the maintainer

## Version History

### v1.0.0 (Current)
- Initial release
- Basic lead saving functionality
- Local storage implementation
- Simple popup interface

---

**Note**: This extension stores data locally in your browser. Data will be lost if you:
- Clear browser data
- Uninstall the extension
- Use a different browser/computer

Always export important leads before performing these actions.
