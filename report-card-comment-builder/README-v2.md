# Report Card Comment Builder v2.0

A professional, multi-class, expandable tool for teachers to generate concise report card comments quickly and efficiently.

## 🆕 What's New in v2.0

### Multi-Class Support
- Create and manage multiple classes (Grade 6 Math, Grade 7 ELA, etc.)
- Switch between classes instantly
- Each class maintains its own curriculum structure

### Strand Organization
- Organize outcomes by curriculum strands
- Collapsible strand sections for easy navigation
- Add, edit, and delete strands as needed

### Full CRUD Operations
- **Create**: Add new classes, strands, and outcomes through intuitive modals
- **Read**: View all your content organized by class and strand
- **Update**: Edit templates directly in the template editor
- **Delete**: Remove classes, strands, or outcomes with confirmation

### Enhanced UI
- Modern, responsive design
- Color-coded achievement levels
- Collapsible sections to reduce clutter
- Better visual hierarchy

## 📋 Files in This Project

- **index.html** - Original simple version (4 outcomes, single class)
- **index-v2.html** - NEW! Enhanced version with multi-class support
- **grade6-math-full.json** - Complete Grade 6 NB Math curriculum data
- **README.md** - This documentation

## 🚀 Getting Started

### Option 1: Start Fresh with v2
1. Open `index-v2.html` in your browser
2. The app comes with a starter Grade 6 Math class
3. Add your own classes, strands, and outcomes

### Option 2: Import Full Grade 6 Math Curriculum
1. Open `index-v2.html`
2. Open browser console (F12)
3. Copy and paste the contents of `grade6-math-full.json`
4. Run: `localStorage.setItem('commentDatabaseV2', JSON.stringify(pastedData))`
5. Refresh the page

## 📚 Grade 6 Math Curriculum Included

The `grade6-math-full.json` file contains the complete New Brunswick Grade 6 Mathematics curriculum with:

### Number Strand
- **Number Sense**
  - Large Numbers and Decimals
  - Prime and Composite Numbers
  - Multiples and Factors
  - Fraction and Decimal Equivalents
  - Percentage, Ratio, and Rate

- **Operations**
  - Decimal Operations
  - Fraction and Mixed Number Operations
  - Order of Operations

### Statistics and Probability
- **Data Analysis**
  - Collect and Represent Data
  - Tables of Values and Linear Graphs
  - Cartesian Plane and Transformations

- **Chance and Uncertainty**
  - Probability of Outcomes

### Patterns and Relations
- **Algebra**
  - Equations Using Letter Variables

### Shape and Space
- **Measurement**
  - Perimeter and Area
  - Volume of Right Rectangular Prisms
  - Describe and Measure Angles

- **2-D Shapes and 3-D Objects**
  - Describe and Construct 3D Objects

**Total: 17 curriculum-aligned outcomes** across 7 strands

## 🎯 Key Features

### Comment Builder Tab
- Select your active class
- Enter student name and pronouns
- Check outcomes taught
- Select achievement levels (2, 3, 3+)
- Optional ending comments
- Generate 600-700 character comments
- Real-time character counter
- Copy to clipboard

### Manage Classes Tab
- View all your classes
- See strand counts at a glance
- Add new classes with subject labels
- Delete classes (with protection for last class)

### Template Editor Tab
- Select class to edit
- Add new strands
- Add new outcomes with all three level templates
- Edit existing templates
- Delete strands or outcomes
- Save all changes

## 💡 How to Use

### Creating Your First Class

1. Go to **Manage Classes** tab
2. Click **Add New Class**
3. Enter class name (e.g., "Grade 7 ELA")
4. Enter subject (optional)
5. Click **Create Class**

### Adding Strands and Outcomes

1. Go to **Template Editor** tab
2. Select your class from dropdown
3. Click **Add Strand**
4. Enter strand name (e.g., "Reading Comprehension")
5. Click **Add Strand**
6. Click **Add Outcome** within that strand
7. Fill in outcome title and all three level templates
8. Click **Add Outcome**

### Generating Comments

1. Go to **Comment Builder** tab
2. Select your class
3. Enter student name
4. Select pronouns
5. Check the outcomes you taught
6. Select achievement level for each (2, 3, or 3+)
7. (Optional) Select an ending comment
8. Click **Generate Comment**
9. Edit if needed
10. Click **Copy to Clipboard**

## 🔧 Technical Details

### Storage
- Uses localStorage (key: `commentDatabaseV2`)
- Completely browser-based, no server needed
- Data persists between sessions
- Separate storage from v1 to avoid conflicts

### Template Variables
Use these in your templates:
- `{Name}` - Student's first name
- `{they}/{them}/{their}` - Lowercase pronouns
- `{They}/{Them}/{Their}` - Capitalized pronouns

### Data Structure
```json
{
  "classes": {
    "classId": {
      "name": "Class Name",
      "subject": "Subject",
      "strands": {
        "strandId": {
          "name": "Strand Name",
          "outcomes": {
            "outcomeId": {
              "title": "Outcome Title",
              "templates": {
                "2": "Level 2 template...",
                "3": "Level 3 template...",
                "3plus": "Level 3+ template..."
              }
            }
          }
        }
      }
    }
  },
  "endingOptions": ["ending 1", "ending 2"],
  "currentClass": "classId"
}
```

## 🎨 Achievement Levels

- **Level 2 (Approaching)** - Orange - Student is developing skills
- **Level 3 (Meeting)** - Green - Student meets expectations
- **Level 3+ (Strong)** - Purple - Student exceeds expectations

## 📱 Browser Compatibility

Works in all modern browsers:
- Chrome/Edge ✅ (Recommended)
- Firefox ✅
- Safari ✅
- Opera ✅

Requires JavaScript enabled and localStorage support.

## 🔄 Migrating from v1 to v2

v1 and v2 use different localStorage keys, so they won't conflict. You can:
- Keep both versions
- Manually recreate your v1 content in v2
- Start fresh with the enhanced features of v2

## 💾 Backup Your Data

To backup your data:
1. Open browser console (F12)
2. Type: `JSON.stringify(JSON.parse(localStorage.getItem('commentDatabaseV2')), null, 2)`
3. Copy the output
4. Save to a .json file

To restore:
1. Open browser console (F12)
2. Copy your backup JSON
3. Type: `localStorage.setItem('commentDatabaseV2', JSON.stringify(YOUR_JSON_HERE))`
4. Refresh the page

## 🎓 Tips for Teachers

### Template Writing
- Keep each template 110-140 characters
- Use active, positive language
- Focus on what students CAN do
- Be specific about skills demonstrated
- 4-5 outcomes typically fit in 700 characters

### Organization
- Create separate classes for different subjects
- Use strands to match your curriculum documents
- Start with fewer outcomes and add more as needed
- Test templates with student names to ensure natural flow

### Workflow
1. Set up all your classes and outcomes at the start of term
2. For each report card cycle, select the class
3. Go through your class list systematically
4. Generate, review, copy, paste into report card system
5. 30-60 seconds per student comment!

## 🚀 Future Enhancement Ideas

- Import/export functionality
- Print-friendly batch mode
- Template sharing between classes
- Student comment history
- Additional achievement levels (Level 1, Level 4)
- Custom pronouns
- Bulk operations

## 📄 License

Free to use and modify for educational purposes.

## 🙏 Credits

Built for New Brunswick teachers following provincial curriculum outcomes.

---

**Version History**
- v2.0 (Current) - Multi-class, strand organization, full CRUD operations
- v1.0 - Single class, 4 outcomes, basic functionality