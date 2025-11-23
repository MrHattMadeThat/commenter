# Quick Start Guide - Report Card Comment Builder v2

## 🚀 5-Minute Setup

### Step 1: Open the App
Open `index-v2.html` in your web browser (Chrome, Firefox, or Edge recommended)

### Step 2: Load Full Grade 6 Math (Optional)
If you want the complete NB Grade 6 Math curriculum:

1. Press F12 to open browser console
2. Open `grade6-math-full.json` in a text editor
3. Copy the entire contents
4. In the console, type:
```javascript
localStorage.setItem('commentDatabaseV2', '...[paste the JSON here]...')
```
5. Press Enter
6. Refresh the page (F5)

You now have 17 outcomes across 7 strands ready to use!

### Step 3: Generate Your First Comment

1. **Comment Builder** tab
2. Enter student name: "Emma"
3. Select pronouns: "she/her"
4. Check 3-4 outcomes (e.g., Decimal Operations, Angles, etc.)
5. Click the achievement level buttons (2, 3, or 3+) for each
6. Click **Generate Comment**
7. Review and edit if needed
8. Click **Copy to Clipboard**
9. Paste into your report card system!

## 📝 Common Tasks

### Add a New Class (e.g., Grade 7 ELA)
1. **Manage Classes** tab
2. **Add New Class** button
3. Name: "Grade 7 English Language Arts"
4. Subject: "ELA"
5. **Create Class**

### Add a Strand
1. **Template Editor** tab
2. Select your class
3. **Add Strand** button
4. Name: "Reading Comprehension"
5. **Add Strand**

### Add an Outcome
1. **Template Editor** tab
2. Find your strand
3. **Add Outcome** button
4. Fill in:
   - Title: "Main Ideas and Supporting Details"
   - Level 2: "{Name} is developing skills in identifying main ideas..."
   - Level 3: "{Name} identifies main ideas and supporting details..."
   - Level 3+: "{Name} expertly analyzes texts for main ideas..."
5. **Add Outcome**

### Edit a Template
1. **Template Editor** tab
2. Find the outcome
3. Click in the textarea
4. Edit the text
5. **Save All Changes** button

## 💡 Pro Tips

### Template Variables
Always use these in your templates:
- `{Name}` becomes "Emma" or "James"
- `{They}` becomes "She" or "He" or "They"
- `{they}` becomes "she" or "he" or "they"
- `{their}` becomes "her" or "his" or "their"

### Perfect Length
- Each template: 110-140 characters
- Select 4-5 outcomes = perfect 600-700 character comment
- Watch the character counter (green = good, orange = close, red = too long)

### Workflow for 30 Students
1. Open the app
2. Select your class
3. For each student:
   - Type name (5 seconds)
   - Check 4 outcomes (10 seconds)
   - Click levels (10 seconds)
   - Generate, copy (5 seconds)
   - **Total: 30 seconds per student = 15 minutes for whole class!**

## 🎯 Your First Real Use Case

**Scenario**: You're completing report cards for Grade 6 Math, Term 1. You taught Number Sense and Operations.

1. Open app, select "Grade 6 Mathematics"
2. Student 1: "Marcus"
3. Check these outcomes:
   - ✅ Large Numbers and Decimals → Level 3
   - ✅ Decimal Operations → Level 3
   - ✅ Prime and Composite Numbers → Level 2
   - ✅ Multiples and Factors → Level 3
4. Select ending: "They consistently engage with lessons..."
5. **Generate Comment**
6. Result: 
   > "Marcus demonstrates solid understanding of large numbers and decimals and can explain their place value with good accuracy. He adds, subtracts, multiplies, and divides decimals to hundredths with good accuracy and estimates reasonably. Marcus is learning about prime and composite numbers. He can identify some examples but needs support to sort and classify numbers consistently. Marcus identifies multiples and factors of whole numbers and applies arrays, repeated division, and factor trees with growing independence. He consistently engages with lessons and contributes to class discussions."

7. **Copy to Clipboard** → Paste in report card → Done!

## 🔧 Troubleshooting

**Q: My changes disappeared!**
A: Click "Save All Changes" in Template Editor before switching tabs.

**Q: Comment is too long (red counter)**
A: Select fewer outcomes OR choose shorter ending OR manually edit.

**Q: Can I use this offline?**
A: Yes! Once loaded, works completely offline. Data saves in browser.

**Q: How do I backup?**
A: F12 → Console → `localStorage.getItem('commentDatabaseV2')` → Copy → Save to file

**Q: How do I restore backup?**
A: F12 → Console → `localStorage.setItem('commentDatabaseV2', '...paste here...')` → Refresh

## ✅ Checklist for Term 1

- [ ] Load app
- [ ] Import or create your classes
- [ ] Add all strands you teach
- [ ] Add all outcomes you assess
- [ ] Test with a few student names
- [ ] Adjust templates if needed
- [ ] Save all changes
- [ ] Generate 30 comments in 15 minutes!
- [ ] Celebrate early mark completion 🎉

---

**Need More Help?**
Check the full README-v2.md for detailed documentation.