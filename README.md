SJSU Dining Hall Food Waste Reduction
Team: Isaac Nawabi · Zohal Sayed · Simrit Mann
Course: 110A Fundamentals of MIS | SJSU Spring 2026
UN SDG: Goal 12 Responsible Consumption and Production

1. Problem
Mia is a first-generation SJSU student working part-time to cover tuition. On a tight budget, she relies on the Spartan Food Pantry but often misses out on surplus meals from the dining hall because she has no way of knowing when or where food is available. Every day, SJSU dining facilities discard hundreds of pounds of perfectly edible food pasta, salads, sandwiches, and more simply because no system exists to connect that surplus to students who need it. The exact failure point is not that the food doesn't exist, but that the information about it never reaches the people who could use it. A dining hall worker knows there are 30 servings of pasta left at 7:30 PM. Mia does not. Nothing bridges that gap today.

2. AI Capability
We use text generation (Lab 1) to address this failure. The AI capability fits because the problem is an information-delivery problem: surplus food exists, but no clear, timely, human-readable alert is being created and distributed. A dining hall worker should not need to be a copywriter, they should be able to input three facts (food type, quantity, pickup time) and have a friendly, useful alert generated instantly and posted to the SAMMY App for students like Maria to see.
Text generation directly addresses this: given structured input from staff, Gemini drafts a warm, readable pickup alert in seconds. This is the same capability practiced in Lab 1, where we saw that a well-designed system prompt can turn raw data into a useful, audience-appropriate message with no manual writing required.
We chose this over image recognition (Lab 3) because the bottleneck is not identifying food visually staff already know what they have. The bottleneck is getting that information out fast, in plain language, to the right people.

3. Workflow
What goes in: A dining hall staff member enters three fields  food type, quantity available, and pickup window  into a simple input form at the end of a meal service.
What the AI does: Gemini 2.0 Flash receives that input through a system prompt that instructs it 1to act as an SJSU Dining Services assistant. It generates a 3–4 sentence pickup alert written in a warm, welcoming tone  not clinical or bureaucratic  suitable for posting directly to students.
What comes out: A plain-language alert such as:
"Hey Spartans! The Dining Commons has about 30 servings of pasta, salad, and garlic bread available for free pickup tonight at 7:30 PM at the main entrance. No sign-up needed just stop by before closing. Don't let good food go to waste!"
Who acts on it: The alert is reviewed by the staff member (a 10-second read) and then posted to the SJSU SAMMY App, where food-insecure students like Maria can see it in real time and pick up the food before it is discarded.
📸 [Screenshot of notebook output — Test Case 1 — to be added after running]
📸 [Screenshot of notebook output — Test Case 2 — to be added after running]
📸 [Screenshot of edge case output — to be added after running]

4. Failure Case
The failure: A staff member inputs "leftover event food  mixed items, some may have been sitting out" with a quantity of "unknown" and a pickup time of "sometime after 6." Gemini generates a confident, friendly alert anyway  "Come grab free food at the Dining Commons tonight after 6!" without flagging that the food condition is ambiguous or that the quantity and time are too vague to be actionable.
The real-world consequence: Mia walks across campus at 6:30 PM based on the alert, finds nothing, and loses trust in the system. Worse, if food that had been sitting out too long was redirected to the Spartan Food Pantry without a staff safety check, a student could consume food that causes illness.
Lab connection: In Lab 1, we observed that the model produces confident, well-formatted output regardless of input quality. A vague or incomplete prompt still generates a polished response — the model does not flag uncertainty or refuse to act. This showed us that confident output is not the same as accurate or safe output, and that input quality directly determines whether the alert is useful or harmful.

5. Oversight and Tradeoff
Oversight decision: A staff member must visually review and approve every AI-generated alert before it is posted. No alert goes live automatically. This review happens at the moment the alert is drafted, before it reaches any student.
Justification: In Lab 1, we observed that the model produces polished output even when given ambiguous or incomplete input. Because the alert directly affects whether a food-insecure student makes a trip across campus, and because the model cannot assess food safety or input completeness, human review is the only check between a bad input and a harmful outcome.
The one change: We would add an input validation step that requires staff to confirm food condition safe, unsure, do not donate before the alert is generated. If the staff member selects "unsure," the system blocks the alert and prompts a supervisor check instead of generating text.
What it costs: This adds approximately 30–60 seconds per alert and requires staff training on the three-option condition field. It reduces the speed advantage of the system slightly, but protects the students the system is designed to serve  particularly those at the Spartan Food Pantry who are most vulnerable to a misdirected or misleading alert.



