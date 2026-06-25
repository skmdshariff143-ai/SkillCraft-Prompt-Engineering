# Task 05: Prompt Automation Projects

## 🎯 Objective
To develop highly functional, automation-ready prompts for repetitive professional tasks: Automated Email Generation and Academic Research Summarization. This task explores how providing explicit formatting instructions and tone constraints enables an AI to act as a reliable, high-volume processing engine.

---

## 📧 Project 1: Automated Email Generator

**Goal:** Create a prompt that takes messy, shorthand notes and converts them into polished, professional emails ready to be sent to clients or internal stakeholders.

### ⚙️ The Automation Prompt
> "You are an executive communications assistant. Your task is to take the following shorthand notes and draft a professional, polite, and concise email. 
> 
> **Constraints:**
> 1. Tone must be professional and empathetic.
> 2. Include a clear subject line wrapped in [brackets].
> 3. Ensure all action items or deadlines from the notes are explicitly stated in bullet points.
> 4. Keep the email under 150 words.
> 5. Output ONLY the email text (Subject, Body, Sign-off). Do not include any conversational filler.
> 
> **Shorthand Notes:**
> [INSERT_NOTES_HERE]"

### 📝 Test Cases

#### Scenario 1: The Apology & Delay
**Sample Input:** 
> "client upset. shipment of servers delayed by 2 weeks due to supply chain. offer 10% discount on next order to say sorry. need them to confirm if they still want it or cancel by friday."

**AI Output:**
> [Subject: Important Update Regarding Your Server Shipment]
> 
> Dear Client,
> 
> I am writing to sincerely apologize for a delay regarding your recent order. Due to unforeseen supply chain disruptions, the shipment of your servers has been delayed by two weeks. 
> 
> We understand how critical this hardware is to your operations, and we are actively working to expedite the process. As a gesture of our commitment to your business, we have applied a 10% discount to your next order.
> 
> Please let us know how you would like to proceed:
> * Confirm you would like to maintain the delayed order.
> * Cancel the order for a full refund.
> 
> Kindly provide your decision by this Friday so our logistics team can make the necessary arrangements. Thank you for your continued patience.
> 
> Best regards,
> 
> [Your Name]

#### Scenario 2: Internal Meeting Request
**Sample Input:** 
> "need meeting with dev team next tuesday at 2pm. discuss the new api integration. tell them to review the docs I attached before the meeting. keep it brief."

**AI Output:**
> [Subject: Action Required: API Integration Meeting - Next Tuesday 2:00 PM]
> 
> Hi Team,
> 
> We need to align on the new API integration rollout. Please block out time for a mandatory sync next Tuesday at 2:00 PM.
> 
> To ensure our meeting is as productive as possible, please complete the following action item beforehand:
> * Review the attached API documentation.
> 
> Come prepared with any questions or technical blockers you foresee. I will send out the calendar invite shortly. 
> 
> Best,
> 
> [Your Name]

#### Scenario 3: Cold Outreach / Sales
**Sample Input:** 
> "reach out to sarah at techcorp. saw her post on linkedin about needing better cybersecurity. we sell AI threat detection software. ask for 10 min call next week."

**AI Output:**
> [Subject: Enhancing TechCorp's Cybersecurity Infrastructure]
> 
> Hi Sarah,
> 
> I saw your recent post on LinkedIn regarding the growing need for robust cybersecurity measures, and your insights deeply resonated with our team.
> 
> I am reaching out because we specialize in AI-driven threat detection software that proactively identifies breaches before they escalate. Given TechCorp's current scaling trajectory, our platform could seamlessly integrate with your existing infrastructure to provide immediate, automated threat mitigation.
> 
> I would love to learn more about your current security stack. Do you have 10 minutes for a brief introductory call next week? 
> 
> Best regards,
> 
> [Your Name]

### 📊 Analysis
The prompt successfully acts as a linguistic translator, turning fragmented "brain dumps" into highly polished corporate communication. The strict 150-word constraint ensures the AI avoids the typical pitfall of generating overly verbose emails. The mandated bullet points for action items ensure that the emails are not just polite, but functionally effective in driving a response.

### 🪞 Reflection (Email Generator)
Automating email generation requires a delicate balance between structure and empathy. A purely robotic email is jarring, but a highly creative email might misrepresent the sender's intent. By heavily constraining the structure (Subject line, word count, bullet points) while dictating a specific tone ("professional and empathetic"), the prompt creates a reliable "corporate voice" that scales perfectly across multiple scenarios.

---

## 🔬 Project 2: Research Paper Summarizer

**Goal:** Create an automation prompt that ingests dense, highly technical academic abstracts or papers and outputs a structured, easily digestible summary for a non-technical executive or busy researcher.

### ⚙️ The Automation Prompt
> "You are a Chief Scientific Officer analyzing academic research. Read the following text and provide a structured summary tailored for a busy executive. 
> 
> **Format Requirements:**
> 1. **The TL;DR:** One single sentence summarizing the entire paper.
> 2. **Key Findings:** Exactly 3 bullet points detailing the most critical data or discoveries.
> 3. **Business/Real-World Application:** A short paragraph explaining why this research actually matters and how it can be applied to industry.
> 
> **Constraints:**
> - Strip away complex academic jargon. Explain it as if speaking to a high school graduate.
> - Do not include any introductory conversational text.
> 
> **Research Text:**
> [INSERT_RESEARCH_HERE]"

### 📝 Test Cases

#### Scenario 1: Medical Research
**Sample Input:** 
> "Abstract: We investigated the efficacy of targeted mRNA delivery utilizing lipid nanoparticles (LNPs) functionalized with aptamers targeting the epidermal growth factor receptor (EGFR) in vivo. Mice bearing human glioblastoma xenografts were treated intravenously. Results demonstrated a 74% reduction in tumor volume compared to the control group, driven by the localized translation of pro-apoptotic proteins. Minimal off-target hepatotoxicity was observed, indicating a highly specific biodistribution profile."

**AI Output:**
> **The TL;DR:** 
> Scientists have developed a new, highly targeted way to deliver medicine directly into brain tumors, successfully shrinking them without causing major side effects.
> 
> **Key Findings:**
> * The new delivery method reduced the size of the tumors by 74% in testing.
> * The medicine works by entering the tumor cells and triggering them to self-destruct.
> * The treatment was highly accurate, mostly avoiding damage to healthy organs like the liver.
> 
> **Business/Real-World Application:**
> This research proves that highly targeted "smart drugs" can successfully treat complex cancers like brain tumors. Pharmaceutical companies can leverage this delivery system to create safer, more effective oncology treatments that minimize the harsh side effects typically associated with traditional chemotherapy.

#### Scenario 2: Materials Science
**Sample Input:** 
> "Abstract: This paper presents the synthesis of a novel graphene-aerogel composite doped with silver nanoparticles. The material exhibits an ultra-low density of 0.15 mg/cm3 and a hierarchical porous structure. Compression testing revealed elastic recovery up to 90% strain. Furthermore, the composite demonstrated extraordinary piezoresistive sensitivity, rendering it highly effective for real-time human motion monitoring and wearable sensor applications."

**AI Output:**
> **The TL;DR:** 
> Researchers have created a revolutionary, ultra-lightweight material that conducts electricity and acts like an incredibly sensitive sponge.
> 
> **Key Findings:**
> * The new material is practically weightless and extremely porous.
> * It is highly durable and can be squished to 10% of its size, bouncing right back to its original shape.
> * It is highly sensitive to touch and pressure, changing its electrical resistance when squeezed.
> 
> **Business/Real-World Application:**
> Because this material is lightweight, flexible, and highly sensitive to movement, it is perfect for the wearable technology market. Tech companies could use this to manufacture ultra-thin smart clothing, advanced fitness trackers, or highly responsive robotic skin that can "feel" pressure.

#### Scenario 3: Computer Science (AI)
**Sample Input:** 
> "Abstract: We introduce 'SparseGPT', a novel pruning methodology for Large Language Models (LLMs) comprising 100 billion+ parameters. Traditional magnitude pruning degrades perplexity at high sparsity levels. SparseGPT utilizes a one-shot, layer-wise weight update scheme using an approximate Hessian inverse. We achieved 60% unstructured sparsity on a 175B parameter model with zero retraining and negligible accuracy loss, effectively reducing VRAM inference requirements by half."

**AI Output:**
> **The TL;DR:** 
> Computer scientists have found a new way to delete 60% of an AI model's code without making it any less intelligent, drastically reducing the cost to run it.
> 
> **Key Findings:**
> * The new "SparseGPT" method safely removes unnecessary data from massive AI models.
> * It successfully shrank a massive AI model by 60% without requiring the AI to be retrained.
> * The smaller model performed just as well as the original, but required half the computer memory to run.
> 
> **Business/Real-World Application:**
> Running cutting-edge AI models currently requires millions of dollars in massive server farms. This technology allows tech companies to shrink those models so they can run on much cheaper, smaller computers (and eventually smartphones) while maintaining top-tier performance, vastly lowering the barrier to entry for AI startups.

### 📊 Analysis
The automation prompt successfully performs a complex "translation" task. It not only extracts the core information but actively restructures it and translates it out of domain-specific jargon (e.g., translating "off-target hepatotoxicity" to "damage to healthy organs like the liver"). The rigidly forced structure (TL;DR, 3 Bullets, Business Application) ensures that the output is instantly readable and perfectly suited for an automated news aggregator or internal executive dashboard.

### 🪞 Reflection (Research Summarizer)
The true power of an LLM in an automation pipeline is its ability to understand semantics, not just syntax. By directing the AI to synthesize the information through the lens of a "Chief Scientific Officer," it understands that it must extract the *value*, not just the *data*. The negative constraint prohibiting jargon is the most critical element of this prompt, proving that we can use AI to democratize complex, siloed academic knowledge for the broader business world.

---

## 🏁 Conclusion
Both the Email Generator and the Research Paper Summarizer prove that prompt engineering is highly effective for building robust, scalable automation tools. By mastering structural constraints, negative limits, and persona framing, we can build specialized AI pipelines that save thousands of hours of manual labor in writing and research.
