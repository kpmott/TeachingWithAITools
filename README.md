# Creating Teaching Content with AI Tools as Writing Assistants

**Kevin Mott** | [kevinpmott.com](https://kevinpmott.com) \
Assistant Professor, Teaching Stream (Finance)\
Rotman School of Management, University of Toronto

---

## The Problem

Creating your own course materials is exhausting. Especially for niche courses, textbooks may not be suitable. \
**Result:** You spend more time on content creation than on teaching, student interaction, or research.

---

## My Solution: Be an Editor, Not a Writer

Modern AI assistants (ChatGPT, Claude, Gemini, etc.) can function as **best-in-class TA-level writing assistants**. I work iteratively, using the AI tool to create content in the following order. Once a piece is created, I have it refer to the material already done in the other pieces to move forward. The tools handle the "first draft" at every stage:

1. **Lecture slides** (LaTeX/Beamer, PowerPoint, Google Slides, etc.)
2. **Detailed notes** (LaTeX → PDF, Word, Markdown, etc.)
3. **Summary/practical slides**
4. **Practice problems** with solutions

This frees me up from writing (which I'm not good at) and instead allows me to focus on:
- Curating the learning path
- Editing for accuracy and narrative flow
- Adjusting to the level of the students
- Ensuring correctness
- Managing voice and style

The AI handles formatting, drafting, and iteration.

**The real power:** These AI tools are **exceptionally good at writing** and **incredibly nimble** at changing:
- **Tone** (formal → conversational, technical → accessible)
- **Style** (concise → detailed, theoretical → applied)
- **Voice** (textbook → lecture → exam question)
- **Level** (introductory → advanced, undergraduate → masters)

This flexibility means you can rapidly create multiple versions of the same content for different audiences, or iterate until you find the right level for your students. No need to force-fit materials at the wrong level.

**Important caveat:** AI tools almost never make grammar, spelling, or style mistakes—they excel at writing. Content accuracy varies with originality of the topic. However, they **still sometimes make arithmetic mistakes**. **ALWAYS CHECK THE NUMBERS!** Verify calculations, formulas, and numerical examples yourself. (This problem is improving rapidly—it's already better than last year and well on its way to being solved.)

### My preferred tools

I use **Claude Code** as my preferred AI tool, launched in **VS Code** as my preferred IDE, with **LaTeX** as my preferred word processing for a simple reason: because I prefer them. More importantly, the most advanced AI tools today are *best* positioned to work with:
- **Text files** (plain text, Markdown, LaTeX, code files)
- **Directory structures** (organized folders)
- **Version control** (Git)

Tools like Microsoft Office are catching up with AI integration, and I expect that gap to close. **The point isn't my specific workflow or software choices.** The point is that **any AI can now serve as a sophisticated writing assistant**, lowering the cost to faculty to work at a higher level in their teaching:
- Changing curriculum more easily 
- Providing level-appropriate resources
- Adapting to student feedback
- Research and pedagogy

This repository demonstrates one workflow, but the principles apply regardless of your tools.

---

## What's in This Repository

To help defray the cost of using LaTeX, I've included **free Rotman-branded resources** you can use or adapt:

📄 **[Mott_Beamer.sty](Mott_Beamer.sty)** - LaTeX style file for presentation slides
- Clean Beamer theme with UofT/Rotman colors
- Professional formatting for lectures
- Customize for your institution's branding

📄 **[Mott_Handout.sty](Mott_Handout.sty)** - LaTeX style file for handouts
- For assignments, exams, and course notes
- Includes solution toggle functionality (show/hide answers with one command)
- Professional headers and footers with course branding

🖼️ **Rotman logo** (`rotman.png`) - High-quality branding image for headers. Teaching in a different program? Just replace this file. 

📝 **[CLAUDE.md](CLAUDE.md)** - Global AI writing style configuration
- Controls voice, tone, and exposition style across all generated content
- Eliminates need to repeat instructions every time
- Examples: narrative prose preferences, audience level, formatting conventions
- Works with Claude Code; similar approaches available for other AI tools

📁 **[question_bank/](question_bank/)** - Organized repository for exam and practice questions
- Store questions by topic in separate `.tex` files for easy reuse across semesters
- Each question file contains the problem and its solution
- Pull questions into any exam or practice set with a single `\input{}` command
- Perfect for building up a library over time: add questions as you write them, then mix and match for future preps

These style files handle all the LaTeX formatting complexity—you just customize the course info and logo, then focus on content. AI assistants can work directly with these files to generate properly-formatted materials.

📁 **Complete example:** The [F5_Lecture/](F5_Lecture/) folder contains a full corporate finance lecture (from my course JRE 300: Fundamentals of Accounting and Finance, taught for engineering students) with:
- Main slides (~120 min lecture, 1,589 lines)
- Detailed notes (26 pages)
- Summary/review slides
- Practice problems with solutions

**What's coming:** I'll walk through my general workflow, then show you how to try it yourself with a simple example. The F5 lecture serves as a complete reference in the appendix.

---

## My Workflow

### Step 1: Design the Structure

Start with a high-level outline of your lecture or module. You should always retain control of the lecture structure and content.

**Finance example:** A corporate finance lecture might cover Modigliani-Miller theorem, tax effects, bankruptcy costs, and hedging applications in that order.

### Step 2: Create Slides Iteratively
I almost **never free-type LaTeX anymore**—everything is done through commands to the AI. 

**The key principle: Get all content in place FIRST. Don't sweat the small stuff yet.**


**Step 2a: Get the structure right (ignore details!)**

Present your outline in bullet form and have the AI create all slides in one batch:

```
You: "Here's my lecture outline. Create beamer slides for the entire lecture using my @Mott_Beamer.sty. The lecture is for students at the level of [level] and they have already seen the following topics: [topic1,topic2,...]. They are especially comfortable with [skill1] but [skill2] remains shaky, so steer clear unless absolutely necessary, in which case be sure to explain it to death from first principles again. 

      • Introduction to [Topic]
      • Part 1: [Concept A]
        - Definition and intuition
        - Mathematical framework
        - Numerical example
      • Part 2: [Concept B]
        - Build on Concept A
        - Key theorem
        - Applications
      • Part 3: [Extensions]
        - Real-world complications
        - Policy implications
      • Conclusion

AI: [Generates complete slide deck with all sections]
```

Review the output. **Don't worry about incorrect notation, poor examples, weird flow, or bad formatting yet.** Just check: does the **structure** match your intention? Are the right concepts in the right order? Is anything missing or out of place?

If the structure is wrong, fix it now:
```
You: "Move [section] before [section]—students need that foundation first."

You: "Add a mini-section on [topic] between Parts 2 and 3."
```

**Only once the structure matches your intention, proceed to Step 2b.**

**Step 2b: Polish section-by-section (this is where you shine)**

Now go through linearly, one section at a time. This is where your **expertise shines**—you're spared the grunt work of slide-making and can focus on:

```
You: "In the [section], the notation is inconsistent."

AI: [Fixes notation]

You: "That example is too abstract. Replace it with a real company: show Apple's capital structure with actual numbers from 2023. Source: [link to Apple's financials]"

AI: [Generates better example with real data] (AI can look things up online, or read specified websites or documents!)

You: "This slide is too dense. Split it: put the intuition on one slide, the math on the next."

AI: [Reformats slides]
```

Work through each section completely before moving to the next. **This is where you add value**: choosing better examples, ensuring pedagogical flow, fixing technical details, adjusting level for your students.

**Finance example:** Give outline with MM theorem, taxes, bankruptcy costs, hedging. AI generates all slides. First pass: structure looks good but bankruptcy should come after taxes. Fix that. Then go section-by-section: MM theorem section needs better notation and a concrete example. Taxes section needs simpler math. Hedging section needs a Canadian company example instead of the generic one.

**Key lesson:** You need to **reign in the tools**. AI will often over-elaborate, add unnecessary complexity, or generate verbose explanations. I regularly say: "Simpler," "More concise," or "Just the key equation and one example." **I never write LaTeX directly—I describe what I want and the AI implements it.** You focus on *what* should be there; AI handles *how* to code it.

### Step 3: Generate Matching Notes

Once slides are solid:

```
You: "Based on these slides, write detailed notes. Fill in the 'connective tissue'—things I'd say out loud while lecturing. Add more intuition around [key concept]."

AI: [Generates comprehensive notes matching slides but with deeper explanation]
```

**Pro tip: Global style control with `CLAUDE.md`**

This is where the real power comes in. Instead of repeating style instructions every time, create a [`CLAUDE.md`](CLAUDE.md) file (or similar configuration file for your AI tool) that contains **global writing style guidelines**. This file lets you control:

- **Voice and tone** ("conversational but rigorous," "avoid corporate jargon")
- **Exposition style** ("narrative prose, not bullets," "lots of connective tissue")
- **Audience level** ("undergraduate business students," "advanced PhD students")
- **Specific preferences** ("don't use 'key insight'—just state it directly," "use single quotes")
- **Formatting conventions** (section structure, how to highlight terms, etc.)

See my [CLAUDE.md](CLAUDE.md) for an example showing how I enforce narrative prose style, transitional language, and pedagogical approach across all generated notes. The AI will automatically follow these guidelines without you needing to remind it each time.

**For other AI tools:** Similar approaches work with custom instructions (ChatGPT), system prompts, or project-level configuration files.

### Step 4: Create Summary and Practice Materials

```
You: "Create ~20 summary slides at the highest level, suitable for exam review."

You: "Create practice problems testing understanding of [key concepts]. Include detailed solutions."

You: "Students in class asked about tangentially related [topic]. Can you help me sketch a practice problem to cover that intuition? I don't have time in class."
```

**Important caveat:** Practice problem generation is currently the weakest part of this workflow and where I spend the most time editing. AI-generated problems often need significant revision—they may be too easy, too hard, poorly worded, or test the wrong concepts. Expect to rewrite many problems substantially rather than just tweaking them.

### Step 5: Review and Edit

**This is where I spend my time:**
- **Check numerical correctness** (ALWAYS verify calculations—AI can make arithmetic mistakes!)
- Verify formulas and mathematical derivations
- Ensure narrative consistency
- Adjust voice and style
- Edit for visual design and brevity

**Critical reminder:** AI excels at grammar, spelling, and style, but still occasionally makes arithmetic errors. Double-check every calculation, numerical example, and formula.

---

## Why This Works for Custom Audiences

Traditional textbooks are written for a generic audience with fixed examples and one level:

**With AI assistance, I can:**

**Adjust mathematical level:**
```
Engineering students: "Use calculus notation, derive from first principles"
MBA students: "Focus on intuition, use numerical examples, avoid derivations"
```

**Customize examples:**
```
"Replace the airline hedging example with a renewable energy company hedging electricity prices. Use Canadian policy context."
```

**Match prerequisites:**
```
"These students haven't seen portfolio theory yet. Explain the intuition of why we want to measure what will ultimately become beta without referencing the CAPM derivation."
```

**Iterate quickly:**
- Test material with a class
- Get feedback ("too advanced" or "too basic")
- Regenerate sections at a different level
- Deploy updated materials within minutes

---

## Let's Try It Together

Think of a lecture you enjoy giving—something you know well and could explain off the top of your head. Now let's walk through the workflow together, step by step.

See [example_prompts.md](example_prompts.md) for concrete example prompts you can adapt to your preferred lecture.

**Step 1:** Start with your outline. What are the main sections? What order makes pedagogical sense? Write this down in bullet form.

**Step 2:** Open your preferred AI assistant (ChatGPT, Claude, Copilot, Gemini, etc.) and feed it your outline. Ask it to generate slides for the entire lecture. Review the structure—don't worry about details yet. Is anything missing? Out of order? Fix the structure first.

**Step 3:** Once the structure is right, go section by section. Polish notation, improve examples, adjust the level for your students. This is where your expertise matters most.

**Step 4:** Generate matching notes from the slides. Ask the AI to fill in the 'connective tissue'—the things you'd say out loud while lecturing.

**Step 5:** Create practice problems testing the main concepts. Remember: this is the weakest part of the workflow. Expect to revise these substantially.

**Step 6:** Review everything. Check the numbers. Verify the formulas. Edit for voice and style.

**The lesson:** You're steering. The AI is drafting. Iteration is fast and cheap.

---

## Getting Started

### Choose Your Tools

**AI Assistant Options:**
- ChatGPT (web or API)
- Claude (web, Claude Code in VS Code, or API)
- GitHub Copilot
- Google Gemini
- Microsoft Copilot

**Content Creation Tools:**
- **LaTeX** (academic standard, great version control) - *This repo's approach*
- **Microsoft PowerPoint/Word** (familiar, AI integration improving)
- **Google Slides/Docs** (collaborative, cloud-based)
- **Markdown** (simple, portable, great for notes)

### This Repository's Setup (LaTeX-based)

This repo demonstrates a LaTeX workflow because it works well with text-based AI tools and version control.

**Prerequisites for this approach:**
1. An AI assistant (I use Claude Code in VS Code)
2. LaTeX distribution (MacTeX, TeX Live, or MiKTeX)
3. Basic familiarity with LaTeX (though AI handles most syntax)

**Project structure:**
```
your-course/
├── Mott_Beamer.sty          # Beamer style file (customize colors, fonts)
├── Mott_Handout.sty         # Notes/handout style file
├── question_bank/
│   ├── Topic1/
│   │   ├── question1.tex
│   │   └── question2.tex
│   └── Topic2/
│       └── question1.tex
└── Lecture_N/
    ├── LectureN_Slides.tex
    ├── LectureN_Notes.tex
    ├── LectureN_Practical.tex
    └── [compiled PDFs]
```

**Style files included:**
- [Mott_Beamer.sty](Mott_Beamer.sty): Beamer presentation style (colors, themes, footers)
- [Mott_Handout.sty](Mott_Handout.sty): Handout/notes style with solution toggle

Both include attribution and are ready for you to customize with your own branding. AI assistants can use your existing style files, suggest modifications, or create new ones.

---

## Quality and Academic Integrity

**Won't the AI make mistakes?**

Yes! That's why you're the editor. AI tools are excellent at grammar, spelling, and style—almost flawless. However:

**Where AI excels:**
- Grammar, spelling, punctuation (nearly perfect)
- Formatting and structure
- Generating clear explanations
- Adapting tone and style

**Where you must check carefully:**
- **Arithmetic and calculations** (AI still makes occasional math errors—ALWAYS verify!)
- Numerical examples (recalculate them yourself)
- Formulas and derivations
- Logical flow and conceptual accuracy
- Citation accuracy

Content mistakes vary with topic originality—well-established concepts are more reliable than cutting-edge material.

Think of it like having a very capable research assistant who writes beautifully but occasionally miscalculates. The arithmetic problem is improving rapidly (much better than a year ago), but for now: **trust the prose, verify the numbers**.

**What about academic integrity?**

This is **tool use**, like using a calculator or spell-checker. You're:
- Designing the learning path
- Ensuring accuracy
- Maintaining pedagogical quality
- Creating original examples and problems

The AI helps with formatting and drafting, not with thinking. The copyright is yours—the AI is a tool.

---

## Complete Example: F5 Lecture

For a complete worked example, see the [F5_Lecture/](F5_Lecture/) folder in this repository.

| File | Purpose | Size |
|------|---------|------|
| `F5_Slides.tex` | Main lecture slides (4 parts, ~90 min) | ~1,589 lines |
| `F5_Notes.tex` | Detailed notes with full explanations | ~26 pages |
| `F5_Practical_Slides.tex` | Summary slides for review | ~20 slides |
| `F5_Practical.tex` | Practice problems from question bank | 5 problems |

**Content covered:**
- Modigliani-Miller theorem
- Tax shields and bankruptcy costs
- Central bank monetary policy transmission
- Options and hedging (very basic introduction)

---

## License

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/).

You are free to:
- Share and adapt these materials for non-commercial purposes
- Use this workflow for your own teaching

You must:
- Give appropriate credit
- Indicate if changes were made

---

## Resources

- **Claude Code:** [claude.ai/code](https://claude.ai/code)
- **VS Code:** [code.visualstudio.com](https://code.visualstudio.com)
- **LaTeX Reference:** [overleaf.com/learn](https://www.overleaf.com/learn)
- **Beamer Guide:** [CTAN Beamer Documentation](https://ctan.org/pkg/beamer)

---

*Created with AI assistance using Claude Code*
