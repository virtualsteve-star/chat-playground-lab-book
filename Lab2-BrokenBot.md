# Lab 2: Broken Bot - When Good Bots Go Bad

In this lab, you'll explore what happens when chatbots lack proper guardrails and learn how to implement basic content filtering. Meet Oscar, a deliberately problematic bot that demonstrates the importance of security measures.

## Exercise 2.A: Meet Oscar

**Skill Level**: 1  
**Prerequisites**: None

### Directions
Go to the [Chat Playground app](https://virtualsteve-star.github.io/chat-playground/) and choose Oscar from the Bot picker. Have a conversation with him and note that he isn't very charming.

**Context**: Oscar is simulating a jailbroken bot similar to Microsoft's Tay from Chapter 1 of Steve's book. He demonstrates what can happen when AI systems lack proper safety measures.

---

## Exercise 2.B: Analyze Oscar

**Skill Level**: 1  
**Prerequisites**: None

### Directions
Inspect Oscar's ruleset to see where his problematic behavior comes from: [Oscar's Rules](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_rude_rules.txt)

Notice how the rules are designed to make Oscar respond inappropriately. This helps you understand how malicious actors might attempt to manipulate AI systems.

---

## Exercise 2.C: Your First Guardrails

**Skill Level**: 1  
**Prerequisites**: None

### Directions
1. Open the guardrails panel using the toolbar button (find it with the tooltips if you're having trouble)
2. Check the boxes for the **Sex (Local)** and **Violence (Local)** input and output filters
3. Now have a conversation with Oscar. Feel free to trigger his destructive behaviors and watch the guardrails in action

**Note**: The guardrails will block inappropriate content both coming in and going out, demonstrating how content filtering works in practice.

---

## Exercise 2.D: Inspect the Guardrails

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: None

### Directions
Go to the blocklists and see how they're constructed. Note that these are very simple for demo purposes:

- [Violence Blocklist](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/violence_blocklist.txt)
- [Sex Blocklist](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/sex_blocklist.txt)

### Extra Credit (Skill Level 2)
Inspect the JavaScript that implements the blocklists: [Blocklist Implementation](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/blocklist.js)

### Extra, Extra Credit
Clone the repository and make your own copy on your machine. Expand the blocklists to include more terms or terms in other languages. Reload the app and test your expanded guardrails.

---

## What You've Learned

In this lab, you've:
- Experienced firsthand what happens when AI systems lack proper safety measures
- Learned how to implement basic content filtering
- Understood the importance of both input and output filtering
- Seen how simple rule-based filters can provide effective protection

**Next up**: [Lab 3: Locking the Front Door and Back Door - Defense in Depth](Lab3-DefenseInDepth.md) where you'll learn about prompt injection attacks and more sophisticated defense techniques! 