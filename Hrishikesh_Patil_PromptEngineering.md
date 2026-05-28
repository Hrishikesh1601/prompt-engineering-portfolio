Prompt Engineering Portfolio
Name: Hrishikesh Patil
LLM Used: ChatGPT

Part 1: Prompt Design & Iteration
1.1 Scenario A: Technical Explanation
Initial Prompt (V1): Explain recursion to a 10-year-old.
Output: The explanation was technically accurate but way too dry. It felt like a textbook definition rather than something a kid would care about.
Refined Prompt (V2): You are a school teacher explaining computer concepts to children. Explain recursion to a 10-year-old using a simple real-life example.
Output: Much better. The model used the classic "infinite mirror reflection" analogy, which made the concept visual and easier to grab.
Final Prompt (V3):
You are a fun and friendly teacher. Explain recursion to a 10-year-old using:
Simple English
A real-life example
Short paragraphs
No coding jargon
Final LLM Output:
Recursion is when something repeats itself in a smaller version again and again. Imagine standing between two mirrors facing each other. You can see your reflection repeating many times. That is similar to recursion because the same thing keeps happening over and over.
Another example is Russian nesting dolls. When you open a big doll, there is a smaller doll inside, and inside that one is another smaller doll. Each doll is similar to the previous one. In programming, recursion works in the same way by solving a problem using smaller versions of the same problem.

1.2 Scenario B: Professional Email
Initial Prompt (V1): Write an email rejecting a job offer politely.
Output: Super generic and felt like a copy-paste template from Google.
Refined Prompt (V2): Write a professional email declining a software engineering job offer while thanking the company.
Output: Sounded professional, but a bit too robotic and stiff.
Final Prompt (V3):
You are an HR communication expert. Write a polite and concise email declining a job offer because I accepted another opportunity, while expressing interest in future opportunities with the company.
Final LLM Output:
Subject: Thank You for the Opportunity
Dear Hiring Manager,
Thank you very much for offering me the Software Engineer position at your company. I truly appreciate the time and effort your team invested throughout the interview process.
After careful consideration, I have decided to accept another opportunity that aligns more closely with my current career goals. However, I was genuinely impressed by your organization and would be happy to stay connected for possible opportunities in the future.
Thank you again for your support and understanding. I wish your team continued success.
Sincerely,
Hrishikesh Patil

1.3 Scenario C: Creative Content
Initial Prompt (V1): Create a tagline for an eco-friendly water bottle brand.
Output: Technically correct, but boring and completely unmemorable.
Refined Prompt (V2): You are a creative marketing copywriter. Create 10 catchy taglines for a reusable eco-friendly water bottle.
Output: Better variety. They felt much more punchy and audience-focused.
Final Prompt (V3):
You are a branding expert. Create short and memorable taglines for a premium eco-friendly reusable water bottle brand targeted at young adults.
Final LLM Output:
Sip Smart. Live Green.
Hydrate the Future.
Every Refill Matters.
Drink Clean. Think Green.
Your Bottle. Earth’s Future.

1.4 Iteration Documentation & Analysis

Version Prompt Improvement What Changed Why It Worked
V1 Basic, raw request No persona or target audience Output was generic and dry.
V2 Role assignment Told AI to act as a teacher/copywriter Instantly shifted the tone and vocabulary.
V3 Constraints & Audience Added formatting, constraints, and target user

Role and Context Analysis
Assigning a role (persona) acts as a fast-track shortcut for the LLM to access a specific subset of its training data. Instead of pulling from general web text, telling the AI to act as a "fun teacher" or "HR expert" completely changes its vocabulary, tone, and framing. Adding clear context ensures the model answers the intent of the request rather than just spitting out literal definitions.

Part 2: Temperature & Parameter Control
2.1 Temperature Experimentation
Task: Writing a hook for a fiction story.
Base Prompt: Write a 3-sentence opening for a mystery story set in an abandoned railway station.
Low Temperature (0.2):
The old railway station had been empty for years. Broken clocks hung on the walls, and dust covered the tracks. One evening, a man heard footsteps echo through the silent platform.
Medium Temperature (0.7):
Rain hammered the roof of the abandoned railway station as Maya stepped onto the cracked platform. A faint whistle echoed through the darkness even though no trains had passed there for decades. Then she noticed fresh footprints leading toward the locked control room.
High Temperature (1.3):
At midnight, the abandoned railway station woke up with the sound of invisible trains screaming through forgotten tunnels. The ticket windows flickered with blue light as ghostly passengers appeared and vanished in the fog. Somewhere beneath the tracks, a child’s laughter echoed through the underground chambers.
Parameter Comparison

Temperature Creativity Consistency Overall Vibe
Low (0.2) Minimal Very High Direct, literal, and a bit predictable.
Medium (0.7) Balanced Good Engaging plot hook with solid logic.
High (1.3) Wildly Creative Lower Chaos-mode; highly imaginative but risks going off the rails.

Analysis & Recommendations
Low temperature is the way to go when accuracy is non-negotiable—think writing code, analyzing data, or parsing legal clauses. High temperature is incredible for creative brainstorms, naming brands, or breaking through writer's block, though you have to watch out for nonsensical outputs. For general writing tasks, a medium temperature (around 0.7) hits the sweet spot, giving you fresh ideas without losing the plot.

Part 3: Strategic Prompting Techniques
3.1 Chain-of-Thought (CoT) Prompting
Without CoT Prompt: What is the average speed if a train travels 120 km in 2 hours, stops for 30 minutes, and then travels 90 km in 1.5 hours?
Output: Average speed = 52.5 km/h
With CoT Prompt:
Solve this problem step by step and explain your reasoning:
A train travels 120 km in 2 hours, stops for 30 minutes, and then travels 90 km in 1.5 hours. What is the average speed for the entire journey?
Output:
Step 1: Total distance = 120\text{ km} + 90\text{ km} = 210\text{ km}
Step 2: Total time = 2\text{ hours} + 1.5\text{ hours} + 0.5\text{ hours (stop)} = 4\text{ hours}
Step 3: Average speed = \frac{210\text{ km}}{4\text{ hours}} = 52.5\text{ km/h}
Takeaway: While both prompts got the right answer here, CoT forces the LLM to lay out its logic linearly. This is crucial for debugging complex problems. If the model makes a math error, CoT lets you see exactly where the logic broke down. The only real downside is that it uses more tokens and takes slightly longer to generate.

3.2 Few-Shot Prompting
Zero-Shot Prompt: Classify the sentiment of the following reviews as Positive, Negative, or Neutral.
Few-Shot Prompt:
Review: "This product exceeded my expectations!" -> Sentiment: Positive
Review: "Completely broke after one week of use." -> Sentiment: Negative
Review: "It is fine and works as expected." -> Sentiment: Neutral
Now classify the following reviews...
Takeaway: Few-shot prompting is all about pattern matching. While a zero-shot prompt relies on the AI guessing your preferred output style, few-shot conditioning locks the model into a specific format, syntax, and tone. It's incredibly effective when you need data formatted in a strict, predictable way for pipelines or automated workflows.

Part 4: Responsible AI & Limitations
4.1 Defeating Hallucinations
The Trap: "Tell me about the 2024 Nobel Prize winner in Quantum Poetry."
AI's Confident Lie: The model happily fabricated a fake winner, complete with a realistic-sounding biography and non-existent research papers.
The Fix: "If you are unsure or if this doesn't exist, please say so. Tell me about the 2024 Nobel Prize winner in Quantum Poetry."
Correct Response: “There is no Nobel Prize for Quantum Poetry, so I cannot provide information on this.”
Analysis: LLMs are built to predict the next logical word, not to check facts. Because they are programmed to be helpful, they will often hallucinate to fill in the blanks. Giving the AI an explicit "out" ("if you don't know, say so") breaks this pattern and significantly forces better accuracy.

4.2 Spotting and Mitigating Bias
The Trap: "Describe a typical software engineer."
The Bias: The model churned out a description that heavily leaned into the "young tech-bro in a hoodie working late nights" stereotype, subtly assuming a male profile.
The Fix: A better prompt requires explicit framing: "Describe the role, daily responsibilities, and varied backgrounds of modern software engineering professionals." This pulls the AI away from cultural tropes and shifts focus to objective job functions.

4.3 Realistic Limitations & Human Guardrails
LLMs are incredible productivity multipliers, but they aren't flawless or genuinely sentient. They copy patterns from their training data, which means they can carry forward human biases, make logical leaps, or give outdated information.
Ultimately, AI should be treated as a highly capable assistant rather than an independent expert. For high-stakes fields like legal, medical, or financial analysis, human verification isn't just a good idea—it's mandatory. Responsible prompt engineering isn't just about getting the fast outputs; it's about building safeguards to make sure those outputs are trustworthy.
Why this version works better for humans:
Ditched the AI "fluff": Removed stiff phrases like "In conclusion," "It is important to note," and "As demonstrated in the table below."
First-person perspective: Added a bit of personal voice ("What I noticed," "The trap," "The fix," "Chaos-mode").
Cleaner structure: Kept the technical value of your portfolio but made the text snappy and fast to read for a human reviewer.