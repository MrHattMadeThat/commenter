# Report Card Comment Builder

A professional, expandable tool for teachers to generate concise report card comments quickly and efficiently.

## Features

### 🎯 Core Functionality
- **Outcome Selection**: Choose from multiple learning outcomes with checkboxes
- **Achievement Levels**: Select Level 2 (Approaching), Level 3 (Meeting), or Level 3+ (Strong) for each outcome
- **Auto-Generation**: Combines templates into a cohesive 600-700 character comment
- **Student Personalization**: Automatically inserts student name and correct pronouns (they/them, she/her, he/him)
- **Optional Endings**: Add personality with customizable closing sentences
- **Character Counter**: Real-time feedback with color coding (green < 650, orange < 700, red > 700)

### ✏️ Template Editor
- **Full Control**: Edit all comment templates directly in the app
- **Add New Outcomes**: Expandable system for future curriculum additions
- **Manage Endings**: Edit the optional closing comments
- **Persistent Storage**: All changes saved to browser's localStorage
- **Reset Option**: Restore default templates anytime

### 📋 User Experience
- **Copy to Clipboard**: One-click copying of generated comments
- **Manual Editing**: Fine-tune generated comments before copying
- **Clear All**: Quick reset for the next student
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Beautiful UI**: Modern gradient design with smooth transitions

## Initial Outcomes Included

1. **Place Value to the Millions**
2. **Adding & Subtracting Decimals to Thousandths**
3. **Standard / Expanded / Word Form**
4. **Prime/Composite + Factor Trees**

Each outcome includes three achievement level templates.

## How to Use

### Generating a Comment

1. Open `index.html` in your web browser
2. Enter the student's name
3. Select pronouns (they/them, she/her, or he/him)
4. Check the outcomes you taught
5. Select the achievement level for each outcome
6. (Optional) Choose an ending comment
7. Click "Generate Comment"
8. Review and edit if needed
9. Click "Copy to Clipboard"

### Editing Templates

1. Click the "Template Editor" tab
2. Edit any template text in the textareas
3. Modify ending options as desired
4. Click "Save Changes"
5. Templates are automatically saved to your browser

### Resetting to Defaults

1. Go to the "Template Editor" tab
2. Click "Reset to Defaults"
3. Confirm the action

## Technical Details

### Storage
- Uses browser's localStorage for persistence
- No server required - runs entirely in the browser
- Data stored in JSON format

### Template Variables
Templates support the following placeholders:
- `{Name}` - Student's first name
- `{they}/{them}/{their}` - Lowercase pronouns
- `{They}/{Them}/{Their}` - Capitalized pronouns

### File Structure
```
report-card-comment-builder/
├── index.html          (Complete single-file application)
└── README.md          (This file)
```

## Future Expansion Ideas

- Add more subjects (ELA, Social Studies, Science)
- Drag-and-drop outcome reordering
- Import/export template databases
- Multiple student batch processing
- Print-friendly formatting
- Additional pronoun options
- Custom outcome creation interface

## Browser Compatibility

Works in all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

Requires JavaScript enabled and localStorage support.

## Notes for Teachers

- Each template is designed to be ~110-140 characters
- 4-5 outcomes typically fit within the 700 character limit
- The system automatically trims and combines sentences
- Templates use professional, curriculum-appropriate language
- Focus on growth and achievement, not deficits

## License

Free to use and modify for educational purposes.

## Support

For issues or questions, refer to the feature documentation in the template editor panel.
