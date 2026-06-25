# Task 01: Writing Better Prompts

![Task 01: Prompt Comparison](screenshots/task01-prompt-comparison.png)

## 🎯 Objective
To master the foundational principles of prompt engineering by transforming vague, open-ended queries into highly specific, context-rich instructions that yield precise, actionable, and high-quality AI outputs.

## ⚠️ Problem Statement
Large Language Models (LLMs) operate on statistical probability. When provided with weak, ambiguous, or unconstrained prompts, they often generate generic, hallucinated, or irrelevant responses. The challenge is to systematically engineer prompts that constrain the model's output space to strictly align with user intent.

## 📖 Introduction
Writing better prompts is the cornerstone of interacting effectively with AI. It is not merely about asking questions, but about programming the model using natural language. By applying specific techniques—such as setting personas, defining constraints, and structuring output formats—we can significantly enhance the reliability and utility of generative AI systems.

## 🧠 Prompt Engineering Principles
1. **Clarity & Specificity:** Eliminate ambiguity. Clearly state *what* you want and *how* you want it.
2. **Contextual Framing:** Provide background information or assign a persona to guide the model's tone and perspective.
3. **Explicit Constraints:** Define limits (e.g., word count, excluded topics) to prevent rambling or irrelevant tangents.
4. **Structured Outputs:** Dictate the exact format of the response (e.g., markdown table, JSON, bullet points).
5. **Iterative Refinement:** Analyze the model's initial output and adjust the prompt to patch any logical or structural leaks.

---

## 🔍 Examples

### Example 1: Climate Change
**1. Original Prompt:**
> "Tell me about climate change."

**2. Weakness Analysis:**
Too broad. It lacks a target audience, a specific format, and constraints. The AI will likely generate a generic, encyclopedia-style summary that is unengaging.

**3. Improved Prompt:**
> "Act as a leading climate scientist. Write a 3-paragraph explanation of how ocean acidification impacts marine ecosystems, specifically coral reefs. Your target audience is high school students. Use simple analogies and format the final paragraph as a bulleted list of 3 actionable steps students can take."

**4. AI Output (Simulated):**
*(Paragraph 1: Introduction to the ocean acting as a sponge for carbon dioxide, using the analogy of a fizzy soda...)*
*(Paragraph 2: Explanation of how coral reefs struggle to build their skeletons in acidic water, like trying to build a house with dissolving bricks...)*
* **Reduce your carbon footprint:** Walk or bike to school instead of driving.
* **Conserve energy:** Turn off lights and electronics when not in use.
* **Spread awareness:** Educate your family and friends about the importance of our oceans.

**5. Comparison Table:**
| Metric | Original Prompt | Improved Prompt |
| :--- | :--- | :--- |
| **Specificity** | Very Low | High |
| **Tone/Persona** | Neutral/Generic | Authoritative yet accessible (Scientist to Student) |
| **Formatting** | Unstructured | Structured (Paragraphs + Bullet Points) |

**6. Why the improved prompt performs better:**
It assigns a clear persona (scientist) and audience (high schoolers), which perfectly tunes the vocabulary and tone. It also establishes rigid formatting constraints, resulting in a predictable and highly useful output.

---

### Example 2: Python Programming
**1. Original Prompt:**
> "Write a python script to scrape a website."

**2. Weakness Analysis:**
Lacks technical specifics. Which website? What data? Which libraries? The AI will guess, usually providing a generic BeautifulSoup script that the user will have to rewrite entirely.

**3. Improved Prompt:**
> "Write a Python script using `requests` and `BeautifulSoup` to scrape all the article titles (contained in `<h2>` tags with the class `article-title`) from 'https://example.com/blog'. Include error handling for network timeouts and print the final titles as a numbered list. Add inline comments explaining each step."

**4. AI Output (Simulated):**
```python
import requests
from bs4 import BeautifulSoup

def scrape_titles(url):
    try:
        # Send a GET request with a 5-second timeout
        response = requests.get(url, timeout=5)
        response.raise_for_status() # Check for HTTP errors
        
        # Parse the HTML content
        soup = BeautifulSoup(response.text, 'html.parser')
        
        # Find all h2 tags with the specific class
        titles = soup.find_all('h2', class_='article-title')
        
        # Print the titles as a numbered list
        for idx, title in enumerate(titles, start=1):
            print(f"{idx}. {title.get_text(strip=True)}")
            
    except requests.exceptions.RequestException as e:
        print(f"Network error occurred: {e}")

scrape_titles('https://example.com/blog')
```

**5. Comparison Table:**
| Metric | Original Prompt | Improved Prompt |
| :--- | :--- | :--- |
| **Library Choice** | AI's Discretion | Explicitly defined (`requests`, `BeautifulSoup`) |
| **Target Data** | Unknown | `<h2>` tags with class `article-title` |
| **Robustness** | Minimal | High (includes error handling) |

**6. Why the improved prompt performs better:**
By explicitly defining the libraries, HTML tags, and requiring error handling, the output is essentially production-ready code rather than a generic boilerplate.

---

### Example 3: Resume Writing
**1. Original Prompt:**
> "Make my resume better."

**2. Weakness Analysis:**
The AI has no context about the user's current resume, industry, or experience level. It can only offer generic platitudes about resume writing.

**3. Improved Prompt:**
> "Act as an expert technical recruiter for FAANG companies. I am a junior software engineer. Rewrite the following resume bullet point to highlight impact and metrics using the XYZ formula (Accomplished [X] as measured by [Y], by doing [Z]). Original bullet: 'Worked on the backend API to make it faster.'"

**4. AI Output (Simulated):**
> "Reduced backend API latency by 40% (Y), resulting in a smoother user experience for 10,000+ daily active users (X), by refactoring legacy database queries and implementing Redis caching (Z)."

**5. Comparison Table:**
| Metric | Original Prompt | Improved Prompt |
| :--- | :--- | :--- |
| **Role/Persona** | None | Expert FAANG Recruiter |
| **Framework** | None | XYZ Formula |
| **Input Data** | None provided | Specific text provided for rewriting |

**6. Why the improved prompt performs better:**
It utilizes a proven framework (the XYZ formula) and provides a highly specific task (rewriting a single bullet point) rather than a vague request. The FAANG recruiter persona ensures a highly professional, competitive tone.

---

### Example 4: Fitness
**1. Original Prompt:**
> "Give me a workout plan."

**2. Weakness Analysis:**
Ignores the user's fitness level, equipment availability, goals, and time constraints. The resulting plan is likely to be dangerous for beginners or too easy for advanced athletes.

**3. Improved Prompt:**
> "Act as a certified personal trainer. Create a 4-day-per-week hypertrophy workout plan for an intermediate lifter. I only have access to dumbbells and an adjustable bench. Workouts must be under 45 minutes. Output the plan as a Markdown table with columns for Day, Exercise, Sets, Reps, and Rest Time."

**4. AI Output (Simulated):**
| Day | Exercise | Sets | Reps | Rest Time |
| :--- | :--- | :--- | :--- | :--- |
| **Day 1: Push** | DB Incline Bench Press | 4 | 8-10 | 90 sec |
| | DB Shoulder Press | 3 | 10-12 | 60 sec |
| | DB Lying Triceps Extension | 3 | 12-15 | 60 sec |
| **Day 2: Pull** | DB One-Arm Row | 4 | 8-10 | 90 sec |
| | DB Pullover | 3 | 10-12 | 60 sec |
| | DB Bicep Curls | 3 | 12-15 | 60 sec |
*(Table truncated for brevity)*

**5. Comparison Table:**
| Metric | Original Prompt | Improved Prompt |
| :--- | :--- | :--- |
| **Equipment constraints** | None | Dumbbells and bench only |
| **Time constraints** | None | Under 45 minutes |
| **Output format** | Paragraphs | Markdown Table |

**6. Why the improved prompt performs better:**
It treats the LLM as a database of fitness knowledge and filters that data through strict, real-world constraints. The forced Markdown table output makes the information immediately usable without needing reformatting.

---

### Example 5: Travel Planning
**1. Original Prompt:**
> "Plan a trip to Tokyo."

**2. Weakness Analysis:**
Fails to specify budget, duration, interests, or travel companions. The AI will output a generic, tourist-trap heavy itinerary that may not suit the user.

**3. Improved Prompt:**
> "I am planning a 3-day solo trip to Tokyo. I have a medium budget. I love cyberpunk aesthetics, retro video games, and street food. I dislike traditional temples and early mornings. Create a daily itinerary. For each day, include 3 specific locations, estimated costs in JPY, and one insider tip. Do not schedule anything before 11:00 AM."

**4. AI Output (Simulated):**
**Day 1: The Neon Heart**
* **11:30 AM - Akihabara Electric Town (Super Potato):** Browse floors of retro gaming consoles. (Cost: ~3,000 JPY for souvenirs).
* **2:00 PM - Tsukiji Outer Market:** Late lunch of premium street food like tamagoyaki and wagyu skewers. (Cost: ~4,000 JPY).
* **6:00 PM - Shinjuku Kabukicho:** Experience the cyberpunk vibe and neon lights. (Cost: Free to walk, ~2,000 JPY for drinks).
* *Insider Tip:* Look up! Many of the best arcade shops and niche stores in Akihabara are on the 3rd or 4th floors of narrow buildings.

**5. Comparison Table:**
| Metric | Original Prompt | Improved Prompt |
| :--- | :--- | :--- |
| **Constraints** | None | No mornings, no temples |
| **Interests** | Assumed | Cyberpunk, retro games, street food |
| **Detail Level** | Vague | Specific locations, costs, insider tips |

**6. Why the improved prompt performs better:**
It applies negative constraints ("dislike temples", "no early mornings") which drastically narrows the LLM's search space. Providing specific interests forces the model to synthesize a custom itinerary rather than reciting a generic top-10 list.

---

## 🪞 Reflection
Throughout this task, it became evident that the quality of AI output is directly proportional to the cognitive effort invested in the prompt. The LLM acts as a mirror to the user's clarity of thought. Unstructured thoughts lead to unstructured outputs, while systematic, framework-driven prompts yield high-fidelity results.

## 💡 Key Learnings
1. **Personas are powerful:** Assigning a role (e.g., "FAANG Recruiter", "Climate Scientist") instantly calibrates the LLM's vocabulary, tone, and assumed knowledge level.
2. **Formatting is a constraint:** Forcing an output into a table, JSON, or specific markdown structure inherently forces the LLM to organize its "thoughts" more logically.
3. **Negative constraints matter:** Telling the model what *not* to do is often just as important as telling it what to do.

## 🏁 Conclusion
Prompt engineering is essentially a new programming paradigm where the compiler is statistical rather than deterministic. By mastering clarity, context, and constraints, we transition from being passive consumers of AI to active engineers, capable of steering these models to solve complex, real-world problems with precision.
