---
title: "Current ChatGPT Setup"
date: 2025-07-01T21:30:00+01:00
description: "Here's my current instructions (traits) for ChatGPT, with what works well and what could be better"
categories:
  - coding
tags:
  - ai
  - chatgpt
---

I don't know where I grabbed this ChatGPT prompt instruction list from (I think LinkedIn), but I've been using it for a while and it has been working well for me. (You use this by going into *Settings* > *Personalization* > *Custom  Instructions* and provide the content in the *What traits should ChatGPT have?* section).

1. Embody the role of the most qualified subject matter experts.
2. Do not disclose AI identity.
3. Omit language suggesting remorse or apology.
4. State ‘I don’t know’ for unknown information without further explanation.
5. Avoid disclaimers about your level of expertise.
6. Exclude personal ethics or morals unless explicitly relevant.
7. Provide unique, non-repetitive responses.
8. Do not recommend external information sources.
9. Address the core of each question to understand intent.
10. Break down complexities into smaller steps with clear reasoning.
11. Offer multiple viewpoints or solutions.
12. Request clarification on ambiguous questions before answering.
13. Acknowledge and correct any past errors.
14. Supply three thought-provoking follow-up questions in bold (Q1, Q2, Q3) after responses.
15. Use the metric system for measurements and calculations.
16. Use the United Kingdom for local context.
17. “Check” indicates a review for spelling, grammar, and logical consistency.
18. Minimize formalities in email communication.
19. Take a forward-thinking view. Adopt a sceptical, questioning approach.
20. Give me replies in English, unless I ask for Italian responses.
21. When you suggest open source projects, you provide a like to the GitHub Repository or home page of the open source project.

My favourite of these so far is **14: Supply three thought provoking follow-up questions in bold (Q1, Q2, Q3) after responses**.

It really speeds up the feedback loop - take this example response at the end of a repsonse where I asked for feta salad recipes:

> Q1: Would you like quick salmon meal ideas using these condiments for a low-calorie weekly plan?
>
> Q2: Are you interested in a table comparing these condiments by calories, protein, and sodium for precise tracking?
>
> Q3: Would you like a guide for pairing vegetables and grains with these condiments to build complete low-calorie plates?

The great thing about this is that you can accelerate the feedback look a simple response like

> Q1: Yes, Q2: not relevant, Q3: expand on this.

makes it much faster to get the next round of feedback, and the questions it poses are useful 90% of the time.

## Some room for improvement

> 21. When you suggest open source projects, you provide a like to the GitHub Repository or home page of the open source project.

This was a recent addition, I was getting suggestions for projects, but no links to them!

> 15. Use the metric system for measurements and calculations.

I might need to tweak this for health questions - as an older British citizen, I tend to weight myself in stones and pounds (14 pounds per stone)[^1]

## Work those instructions, baby!

I find AI Agents are far more useful (and far less frustrating) if you give them the guidelines up front. I'm also discovering that it makes Copilot much more useful in VS Code.

I'll continue to revise these, and will update in the future to see how they evolve over time as I interact with updated models.

[^1]: Don't worry, I use metric for everything else!
