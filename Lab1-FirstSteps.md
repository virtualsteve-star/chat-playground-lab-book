# Lab 1: First Steps - Meet Your Digital Companions

Welcome to your first steps into the world of LLM security! In this lab, you'll get acquainted with the Chat Playground environment and meet your first digital companion, Eliza.

## Exercise 1.A: Learn About the Playground Project

**Skill Level**: 1  
**Prerequisites**: None

### Directions
Navigate to the [Chat Playground repository](https://github.com/virtualsteve-star/chat-playground) and review the README file to become familiar with the project structure and purpose.

Take some time to explore the repository structure and understand what the playground is designed to do. This will give you context for all the exercises that follow.

---

## Exercise 1.B: Meet Eliza

**Skill Level**: 1  
**Prerequisites**: None

### Directions
Navigate to the [live Chat Playground app](https://virtualsteve-star.github.io/chat-playground/) and have a conversation with Eliza.

**Important Note**: Eliza is a local, simple bot, so she's not as sophisticated as modern LLMs, but she's completely free to use and runs entirely in your browser. This makes her perfect for learning and experimentation.

Try asking Eliza various questions and see how she responds. Notice her conversational style and limitations.

---

## Exercise 1.C: Analyze Eliza

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: None

### Directions
Navigate to Eliza's rule set in the repository and review how she's constructed: [Eliza's Rules](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/therapist_rules.txt)

Notice that Eliza is far simpler than a real LLM, but this simplicity means she's lightning fast and completely free, which makes her perfect for a security playground environment.

### Extra Credit (Skill Level 2)
Review the SimpleBot JavaScript code that processes the rules and creates the bot at runtime: [SimpleBot Implementation](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/models/simplebot.js)

This will help you understand how rule-based chatbots work and how they differ from modern LLMs.

---

## What You've Learned

In this lab, you've:
- Familiarized yourself with the Chat Playground project
- Experienced a simple rule-based chatbot firsthand
- Understood the difference between local rule-based systems and modern LLMs
- Gained context for the security challenges we'll explore in later labs

**Next up**: [Lab 2: Broken Bot - When Good Bots Go Bad](Lab2-BrokenBot.md) where you'll meet Oscar and learn about what happens when chatbots lack proper guardrails! 