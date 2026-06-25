# Task 04: AI Automation Specialist - Meeting Notes to JSON Converter

*(Note: Sequenced as Task 04 to preserve your previous Creative Prompting Task 03)*

## 🎯 Objective
To design a deterministic, robust prompt that reliably converts unstructured, conversational meeting transcripts into a strictly formatted, machine-readable JSON object. This task highlights how prompt engineering bridges the gap between natural language processing and structured data automation.

## ⚙️ The Automation Prompt

> "You are an automated data extraction pipeline. Your task is to process the following raw meeting transcript and output a strictly formatted JSON object.
> 
> **Instructions:**
> 1. Extract the following fields: `meeting_date` (YYYY-MM-DD), `participants` (array of strings), `main_topics` (array of strings), `action_items` (array of objects containing `assignee`, `task`, and `deadline_date`), and `sentiment` (enum: 'Positive', 'Neutral', 'Negative').
> 2. If a specific deadline date is not mentioned for an action item, use `null`.
> 3. Do not include any conversational filler, introductory text, or markdown code blocks (like ```json). Output ONLY the raw, valid JSON.
> 
> **Raw Transcript:**
> [INSERT_TRANSCRIPT_HERE]"

## 📐 Prompt Design Breakdown
* **Role Assignment ("Automated data extraction pipeline"):** Removes conversational AI tendencies and forces the model to act as a programmatic function.
* **Strict Schema Definition:** Explicitly defining the fields, data types (arrays, objects), and enums ensures the output can be parsed programmatically without throwing syntax errors.
* **Edge Case Handling ("use null"):** Prevents the LLM from hallucinating deadlines when none exist.
* **Negative Constraints ("Output ONLY the raw, valid JSON"):** Crucial for automation. If the AI outputs "Here is your JSON: { ... }", it breaks the automated parsing script.

---

## 📝 Test Cases & JSON Outputs

### Scenario 1: The Product Sync
**Meeting Notes (Input):**
> "Okay, let's get started. Today is October 12, 2026. It's just Sarah and John on the call today. Sarah noted that the new UI deployment was highly successful and user feedback has been great. John brought up a minor bug in the login portal. Sarah will patch the login bug by next Friday. John needs to draft the release notes, but there's no rush on that yet."

**JSON Output:**
{
  "meeting_date": "2026-10-12",
  "participants": ["Sarah", "John"],
  "main_topics": ["New UI deployment", "Login portal bug"],
  "action_items": [
    {
      "assignee": "Sarah",
      "task": "Patch the login bug",
      "deadline_date": "2026-10-16"
    },
    {
      "assignee": "John",
      "task": "Draft release notes",
      "deadline_date": null
    }
  ],
  "sentiment": "Positive"
}

---

### Scenario 2: The Urgent Escalation
**Meeting Notes (Input):**
> "Date: 03/15/2026. Attendees: Mike, Emily, David. Look, guys, we have a major problem. The server crashed three times last night and clients are furious. David, you need to pull the server logs immediately, I need them by EOD today. Emily, contact the premium clients and apologize by tomorrow morning. This is a mess and we need to fix it now."

**JSON Output:**
{
  "meeting_date": "2026-03-15",
  "participants": ["Mike", "Emily", "David"],
  "main_topics": ["Server crashes", "Client complaints"],
  "action_items": [
    {
      "assignee": "David",
      "task": "Pull server logs",
      "deadline_date": "2026-03-15"
    },
    {
      "assignee": "Emily",
      "task": "Contact premium clients to apologize",
      "deadline_date": "2026-03-16"
    }
  ],
  "sentiment": "Negative"
}

---

### Scenario 3: The Brainstorming Session
**Meeting Notes (Input):**
> "Meeting on August 5th, 2026. Amanda, Chloe, and Raj present. We just chatted about some ideas for the upcoming Q4 marketing campaign. Raj suggested doing a TikTok influencer push. Chloe thought a webinar series would be better. We didn't really decide on anything yet, just throwing ideas around. Amanda will schedule a follow-up meeting for next week to finalize the budget."

**JSON Output:**
{
  "meeting_date": "2026-08-05",
  "participants": ["Amanda", "Chloe", "Raj"],
  "main_topics": ["Q4 marketing campaign", "TikTok influencer push", "Webinar series"],
  "action_items": [
    {
      "assignee": "Amanda",
      "task": "Schedule follow-up meeting to finalize budget",
      "deadline_date": "2026-08-12"
    }
  ],
  "sentiment": "Neutral"
}

---

## 🔄 The Prompt Refinement Process
1. **Iteration 1 (The Hallucination Phase):** Initially, the AI would format the date differently every time (e.g., "October 12th", "10/12/26"). I updated the prompt to strictly mandate the ISO format `(YYYY-MM-DD)`.
2. **Iteration 2 (The Chatty AI Phase):** The AI kept outputting "Sure! Here is the JSON you requested:" before the actual `{` bracket. This would immediately break a Python `json.loads()` function. I added the strict negative constraint to remove all conversational filler.
3. **Iteration 3 (The Missing Data Phase):** When an action item lacked a deadline, the AI would make one up (e.g., assigning "Next Week"). I refined the prompt to introduce programmatic logic: *If no deadline is mentioned, output `null`*. This ensures data integrity.

## 🪞 Reflection
When engineering prompts for automation pipelines, creativity is actually a liability. You do not want the LLM to be creative; you want it to be deterministic, rigid, and predictable. This task required a shift in mindset from "prompting an assistant" to "programming a compiler." The primary challenge is accounting for edge cases in the unstructured input (like missing dates or implicit assignments) and ensuring the LLM handles them gracefully without breaking the JSON schema.

## 🏁 Conclusion
By utilizing strict schemas, type casting (arrays, enums), and explicit negative constraints, we can successfully wrangle the probabilistic nature of Large Language Models into reliable data-extraction engines. This enables seamless integration of AI into traditional software architectures, turning messy human conversations into structured, actionable databases.
