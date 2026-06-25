# 📸 Visual Portfolio: Screenshot Capture Guide

Adding real screenshots of your prompt engineering workflows into your GitHub repository significantly boosts the professionalism of your portfolio. Recruiters want to see that you actually executed these prompts in live environments like ChatGPT, Claude, or an API playground.

This guide outlines exactly which moments you should capture, how to name the files, and where to store them for every task in this repository.

---

## 📁 Recommended GitHub Folder Structure
To keep the repository clean, each project folder should contain its own `screenshots/` directory.

```text
SkillCraft-Prompt-Engineering/
├── projects/
│   ├── Task-01-Writing-Better-Prompts/
│   │   ├── README.md
│   │   └── screenshots/          <-- Store Task 1 images here
│   ├── Task-02-AI-Startup-Idea-Generator/
│   │   ├── README.md
│   │   └── screenshots/          <-- Store Task 2 images here
│   └── ... (etc for all tasks)
```

*(Tip: Once you take the screenshots, you can link them directly in the corresponding `README.md` files using the syntax: `![Description](screenshots/filename.png)`).*

---

## 📝 Task-by-Task Screenshot Guide

### Task 01: Writing Better Prompts
**Goal:** Prove that you understand how specificity and constraints change outputs.
* **What to capture:** 
  1. The AI's generic, boring response to the original prompt (e.g., "Tell me about climate change").
  2. The AI's structured, persona-driven response to your engineered prompt.
* **File Names:** 
  * `task1-climate-original.png`
  * `task1-climate-improved.png`
  * `task1-python-improved.png` (Capture the code block generation)

### Task 02: AI Startup Idea Generator
**Goal:** Visually demonstrate the "Regression to the Mean" trap versus elite prompt crafting.
* **What to capture:**
  1. **Version 1 (Basic):** The generic virtual assistant idea.
  2. **Version 3 (Professional):** The "Veteran VC" prompt alongside the highly detailed Pitch Memo (highlighting the ICP, Monetization, and Tech Architecture).
* **File Names:**
  * `task2-startup-v1-basic.png`
  * `task2-startup-v3-pitch-memo.png`

### Task 03: Creative Prompting Projects
**Goal:** Highlight your ability to control tone, style, and negative constraints.
* **What to capture (Story Generator):**
  1. The prompt block showcasing the negative constraints ("Do not use the word fear").
  2. The AI's output showing the "Phantom Voltage" story to prove it followed the rules.
* **What to capture (Advertisement Generator):**
  1. The "NeuroRoast" prompt structure (Hook, Agitate, Solve, CTA).
  2. The punchy, emoji-filled Instagram ad output.
* **File Names:**
  * `task3-scifi-story-constraints.png`
  * `task3-neuroroast-ad-copy.png`

### Task 04: Meeting Notes to JSON Converter
**Goal:** Show your technical capability to turn AI into an automation compiler.
* **What to capture:**
  1. The strict system prompt (defining arrays, enums, and dates).
  2. A side-by-side (or sequential) view of the messy "Urgent Escalation" meeting notes, followed instantly by the clean, formatted JSON output block. Make sure the syntax highlighting of the JSON block is visible!
* **File Names:**
  * `task4-json-system-prompt.png`
  * `task4-json-output-success.png`

### Task 05: Prompt Automation Projects
**Goal:** Demonstrate high-volume business utility and data synthesis.
* **What to capture (Email Generator):**
  1. The shorthand notes provided by the user.
  2. The AI generating the perfectly formatted [Subject Line] and bullet points.
* **What to capture (Research Summarizer):**
  1. The dense, jargon-filled "SparseGPT" abstract.
  2. The AI's TL;DR, 3 bullets, and Business Application output.
* **File Names:**
  * `task5-email-generation.png`
  * `task5-research-summary-sparsegpt.png`

### Task 06: Interview Preparation Assistant
**Goal:** Show mastery over multi-turn, state-based LLM interactions.
* **What to capture:**
  1. **The Behavioral Probe:** Capture Turn 4 and Turn 5 of the mock interview. Show the AI asking a behavioral question, the user giving a shallow answer, and the AI actively pushing back and demanding metrics (The STAR method in action).
  2. **The Evaluation:** Capture the final Evaluation Report showing the Communication and Technical scores.
* **File Names:**
  * `task6-assistant-probing-interaction.png`
  * `task6-assistant-final-evaluation.png`

---

## 💡 Best Practices for Screenshots
1. **Use Dark Mode:** Dark mode generally looks sleeker and more professional in developer portfolios.
2. **Crop Intelligently:** Crop out your browser tabs, bookmarks bar, and system clock. Focus purely on the Chat UI (Prompt and Response).
3. **Use Snipping Tools:** Use `Win + Shift + S` (Windows) or `Cmd + Shift + 4` (Mac) for precise capturing. 
4. **Highlighting:** If possible, use a subtle red or yellow box to highlight the specific constraint in your prompt, and draw a line to where the AI successfully executed it in the output.
