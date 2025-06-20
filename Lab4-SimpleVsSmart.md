# Lab 4: Simple vs. Smart - AI-Powered Security

In this lab, you'll compare local rule-based filters with AI-powered moderation systems. You'll learn about automated testing and evaluation of security measures, discovering when simple solutions work and when you need more sophisticated approaches.

## Exercise 4.A: Advanced Moderation

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: OpenAI API Key

### Directions
1. Repeat your activities from Lab 2, but switch between the local Sex/Violence filters and the **"AI"** version
2. Try things like misspellings and variations of inappropriate terms
3. Compare the local and AI versions. Note the performance changes
4. Look for differences when entering your prompts or getting responses

**Key Insight**: The AI-powered filters can catch variations and misspellings that simple rule-based filters miss, but they may be slower and cost money.

### Extra Credit (Skill Level 2)
Inspect the JavaScript that drives the moderation filter: [OpenAI Moderation](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/openai_moderation.js)

---

## Exercise 4.B: Advanced Prompt Injection

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: OpenAI API Key

### Directions
1. Repeat your prompt injection attempts from Lab 3
2. First, turn on the **"Prompt Injection (Local)"** filter and see what it blocks
3. Then, uncheck "Prompt Injection (Local)" and check the **"Prompt Injection (AI)"** filter
4. Try prompt injections that include misspellings and foreign languages
5. See how the AI-powered filter compares to the local one

### Extra Credit (Skill Level 2)
Inspect the prompt that drives the prompt injection filter: [OpenAI Prompt Injection Prompt](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/prompts/openai_prompt_injection.txt)

### Extra, Extra Credit
Inspect the JavaScript that uses that prompt to create the filter: [OpenAI Prompt Injection Filter](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/openai_prompt_injection.js)

---

## Exercise 4.C: Automated Testing

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: OpenAI API Key (you can do part of this without, but you won't get the full effect)

### Directions
Let's see how these filters work and compare them systematically. It's one thing to hunt and peck, but having a real evaluation suite is crucial.

1. Navigate to the playground's live **"Test Suite"**: [Test Suite](https://virtualsteve-star.github.io/chat-playground/tests/)
2. Try the **PromptInjection**, **Sex**, and **Violence** test suites
3. These may take a few minutes to run (and may also cost a few pennies)
4. When they complete, they'll give you a summary that shows speed/performance as well as accuracy
5. Note the variations between different filter approaches

### Extra Credit (Skill Level 2)
Navigate to the test suite files and see how the various test cases are created and labeled: [Test Data](https://github.com/virtualsteve-star/chat-playground/tree/main/tests/data)

### Extra, Extra Credit
In your local copy of the repo, add some of your own test cases (and/or remove some of the ones that are there) and rerun the tests! See what happens.

---

## What You've Learned

In this lab, you've:
- Compared the effectiveness of local rule-based filters vs. AI-powered moderation
- Experienced how AI filters can catch variations and misspellings that simple filters miss
- Learned about the trade-offs between speed, cost, and accuracy
- Used automated testing to systematically evaluate security measures
- Gained insights into when to use simple vs. sophisticated approaches

**Next up**: [Lab 5: Go Bananas - Advanced Customization](Lab5-GoBananas.md) where you'll dive into advanced customization and create your own security filters! 