# Task 01 - Part 2: AI Response Analysis

This document demonstrates the practical impact of prompt engineering by comparing simulated AI responses to both the original (weak) prompts and the improved (engineered) prompts developed in Task 01.

---

## 🌍 Example 1: Climate Change

### Response to Original Prompt
**Original Prompt:** *"Tell me about climate change."*
> Climate change refers to long-term shifts in temperatures and weather patterns. These shifts may be natural, such as through variations in the solar cycle. But since the 1800s, human activities have been the main driver of climate change, primarily due to burning fossil fuels like coal, oil, and gas. Burning fossil fuels generates greenhouse gas emissions that act like a blanket wrapped around the Earth, trapping the sun's heat and raising temperatures. The consequences include intense droughts, water scarcity, severe fires, rising sea levels, flooding, melting polar ice, catastrophic storms, and declining biodiversity.

### Response to Improved Prompt
**Improved Prompt:** *"Act as a leading climate scientist. Write a 3-paragraph explanation of how ocean acidification impacts marine ecosystems, specifically coral reefs. Your target audience is high school students. Use simple analogies and format the final paragraph as a bulleted list of 3 actionable steps students can take."*
> Hello students! When we think about climate change, we usually think of the air getting hotter, but our oceans are taking a massive hit too. You can think of the ocean as a giant sponge that absorbs carbon dioxide (CO2) from the atmosphere. When CO2 mixes with seawater, it creates carbonic acid. Imagine leaving a chalky seashell in a glass of soda overnight; the acid in the soda slowly dissolves the shell. This is called ocean acidification, and it's happening right now in our real oceans.
>
> This is incredibly dangerous for coral reefs. Corals build their hard, colorful skeletons using minerals they pull from the seawater, much like a bricklayer building a house. However, as the ocean becomes more acidic, those "bricks" become harder to find and start to dissolve. If coral reefs collapse, the thousands of fish and marine animals that call them home lose their habitats, which disrupts the entire marine food web. 
> 
> As the next generation of leaders, here is what you can do to help protect our oceans:
> * **Reduce your carbon footprint:** Walk, bike, or take the bus to school instead of driving. 
> * **Conserve energy:** Turn off the lights, unplug your chargers when not in use, and advocate for renewable energy at your school.
> * **Spread awareness:** Share what you've learned about ocean acidification with your family and friends to inspire community-wide action.

### Side-by-Side Comparison & Analysis

| Feature | Original Response | Improved Response |
| :--- | :--- | :--- |
| **Tone** | Encyclopedia/Wikipedia style. | Educational, engaging, authoritative. |
| **Focus** | General overview of everything. | Highly targeted on ocean acidification and coral reefs. |
| **Formatting** | One block of text. | Structured paragraphs and bullet points. |

**Analysis of Differences:** 
The original output is factually correct but boring and untailored. By applying constraints and a persona, the improved output utilizes analogies (the sponge, the soda, the bricklayer) that are perfectly suited for high school students, making the complex science easy to digest and actionable.

---

## 🐍 Example 2: Python Programming

### Response to Original Prompt
**Original Prompt:** *"Write a python script to scrape a website."*
> ```python
> import requests
> from bs4 import BeautifulSoup
> 
> url = 'http://example.com'
> response = requests.get(url)
> soup = BeautifulSoup(response.text, 'html.parser')
> 
> # Print all paragraph texts
> for p in soup.find_all('p'):
>     print(p.text)
> ```
> *Note: Make sure to install requests and beautifulsoup4 before running this script.*

### Response to Improved Prompt
**Improved Prompt:** *"Write a Python script using `requests` and `BeautifulSoup` to scrape all the article titles (contained in `<h2>` tags with the class `article-title`) from 'https://example.com/blog'. Include error handling for network timeouts and print the final titles as a numbered list. Add inline comments explaining each step."*
> ```python
> import requests
> from bs4 import BeautifulSoup
> import sys
> 
> def scrape_article_titles(url):
>     """Scrapes and prints article titles from a given URL."""
>     try:
>         # 1. Send a GET request to the target URL with a 5-second timeout
>         response = requests.get(url, timeout=5)
>         
>         # 2. Raise an exception if the HTTP request returned an error status code
>         response.raise_for_status()
>         
>     except requests.exceptions.Timeout:
>         print("Error: The network request timed out.")
>         sys.exit(1)
>     except requests.exceptions.RequestException as e:
>         print(f"Error: A network problem occurred - {e}")
>         sys.exit(1)
>         
>     # 3. Parse the retrieved HTML document using BeautifulSoup
>     soup = BeautifulSoup(response.text, 'html.parser')
>     
>     # 4. Find all <h2> elements that possess the class 'article-title'
>     title_elements = soup.find_all('h2', class_='article-title')
>     
>     # 5. Check if any titles were found; if so, iterate and print them as a numbered list
>     if not title_elements:
>         print("No articles found with the specified tags.")
>     else:
>         for index, element in enumerate(title_elements, start=1):
>             # strip() removes any accidental whitespace around the text
>             print(f"{index}. {element.get_text(strip=True)}")
> 
> # Execute the function with the target URL
> scrape_article_titles('https://example.com/blog')
> ```

### Side-by-Side Comparison & Analysis

| Feature | Original Response | Improved Response |
| :--- | :--- | :--- |
| **Target Data** | Randomly scrapes `<p>` tags. | Precisely targets `<h2 class="article-title">`. |
| **Robustness** | Crushes if the network fails. | Contains try-except blocks for timeout and network errors. |
| **Usability** | Barebones script, requires user modification. | Modular function, highly commented, production-ready. |

**Analysis of Differences:** 
The weak prompt yielded a generic "Hello World" of web scraping. The engineered prompt forced the LLM to think like a software engineer, integrating robust error handling, precise DOM targeting, and readable formatting. The improved script is safe to execute and easy to maintain.

---

## 📄 Example 3: Resume Writing

### Response to Original Prompt
**Original Prompt:** *"Make my resume better: 'Worked on the backend API to make it faster.'"*
> You should try to be more specific. Here is a better version: 
> "Improved the backend API to significantly increase speed and efficiency for the application."

### Response to Improved Prompt
**Improved Prompt:** *"Act as an expert technical recruiter for FAANG companies. I am a junior software engineer. Rewrite the following resume bullet point to highlight impact and metrics using the XYZ formula (Accomplished [X] as measured by [Y], by doing [Z]). Original bullet: 'Worked on the backend API to make it faster.'"*
> As a FAANG recruiter, I need to see exactly *what* you achieved and *how* you did it. Let's transform that generic bullet point using the XYZ framework to showcase your engineering impact:
> 
> **Optimized Version:**
> * "Reduced backend API latency by 40% (Y), resulting in a smoother user experience for 10,000+ daily active users (X), by refactoring legacy database queries and implementing Redis caching (Z)."
> 
> *Tip: Be sure to replace the placeholder numbers (40%, 10,000+) and technologies (Redis) with the exact metrics and stack you used in your actual project!*

### Side-by-Side Comparison & Analysis

| Feature | Original Response | Improved Response |
| :--- | :--- | :--- |
| **Value Add** | Swapped synonyms (faster -> speed/efficiency). | Applied a professional HR framework (XYZ formula). |
| **Impact** | Still vague and unquantified. | Forces the user to think in metrics and architectural decisions. |
| **Tone** | Helpful but basic assistant. | Expert mentor guiding a junior engineer. |

**Analysis of Differences:** 
The original output merely paraphrased the input without adding real resume value. By commanding the LLM to adopt a "FAANG Recruiter" persona and explicitly defining a mental model (the XYZ formula), the AI completely restructured the sentence to meet elite industry standards.

---

## 🏋️ Example 4: Fitness

### Response to Original Prompt
**Original Prompt:** *"Give me a workout plan."*
> Here is a standard 3-day full-body workout plan:
> 
> **Monday:**
> - Squats: 3 sets of 10
> - Bench Press: 3 sets of 10
> - Pull-ups: 3 sets to failure
> 
> **Wednesday:**
> - Deadlifts: 3 sets of 8
> - Overhead Press: 3 sets of 10
> - Barbell Rows: 3 sets of 10
> 
> **Friday:**
> - Lunges: 3 sets of 12
> - Incline Press: 3 sets of 10
> - Bicep Curls: 3 sets of 15

### Response to Improved Prompt
**Improved Prompt:** *"Act as a certified personal trainer. Create a 4-day-per-week hypertrophy workout plan for an intermediate lifter. I only have access to dumbbells and an adjustable bench. Workouts must be under 45 minutes. Output the plan as a Markdown table with columns for Day, Exercise, Sets, Reps, and Rest Time."*
> As your virtual PT, I've designed this 4-day Upper/Lower split optimized for hypertrophy (muscle growth) given your equipment limits. Because we are working under a strict 45-minute time cap, rest periods are kept strictly to 60-90 seconds. 
> 
> | Day | Exercise | Sets | Reps | Rest Time |
> | :--- | :--- | :--- | :--- | :--- |
> | **Day 1: Upper A** | DB Flat Bench Press | 4 | 8-10 | 90 sec |
> | | DB One-Arm Row | 4 | 8-10 | 90 sec |
> | | DB Seated Shoulder Press | 3 | 10-12 | 60 sec |
> | | DB Bicep Curls | 3 | 12-15 | 60 sec |
> | **Day 2: Lower A** | DB Goblet Squats | 4 | 10-12 | 90 sec |
> | | DB Romanian Deadlifts (RDLs) | 4 | 10-12 | 90 sec |
> | | DB Walking Lunges | 3 | 12/leg | 60 sec |
> | | DB Calf Raises | 3 | 15-20 | 60 sec |
> | **Day 3: Upper B** | DB Incline Bench Press | 4 | 8-10 | 90 sec |
> | | DB Pullover | 3 | 10-12 | 90 sec |
> | | DB Lateral Raises | 3 | 12-15 | 60 sec |
> | | DB Lying Triceps Extension | 3 | 12-15 | 60 sec |
> | **Day 4: Lower B** | DB Split Squats | 3 | 10/leg| 90 sec |
> | | DB Glute Bridges | 4 | 12-15 | 90 sec |
> | | DB Step-Ups (using bench) | 3 | 10/leg| 60 sec |
> | | DB Seated Calf Raises | 3 | 15-20 | 60 sec |

### Side-by-Side Comparison & Analysis

| Feature | Original Response | Improved Response |
| :--- | :--- | :--- |
| **Equipment** | Assumes a full commercial gym. | Perfectly conforms to DB + Bench constraint. |
| **Goal Alignment** | Generic "full body". | Targeted Upper/Lower split for Hypertrophy. |
| **Presentation** | Bulleted list. | Clean, easily readable Markdown table. |

**Analysis of Differences:** 
The original output is useless to someone working out at home without a barbell. The engineered prompt acts like an API call to a fitness database, applying strict logical filters (equipment == dumbbells, time <= 45m) and a UI formatting request (table). The result is highly customized and immediately usable.

---

## ✈️ Example 5: Travel Planning

### Response to Original Prompt
**Original Prompt:** *"Plan a trip to Tokyo."*
> Tokyo is an amazing city! Here is a simple itinerary for your trip:
> - **Day 1:** Visit the Senso-ji Temple in Asakusa in the morning. In the afternoon, head to the Tokyo Skytree for a view of the city.
> - **Day 2:** Go to Shibuya to see the famous Scramble Crossing. Then walk to Harajuku to see the fashion and visit the Meiji Shrine.
> - **Day 3:** Take a day trip to Mt. Fuji, or visit the Tsukiji Fish Market early in the morning for fresh sushi.

### Response to Improved Prompt
**Improved Prompt:** *"I am planning a 3-day solo trip to Tokyo. I have a medium budget. I love cyberpunk aesthetics, retro video games, and street food. I dislike traditional temples and early mornings. Create a daily itinerary. For each day, include 3 specific locations, estimated costs in JPY, and one insider tip. Do not schedule anything before 11:00 AM."*
> **Day 1: The Neon Heart**
> * **11:30 AM - Akihabara Electric Town (Super Potato):** Browse three floors of meticulously preserved retro gaming consoles and cartridges. (Cost: ~3,000 JPY for souvenirs).
> * **2:30 PM - Nakano Broadway:** A maze-like shopping center filled with vintage anime, manga, and obscure pop culture collectibles. Grab street-style takoyaki in the basement. (Cost: ~2,500 JPY).
> * **7:00 PM - Shinjuku Kabukicho:** Experience the ultimate cyberpunk vibe. Wander the neon-lit alleys and grab dinner in Omoide Yokocho (Memory Lane) for yakitori skewers. (Cost: ~4,000 JPY).
> * *Insider Tip:* Look up! Many of the best arcade shops and niche stores in Akihabara and Nakano are tucked away on the upper floors of narrow, unassuming buildings.
> 
> **Day 2: Fashion, Tech, and Underground Vibes**
> * **11:00 AM - Harajuku (Takeshita Street & Ura-Hara):** Skip the temples and dive into the chaotic, vibrant street fashion. Grab a famous crepe. (Cost: ~1,500 JPY).
> * **3:00 PM - Shibuya Parco (Cyberspace Shibuya):** Visit the 6th floor dedicated entirely to gaming culture (Nintendo Tokyo, Capcom, Pokemon Center). (Cost: Window shopping is free, but expect to spend ~5,000 JPY if you buy).
> * **8:00 PM - Shibuya Nonbei Yokocho (Drunkard's Alley):** Grab a beer and some izakaya street food in this retro, Blade Runner-esque alleyway right next to the train tracks. (Cost: ~3,500 JPY).
> * *Insider Tip:* Don't buy a standard Suica card; add a digital Suica or Pasmo card to your Apple/Google Wallet before you fly to easily tap your phone for train rides and vending machines.
> 
> **Day 3: Man-Made Islands and Future Tech**
> * **12:00 PM - Odaiba (DiverCity Tokyo Plaza):** Marvel at the life-sized, transforming Unicorn Gundam statue. (Cost: Free to view).
> * **3:00 PM - Joypolis (Sega Indoor Theme Park):** An indoor amusement park packed with VR attractions and arcade games that feels straight out of a sci-fi novel. (Cost: ~4,500 JPY for a passport ticket).
> * **7:30 PM - Tsukishima Monja Street:** Try Monjayaki, a savory pan-fried batter dish popular in Tokyo, cooked right in front of you on a hot plate. (Cost: ~2,500 JPY).
> * *Insider Tip:* Ride the automated Yurikamome transit line to Odaiba and try to sit in the very front seat for a spectacular, driverless view of the futuristic skyline crossing the Rainbow Bridge.

### Side-by-Side Comparison & Analysis

| Feature | Original Response | Improved Response |
| :--- | :--- | :--- |
| **Time Constraints** | Ignored (recommends morning temples). | Strictly adhered to (nothing before 11:00 AM). |
| **Personalization** | Cookie-cutter tourist traps. | Hyper-specific to cyberpunk, retro gaming, and street food. |
| **Detail Level** | Bare minimum. | Includes estimated costs in local currency and highly relevant insider tips. |

**Analysis of Differences:** 
The weak prompt generated a lazy TripAdvisor-style summary containing the exact things the user dislikes (early mornings, temples). The improved prompt used negative constraints ("dislike temples") and positive parameters ("cyberpunk", "medium budget") to sculpt a bespoke, highly accurate itinerary that the user can actually follow without needing further research.
