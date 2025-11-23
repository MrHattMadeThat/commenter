# Guide: Using an LLM to Generate Comment Templates

## 🎯 Purpose

This guide helps teachers use AI (like ChatGPT or Claude) to automatically generate professional report card comment templates from their curriculum documents.

## 📋 What You Need

1. **template-blank.json** - The blank template file
2. **Your curriculum document** - PDF, Word doc, or text
3. **Access to an LLM** - ChatGPT (free or paid) or Claude

## 🚀 Step-by-Step Process

### Step 1: Prepare Your Curriculum

Gather your curriculum outcomes. You need:
- Subject/Class name
- Strand names (if applicable)
- Learning outcomes or expectations
- Achievement level descriptions (if available)

**Example sources:**
- Provincial/state curriculum documents
- District scope and sequence
- Unit plans
- Learning standards

### Step 2: Open the Blank Template

Open `template-blank.json` to see the structure:

```json
{
  "classes": {
    "exampleClass": {
      "name": "Example Class Name",
      "subject": "Example Subject",
      "strands": {
        "exampleStrand": {
          "name": "Example Strand Name",
          "outcomes": {
            "exampleOutcome": {
              "title": "Example Outcome Title",
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
  "endingOptions": [...],
  "currentClass": "exampleClass"
}
```

### Step 3: Craft Your LLM Prompt

Use this proven prompt template:

```
I need you to create a JSON file for a report card comment builder app.

CLASS INFORMATION:
- Class Name: [e.g., "Grade 7 English Language Arts"]
- Subject: [e.g., "ELA"]

CURRICULUM STRANDS AND OUTCOMES:
[Paste your curriculum here, organized by strands]

For example:
Strand: Reading Comprehension
- Outcome 1: Identify main ideas and supporting details
- Outcome 2: Make inferences and draw conclusions
- Outcome 3: Analyze author's purpose and perspective

Strand: Writing
- Outcome 1: Write well-organized paragraphs
- Outcome 2: Use varied sentence structures
[etc.]

REQUIREMENTS:
1. Create unique IDs for the class, strands, and outcomes (lowercase, no spaces)
2. For each outcome, write THREE templates:
   - Level 2 (Approaching): Student is developing, needs support
   - Level 3 (Meeting): Student meets grade-level expectations
   - Level 3+ (Strong): Student exceeds expectations
   
3. Each template should:
   - Be 110-140 characters long
   - Use placeholders: {Name}, {They}, {they}, {Their}, {their}, {Them}, {them}
   - Use professional, positive language
   - Be specific to the outcome
   - Focus on what students CAN do

4. Also create 4-6 optional ending comments (positive, varied)

5. Follow this EXACT JSON structure:
[Paste the template-blank.json structure here]

Please generate the complete JSON file now.
```

### Step 4: Review and Refine

The LLM will generate a JSON file. Check for:
- ✅ All strands included
- ✅ All outcomes included
- ✅ Three templates per outcome
- ✅ Templates are 110-140 characters
- ✅ Proper use of placeholders
- ✅ Valid JSON syntax (use jsonlint.com if unsure)

**Common issues to fix:**
- Templates too long → Ask LLM to shorten
- Generic language → Ask for more specific wording
- Missing placeholders → Add {Name}, {They}, etc.
- Wrong format → Provide the template structure again

### Step 5: Save and Import

1. Copy the JSON output
2. Paste into a text editor (Notepad, VS Code, etc.)
3. Save as `[your-subject].json`
4. In the app: **Manage Classes** → **Import JSON File**
5. Select your file
6. Choose MERGE or REPLACE
7. Done! 🎉

## 💡 Example Prompts for Different Subjects

### For Math (with curriculum doc):

```
I have attached the Grade 8 Mathematics curriculum document. Please create a JSON file for the report card comment builder with:

- Class Name: "Grade 8 Mathematics"
- Subject: "Mathematics"

Include all strands from the curriculum. For each outcome, create three comment templates (Level 2, 3, 3+) that are 110-140 characters each and use the placeholders {Name}, {They}, {they}, etc.

Follow the JSON structure from template-blank.json.
```

### For ELA (listing outcomes):

```
Create a JSON file for Grade 6 English Language Arts with these strands and outcomes:

READING:
1. Identify main ideas and key details
2. Make inferences based on text evidence
3. Analyze story elements (plot, character, setting)

WRITING:
1. Write organized multi-paragraph texts
2. Use descriptive language and varied sentences
3. Edit for grammar and mechanics

[etc. for all strands]

Create Level 2, 3, and 3+ templates for each outcome (110-140 characters, using {Name}, {They}, etc.)
```

### For Science:

```
Generate JSON for Grade 7 Science based on these curriculum strands:

Life Science:
- Cell structure and function
- Classification of living things
- Ecosystems and food webs

Physical Science:
- Forces and motion
- Energy transformations
- Properties of matter

[etc.]

Each outcome needs three comment templates with proper placeholders.
```

## 🎨 Customization Tips

### Make Templates More Specific

Instead of generic:
> "{Name} understands the concept."

Ask LLM for specific evidence:
> "{Name} identifies key details and explains their connection to main ideas with good accuracy."

### Add Your Voice

After generation, edit templates to match your teaching language:
- Change "demonstrates" to "shows"
- Add phrases you commonly use
- Adjust formality level

### Vary the Language

For each level, ensure different phrasing:
- Level 2: "is developing," "needs support with"
- Level 3: "demonstrates," "accurately," "with good independence"
- Level 3+: "confidently," "consistently," "strong mastery"

## 🔧 Troubleshooting

### Problem: JSON won't import
**Solution:** 
1. Copy JSON to jsonlint.com
2. Click "Validate JSON"
3. Fix any errors shown
4. Try importing again

### Problem: Templates are too long
**Solution:** Ask LLM:
```
Please rewrite all templates to be exactly 110-140 characters. Keep the meaning but make them more concise.
```

### Problem: Templates are too generic
**Solution:** Ask LLM:
```
Make the templates more specific to the learning outcome. Include concrete evidence of what students can do at each level.
```

### Problem: Placeholders missing
**Solution:** Ask LLM:
```
Go through all templates and ensure they use {Name} for the student's name and {They}/{they}/{Their}/{their} for pronouns.
```

## ✅ Quality Checklist

Before importing, verify:

- [ ] Class name and subject are correct
- [ ] All strands have clear names
- [ ] All outcomes are included
- [ ] Each outcome has exactly 3 templates (2, 3, 3+)
- [ ] Templates are 110-140 characters
- [ ] All templates use {Name} and pronoun placeholders
- [ ] Language is professional and positive
- [ ] Templates are specific to each outcome
- [ ] 4-6 ending comments included
- [ ] JSON is valid (no syntax errors)

## 📚 Resources

**Validate JSON:**
- jsonlint.com
- jsonformatter.org

**LLM Platforms:**
- ChatGPT: chat.openai.com (free & paid)
- Claude: claude.ai (free & paid)
- Anthropic API (programmatic access)

**Character Counters:**
- Use any online character counter
- Most text editors show character count

## 🤝 Sharing with Colleagues

Once you've created a good JSON file:

1. **Export** your data from the app
2. **Share** the JSON file
3. **Provide** this guide
4. They **import** into their copy of the app

This way, your entire department can have consistent, professional comment templates!

## 💬 Example Conversation with LLM

**You:**
```
I need help creating report card comment templates for Grade 5 Math. 
Here's my curriculum: [paste document]

Please create a JSON file following the template-blank.json structure. 
Each outcome needs three templates (Level 2, 3, 3+) that are 110-140 
characters and use placeholders like {Name} and {They}.
```

**LLM:**
```json
{
  "classes": {
    "grade5Math": {
      "name": "Grade 5 Mathematics",
      "subject": "Mathematics",
      "strands": {
        ...
      }
    }
  }
}
```

**You (if needed):**
```
Can you make the templates more specific? Instead of "understands 
fractions," describe what they can actually DO with fractions.
```

**LLM:**
```
I'll revise all templates to include specific, observable actions...
```

## 🎓 Pro Tips

1. **Start Small**: Begin with one strand to test the process
2. **Iterate**: Generate, test, refine, repeat
3. **Save Versions**: Keep backups as you refine templates
4. **Get Feedback**: Have colleagues review before finalizing
5. **Update Yearly**: Refresh templates based on what works best

---

**Questions?** The LLM can help! Just ask it to:
- Shorten templates
- Make language more/less formal
- Add more variety
- Fix JSON errors
- Explain the structure

Happy template generating! 🚀