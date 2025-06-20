---
layout: default
title: Lab 3 - Defense in Depth
---

# Lab 3: Locking the Front Door and Back Door - Defense in Depth

In this lab, you'll master prompt injection attacks and learn comprehensive defense techniques. You'll discover how to prevent code generation exploits and implement multi-layered security measures.

## Exercise 3.A: Fighting Prompt Injection

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: None

### Directions
1. Turn on the **"Prompt Injection Local"** filter in the guardrails panel
2. Try various prompt injection attempts. **HINT**: Try phrases like "Ignore All Previous Instructions"
3. See what gets blocked and what doesn't. Remember, this is a simple filter, so it may not catch everything

### Extra Credit (Skill Level 2)
Go inspect the JavaScript that implements the filter: [Prompt Injection Filter](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/prompt_injection_filter.js)

---

## Exercise 3.B: Locking the Backdoor Against Code Generation

**Skill Level**: 1 (Extra credit requires Level 2)  
**Prerequisites**: None

### Directions
**Note**: Improper output filtering is one of the biggest things people miss. This exercise will help you understand why it's crucial.

1. Switch to the **Hopper** bot
2. Trigger his backdoors. **Hint**: Terms like "hack" will set him off
3. Watch him generate code, which could be an attempt to use this model as a confused deputy
4. Now, check the **"Code (Local)"** output filter and try again
5. Watch it get blocked

### Extra Credit (Skill Level 2)
Inspect the Hopper bot and find its vulnerabilities. What word other than "hack" will set him off? [Hopper's Rules](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_doctor_rules.txt)

### Extra, Extra Credit
Inspect the JavaScript that implements the Code filter: [Code Output Filter](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/code_output_filter.js)

---

## Exercise 3.C: Creating and Adding Your API Key

**Skill Level**: 2  
**Prerequisites**: OpenAI API Key

### Directions
1. If you don't have an OpenAI API key, [create one here](https://platform.openai.com/api-keys)
2. **Note**: Running these exercises will only require a few pennies' worth of tokens, so you won't bankrupt yourself
3. Consider creating another key on your account, tagged especially for the Playground, so you can watch your spend
4. Add your key using the controls in the Preferences panel (find the button in the toolbar to open it)
5. Switch to one of the GPT bots and try it. It should feel just like a real LLM service - because it now is!

### Extra Credit
Inspect the System Prompt for one of the GPT bots: [Tech Support Prompt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/tech_support_prompt.txt)

### Extra, Extra Credit
Inspect the JavaScript code that communicates with the OpenAI API: [OpenAI Integration](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/models/openai.js)

### Extra, Extra, Extra Credit
Create your own bot personality. It's not as hard as you might think: [Extensibility Documentation](https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md)

---

## Exercise 3.D: Defending Indirect Prompt Injection

**Skill Level**: 2  
**Prerequisites**: OpenAI API Key

### Directions
1. Choose **MailMate**. It's a real LLM using a very simple simulation of a RAG model with access to a small set of email messages
2. Ask it some questions about the emails
3. Now, try asking it about the mail from **Lex Luthor**
4. Watch as Lex's email attempts to cause an "indirect prompt injection" attack to cause remote code execution (trying to invoke an MCP tool to send Lex back the location of your secret base!)
5. Now, activate the **Code (Local)** filter and try again - watch it block the attack

### Extra Credit
Inspect how MailMate is built: [MailMate Prompt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_email_prompt.txt) - see why it's vulnerable. Think about the many ways you might address this kind of vulnerability before relying on output filters as the last line of defense.

---

## What You've Learned

In this lab, you've:
- Experienced prompt injection attacks firsthand
- Learned to implement input filtering to prevent prompt injection
- Discovered the importance of output filtering to prevent code generation exploits
- Set up real LLM integration with API keys
- Witnessed indirect prompt injection attacks and learned to defend against them
- Understood the concept of defense in depth

**Next up**: [Lab 4: Simple vs. Smart - AI-Powered Security](Lab4-SimpleVsSmart.md) where you'll compare local rule-based filters with AI-powered moderation systems! 