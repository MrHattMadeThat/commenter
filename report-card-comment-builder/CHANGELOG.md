# Changelog - Report Card Comment Builder

## Version 2.4.0 (Current) - Resources Tab

### Added
- **New Resources Tab**
  - Complete self-service guide for generating classes with AI
  - Download blank template button (generates template-blank.json)
  - Copy AI prompt button (one-click copy with instructions)
  - Step-by-step instructions with links to ChatGPT and Claude AI
  - Tips for best results section
  - Troubleshooting section with common problems and solutions
  
### Resources Tab Features:
1. **Download Blank Template** - Generates and downloads template-blank.json
2. **AI Prompt** - Pre-written prompt that explicitly tells users to provide THREE things:
   - The prompt itself
   - The blank template file
   - Their curriculum document
3. **Copy Prompt Button** - One-click copy with follow-up instructions
4. **Step-by-Step Guide** - 6 clear steps from download to import
5. **Tips Section** - Best practices for AI generation
6. **Troubleshooting** - Solutions for JSON errors, long templates, generic content

### Why This Helps:
- Users no longer need to find external documentation
- Everything needed is in one tab
- Clear emphasis on providing all THREE things to the AI
- Reduces confusion and support requests
- Makes colleague onboarding much easier

### Technical Details
- Added `resourcesPanel` to HTML
- Added `downloadBlankTemplate()` function - generates JSON file on-the-fly
- Added `copyAIPrompt()` function - copies prompt text to clipboard
- Prompt text uses `<pre>` tag with proper formatting
- Links to ChatGPT and Claude AI open in new tabs
- Fourth tab added to navigation

---

## Version 2.3.0 - Engagement Comments

### Added
- **Class Engagement Comments Dropdown**
  - New optional dropdown for comments about student engagement
  - 8 built-in engagement comment options
  - Uses pronoun placeholders ({They}, {they}) for proper grammar
  - Added between curriculum outcomes and ending comment
  - Engagement comments focus on:
    - Participation in discussions
    - Sharing ideas and asking questions
    - Collaboration with peers
    - Listening and attentiveness

### Built-in Engagement Options:
1. "actively participate in class discussions and share insightful ideas"
2. "contribute thoughtfully to class discussions when prompted"
3. "are beginning to share their ideas more confidently in class"
4. "listen attentively and engage with partner discussions"
5. "would benefit from participating more frequently in class discussions"
6. "work well with peers during group activities and discussions"
7. "consistently ask thoughtful questions that deepen understanding"
8. "respectfully build on the ideas of classmates during discussions"

### Comment Structure:
- Curriculum outcomes → Engagement comment (optional) → Ending comment (optional)
- All comments check 700 character limit before adding

### Technical Details
- Added `engagementOptions` array to database structure
- Added `renderEngagementOptions()` function
- Updated `generateComment()` to include engagement comments with pronoun replacement
- Updated `clearAll()` to reset engagement dropdown
- Updated `importData()` to merge engagement options
- Updated `template-blank.json` with engagement options example
- Added to `init()` function

---

## Version 2.2.1 - Import Behavior Fix

### Changed
- **Import Always Adds Classes (Never Replaces)**
  - Removed confusing REPLACE vs MERGE dialog
  - Import now ALWAYS adds new classes to existing ones
  - If duplicate class IDs exist, automatically creates unique IDs
  - Much safer - no risk of accidentally deleting all your classes!
  - Updated import dialog to show class names being imported
  - Updated instructions to reflect new behavior

### Why This Change?
- Users should never accidentally wipe out all their classes
- If you want to remove a class, use the Delete button in Manage Classes
- Simpler, safer, more intuitive
- No more "OK = Replace, Cancel = Merge" confusion

### Technical Details
- Removed conditional logic for replace mode
- Import always merges new classes into existing database
- Confirmation dialog now shows: "Import X class(es): [names]? This will add them to your existing classes."
- Updated `showImportInstructions()` text

---

## Version 2.2.0 - Layout Optimization

### Added
- **Improved Layout for Better Workflow**
  - Student info and comment output now on right column
  - Outcomes selector on left column
  - **Right column stays fixed/sticky while left scrolls** - No scrolling needed!
  - Two "Generate Comment" buttons:
    - Top button: In right column near output (no scrolling needed)
    - Bottom button: After outcomes + auto-scrolls to top to show result
  - Much better workflow: Enter name → Select outcomes → Generate → Copy → Next student
  - No more scrolling back and forth!

### Changed
- **Desktop/Wide View**: 2-column layout (outcomes left, student/output right - sticky!)
- **Mobile/Narrow View**: Single column with student/output first, then outcomes
- Right column uses `position: sticky` to stay visible while scrolling outcomes
- Optimized for teachers working with browser at half-screen width
- Bottom generate button includes helpful text: "(Generates and scrolls to top to see result)"

### Technical Details
- Restructured HTML grid layout
- Added `generateCommentAndScroll()` function with smooth scroll to top
- Added CSS `position: sticky` to right column on desktop (>768px)
- Added CSS flexbox order for mobile to show student info first
- Responsive breakpoint at 768px
- Right column max-height accounts for viewport

---

## Version 2.1.1 - Bug Fix Release

### Fixed
- **Generate Comment Error**: Fixed crash when outcome checkbox was checked but no achievement level was selected
  - Added validation to check for missing level selections
  - Shows helpful alert listing which outcomes need a level selected
  - Prevents "Cannot read properties of undefined" error
  - Added template existence check for extra safety
- **Level Button Click Detection**: Fixed issue where clicking on button text ("Approaching", "Meeting", "Strong") didn't register
  - Now uses `closest('.level-btn')` to find the button regardless of what child element was clicked
  - Improved level extraction from onclick attribute for better reliability

### Technical Details
- Modified `generateComment()` function to track outcomes with missing levels
- Alert now lists specific outcome titles that need level selection
- Added null check for templates before string replacement operations
- Fixed `selectLevel()` to handle clicks on button children (text, br tags)
- Improved regex matching for level parameter extraction

---

## Version 2.1.0 - Import/Export Release

### Added
- **Import/Export Functionality**
  - Import JSON files to load classes and templates
  - Export all data as JSON for backup/sharing
  - Choose between REPLACE (overwrite) or MERGE (keep existing) when importing
  - Automatic handling of duplicate class IDs when merging
  - Instructions modal explaining import/export process

- **Blank Template for Colleagues**
  - `template-blank.json` - Empty template structure
  - Designed for colleagues to fill with their curriculum
  - Perfect for use with LLMs (ChatGPT/Claude) to generate templates
  
- **LLM Generation Guide**
  - `LLM-GUIDE.md` - Comprehensive guide for using AI to generate templates
  - Step-by-step instructions
  - Example prompts for different subjects
  - Troubleshooting section
  - Quality checklist

### Changed
- Manage Classes panel now includes Import/Export section at the top
- Better organization of class management features

### Technical Details
- Added `exportData()` function - downloads JSON file with timestamp
- Added `importData()` function - validates and imports JSON data
- Added `showImportInstructions()` function - displays help modal
- File input element for JSON import (hidden, triggered by button)
- Smart merging prevents duplicate class IDs

---

## Version 2.0.1 - Template Editor Fix

### Fixed
- Template Editor initial load issue (strands wouldn't display until switching classes)
- Added placeholder option "-- Select a class to edit --" to class dropdown
- Template editor now shows helpful message when no class is selected
- Added validation to prevent adding strands without selecting a class first
- Initial render now properly displays placeholder message

### Technical Details
- Modified `renderEditorClassSelect()` to add disabled placeholder option
- Modified `renderTemplateEditor()` to handle empty class selection
- Added `renderTemplateEditor()` call in `init()` function
- Added validation in `showAddStrandModal()`

---

## Version 2.0.0 - Multi-Class Release

### Features
- Multi-class support
- Strand-based organization
- Full CRUD operations (Create, Read, Update, Delete)
- Template editor for all text customization
- Grade 6 NB Mathematics curriculum included (17 outcomes)
- Persistent localStorage storage
- Character counter with visual feedback
- Pronoun support (they/them, she/her, he/him)
- Optional ending comments
- Collapsible strand sections
- Responsive design
- Offline-ready

### Included Content
- 1 default class (Grade 6 Math)
- 1 strand (Number) with 4 outcomes
- Complete NB Grade 6 Math curriculum available as JSON import
- 6 optional ending comments

---

## Version 1.0.0 (Legacy)

### Features
- Single class support
- 4 fixed outcomes
- Template editor
- Basic comment generation
- Character counter
- Pronoun support
- Simple, streamlined interface

---

## Upgrade Path

### From v2.0.x to v2.1.0
Automatic - just replace the HTML file. All data in localStorage remains intact.
New import/export features are immediately available.

### From v1.0 to v2.0+
Manual migration required:
1. Note customizations in v1
2. Open v2
3. Create class
4. Add outcomes
5. Re-enter custom templates

---

## Files in Project

### Core Application
- `index.html` - Version 1 (simple, 4 outcomes)
- `index-v2.html` - Version 2.1 (full-featured, import/export) ⭐

### Data Files
- `grade6-math-full.json` - Complete NB Grade 6 Math (17 outcomes)
- `template-blank.json` - Empty template for colleagues ⭐ NEW

### Documentation
- `README.md` - Version 1 documentation
- `README-v2.md` - Version 2 full documentation
- `QUICKSTART.md` - 5-minute setup guide
- `PROJECT-SUMMARY.md` - Project overview
- `VERSION-COMPARISON.md` - V1 vs V2 comparison
- `DIRECTORY-GUIDE.md` - File structure guide
- `LLM-GUIDE.md` - Guide for generating templates with AI ⭐ NEW
- `CHANGELOG.md` - This file

---

## Known Issues

### v2.1.0
- None currently

---

## Future Enhancements

### High Priority
- ✅ Import/Export functionality (COMPLETED v2.1.0)
- Print-friendly batch mode
- Duplicate class feature
- Template preview before saving

### Medium Priority
- Additional pronoun options (custom pronouns)
- Bulk edit operations
- Template history/undo
- Search/filter outcomes

### Low Priority
- Dark mode
- Additional achievement levels (Level 1, Level 4)
- Multi-language support
- Cloud sync option

---

## Version Numbering

Format: MAJOR.MINOR.PATCH

- **MAJOR**: Breaking changes, major new features
- **MINOR**: New features, non-breaking changes
- **PATCH**: Bug fixes, minor improvements

Current: **2.1.0**

---

## Migration Notes

### v2.0.x → v2.1.0
No migration needed. All existing data works perfectly with new import/export features.

### Using Import/Export
1. Always export your data before major changes
2. Use MERGE mode to add new classes without losing current ones
3. Use REPLACE mode to start fresh with imported data
4. Exported files include timestamp in filename

### Sharing with Colleagues
1. Give them the app (index-v2.html)
2. Give them template-blank.json
3. Give them LLM-GUIDE.md
4. They generate their curriculum JSON with an LLM
5. They import it!

---

## Acknowledgments

v2.1.0 developed based on user feedback requesting:
- Better data portability
- Easier colleague onboarding
- LLM integration for template generation

Thank you to all educators testing and providing feedback! 🎓