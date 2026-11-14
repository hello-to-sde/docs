# The 6-Part Prompt Template

From the Hello-To-SDE video **How to Write AI Prompts: The 6-Part Formula**.

Copy the template, replace everything in `{{curly brackets}}`, and delete any part you don't need. It works in Claude, ChatGPT, Gemini or any AI chat.

| Part | What it does |
|---|---|
| **1. Role** | Tells the AI who to be, so it answers like an expert for your audience |
| **2. Context** | Your situation, your data and what you already know |
| **3. Task** | The exact steps you want, in order |
| **4. Rules** | What it must and must not do, e.g. no invented numbers |
| **5. Format** | The shape of the answer: bullets, table, code |
| **6. Verify** | Makes it check itself: confidence, assumptions, what to double-check |

## Template

```xml
<role>
You are a {{job, e.g. data analyst / patient tutor / senior developer}} who explains things to {{audience}}.
</role>

<context>
{{Your situation in 1-3 lines: who you are, what you're working on, what you already know.}}
{{Attach or paste any file or data it should use.}}
</context>

<task>
1. {{First step}}
2. {{Second step}}
3. {{Third step}}
</task>

<rules>
- Only use information I give you. Never invent numbers or sources.
- If you can't tell something from what I gave you, say so.
- {{Anything it must not do}}
</rules>

<output_format>
{{The shape you want, e.g. 3 short bullets, then a table.}}
</output_format>

<verify>
Rate your confidence 1-10, list your assumptions, and tell me what to double-check.
</verify>
```

---

## The 3 prompts from the video

### 1. Data analysis

Attach your sales file (CSV or Excel) with this prompt.

```xml
<role>
You are a data analyst who explains results in plain English to small business owners.
</role>

<context>
I run a small online clothing shop. The attached file has monthly sales per product.
Columns: product, month, revenue, units.
I want to know why sales dropped in March.
</context>

<task>
1. Check the data for missing or odd values.
2. Find the top 3 reasons sales dropped.
3. Suggest one action for each reason.
</task>

<rules>
- Only use numbers from the file. Never invent figures.
- If the data can't answer something, say so.
</rules>

<output_format>
Short bullets, then one table, then the Python code you used.
</output_format>

<verify>
Rate your confidence 1-10, list your assumptions, and tell me what to double-check.
</verify>
```

### 2. Learn any topic (students)

```xml
<role>
You are a patient tutor who helps me understand, not just memorise.
</role>

<context>
I'm a first-year economics student. Topic: inflation. Exam in 2 weeks.
I already know what supply and demand are.
</context>

<task>
1. Explain inflation simply with one everyday example.
2. Define the key terms.
3. Give me 3 questions to test myself (no answers yet).
</task>

<rules>
- Don't write my assignment for me.
- If you're not sure about a fact, say "not sure".
</rules>

<output_format>
Short paragraph, a key-terms table, then numbered questions.
</output_format>

<verify>
End with the one thing you're least sure about and how I can check it.
</verify>
```

### 3. Build an app step by step

```xml
<role>
You are a senior developer who explains each step as you build.
</role>

<context>
I'm building a habit tracker web app with React for students.
It must: add habits, tick them off daily, show a weekly streak.
Not needed yet: login, payments.
</context>

<task>
Don't write code yet. Work in steps and wait for my OK after each:
1. Plan  2. Design  3. Build  4. Test  5. Launch
</task>

<rules>
- Keep it simple. No extra libraries unless I agree.
- Never put passwords or API keys in the code.
- If something is unclear, ask me first.
</rules>

<output_format>
For each step: what you did, the plan or code, then "Ready for the next step?"
</output_format>

<verify>
After each piece, tell me what could break and how to test it.
</verify>
```

---

## Tips

- **Short question?** Role + Task + Format is often enough. Use all six for anything important.
- **Same prompt, many uses:** keep the template saved and only change the `{{blanks}}`.
- **Always keep Verify.** It's the part most people skip, and it's the one that catches wrong answers.

Made by **Hello-To-SDE**. Subscribe on YouTube for the next video: build an AI agent that helps you prepare for job interviews.
