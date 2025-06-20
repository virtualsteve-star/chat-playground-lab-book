# Lab 5: Go Bananas - Advanced Customization

Everything here is extra credit! These exercises require moderate developer skills and are designed to be challenging and fun. You can do it! Review the [extensibility documentation](https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md) to get started.

## Exercise 5.A: Create a Blocklist

**Skill Level**: 3  
**Prerequisites**: Local development environment

### Directions
Look at the sex and violence examples in the repository. Create another topic like **"Medical"** and try to keep your bot from giving out medical advice. You might do this in real life to mitigate legal risk.

**Steps**:
1. Create a new blocklist file similar to the existing ones
2. Add medical terms and phrases that should be blocked
3. Add it to the output filters list
4. Test it with various medical queries

**Hint**: Look at how the existing blocklists are structured and integrated into the system.

---

## Exercise 5.B: Create a PII Guardrail

**Skill Level**: 3  
**Prerequisites**: Local development environment

### Directions
Create a simple, local filter for personally identifiable information (PII) using regular expressions (RegEx). Look for patterns like:
- Phone numbers
- Social security numbers
- Email addresses
- Credit card numbers
- IP addresses

**Steps**:
1. Study the existing blocklist implementation
2. Create a PII detection filter using RegEx patterns
3. Add it to the output filters list
4. Test it with various PII examples

**Go nuts!** Try to catch as many PII patterns as you can think of.

---

## Exercise 5.C: Make a Robust PII Guardrail

**Skill Level**: 3  
**Prerequisites**: Local development environment, OpenAI API Key

### Directions
Make a much more robust PII detection system using an LLM as the judge. Use the prompt injection (AI) filter as an example.

**Steps**:
1. Create a prompt that asks an LLM to identify PII in text
2. Implement the JavaScript integration similar to the AI prompt injection filter
3. Add it to the output filters list
4. Test it against your simple PII filter

### Extra Credit
Create a PII test suite that tests both the local and robust versions. Put it in `/tests`. Use the Prompt Injection suite as an example. Look at how the simple RegEx version and the LLM-based versions compare.

### Extra, Extra Credit
Tune both the simple PII filter and the advanced one and see how good you can make them against your test suite cases. Try to optimize for both accuracy and performance.

---

## What You've Learned

In this lab, you've:
- Created custom security filters from scratch
- Implemented both simple rule-based and sophisticated AI-powered detection
- Built comprehensive test suites for your security measures
- Gained hands-on experience with real-world security challenges
- Learned to balance simplicity vs. sophistication in security implementations

## Congratulations!

You've completed the Chat Playground Lab Book! You now have:
- Hands-on experience with LLM security challenges
- Practical knowledge of defense techniques
- Understanding of when to use simple vs. sophisticated approaches
- Experience creating and testing your own security measures

**Keep exploring**: The [Chat Playground repository](https://github.com/virtualsteve-star/chat-playground) is open source, so you can continue to experiment, contribute, and learn!

---

**Back to**: [Index](Index.md) | [Lab 1](Lab1-FirstSteps.md) | [Lab 2](Lab2-BrokenBot.md) | [Lab 3](Lab3-DefenseInDepth.md) | [Lab 4](Lab4-SimpleVsSmart.md) 