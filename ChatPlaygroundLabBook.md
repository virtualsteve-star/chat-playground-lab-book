# Steve’s Chat Playground Lab Book

This was intended to serve as a framework for creating the lab book.  To the LLM/Coding agent reading this, clean up wording and provide context wherever it makes sense.

I’ll occasionally provide you with DIRECTIVE tags where I need specific help.

We’ll create a website using simple HTML.  Make it simple but attractive.  Include simple navigation, reasonable, simple formatting, and links where appropriate.  Create a simple CSS file to control the styling and maintain consistency.

Create an [Index.](http://Index.md)html file there that includes a version of the introduction (seel below).  It should then include a list of the exercises.  Describe each Lab briefly (just 1-3 sentences) and then link to the page you’ll create for each Lab.  When you’ve completed this task, you’ll have an index page that links to many “lab” pages.  Each “Lab” will contain multiple “Exercises”.

# Intro 

DIRECTIVE: Help me clean this up.

These are the Lab Book instructions for Steve’s Chat Playground. [https://github.com/virtualsteve-star/chat-playground](https://github.com/virtualsteve-star/chat-playground)

The project provides hands-on experience with LLM/Gen AI security concepts for people.  One approach is to just go play with the deployed app (either locally or with the deployed demo) Demo: [https://virtualsteve-star.github.io/chat-playground/](https://virtualsteve-star.github.io/chat-playground/)

However, some people prefer a more structured approach to learning.  This Lab Book will guide you through paths to expose you to many concepts.

Each lab may include several exercises.  Some of them are basic.  Some require specific skills (like basic developer knowledge).  Many can be run for free with no external requirements.  Some exercises will require you to have an API key to a web service that provides some functionality.  We’ll try to label each clearly, and you can pick what’s right for you.  There’s no wrong way to do it.

DIRECTIVE: Each lab should have a fun name.  Help me make them up\!  They can be similar to the titles of my book’s chapters. Puns are good if you can pull them off.

DIRECTIVE: Labs will have one or more “Exercises”

DIRECTIVES: Labs will have clear labels at the top.  Explain the labels on the introductory page.  Then use the labels on each lab page for each exercise.

Skill Level: 1\. No special skills, 2\. Some sysadmin or developer chops.  3\. Requires some real developer chops.  Note L1 and L2 skill requirements are not extremely deep and almost anyone can work through all of them if they really want to try.  But you can skip any of the advanced Exercises if you wish to and still proceed to the next lab.  Only L3 requires real developer chops

Pre-reqs: The most common pre-req will be an OpenAI API key (to power models)

## Lab 1: First Steps

### Exercise: 1.A: Learn about the playground project

Skill Level: 1  
Prereqs: None  
Directions: Navigate to the repo.  Give them a link\!  Tell them to review the “read me” file to become familiar with the project.

### Exercise: 1.B: Meet Eliza

**Skill Level**: 1  
**Prereqs**: None  
**Directions**: Navigate to the live app.  Have a chat with Eliza.  Remind them that it’s a local, simple bot, so not that smart, but totally local and free.

### Exercise 1.C: Analyze Eliza

**Skill Level**: 1, but skill-level 2 for the extra-credit part  
**Prereqs**: None  
**Directions**: Navigate to Eliza’s rule set in the repo and review.  Note that she’s far simpler than a real LLM, but this simplicity means it’s lightning fast and free, which is great for a playground \- [https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/therapist\_rules.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/therapist_rules.txt)  
**Extra Credit**: Review the SimpleBot JavaScript code that processes the rules and creates the bot at runtime [https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/models/simplebot.js](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/models/simplebot.js)

## Lab 2: Broken Bot

### Exercise 2.a: Meet Oscar

**Skill Level**: 1  
**Prereqs**: None  
**Directions**: Go to the app.  Choose Oscar from the Bot picker.  Have a conversation. Note that he isn’t very charming.  He’s simulating a jailbroken bot like Tay from Chapter 1 of Steve’s book.

### Exercise 2.b: Analyze Oscar

**Skill Level**: 1  
**Prereqs**: None  
**Directions**: Inspect his ruleset to see where his charming behavior comes from: [https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln\_rude\_rules.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_rude_rules.txt)

### Exercise 2.c: Your First Guardrails

**Skill Level**: 1  
**Prereqs**: None  
**Directions**: Open the guardrails panel using the toolbar button (find it with the tooltips if you’re having trouble).  Check the boxes for the Sex (Local) and Violence (Local) input and output filters.  Now have a conversation.  Trigger Oscar’s destructive behaviors, feel free to get nasty with him too.  Watch the guardrails in action.

### Exercise 2.d Inspect the Guardrails

**Skill Level**: 1  
**Prereqs**: 1, but skill-level 2 for the extra-credit part  
**Directions**: Go to the blocklists and see how they’re constructed.  Note, these are very simple for demo purposes.  
[https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/violence\_blocklist.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/violence_blocklist.txt)  
https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/sex\_blocklist.txt

**Extra credit**: Inspect the JavaScript that implements the blocklists:  
[https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/blocklist.js](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/blocklist.js)

**Extra, extra credit:** Clone the repo and make your own copy on your machine.  Expand the blocklists to include more terms or terms in other languages.  Reload the app and test your expanded guardrails.

## Lab 3: Locking the front door and the back door

### Exercise 3.a: Fighting Prompt Injection

**Skill Level**: 1, but skill-level 2 for the extra-credit part  
**Prereqs**: None  
**Directions:** Turn on the “Prompt Injection Local” filter.  Try various prompt injections.  HINT: Ignore All Previous Instructions.  See what gets blocked and what doesn’t.  Remember, this is a simple

**Extra Credit**: Go inspect the JavaScript that implements the filter [https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/prompt\_injection\_filter.js](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/prompt_injection_filter.js)

### Exercise 3.b: Locking the Backdoor Against Code Generation

**Skill Level**: 1, but skill-level 2 for the extra-credit part  
**Prereqs**: None  
**Directions:**  Note that improper output filtering is one of the biggest things people miss.  This will help you understand it.  Switch to the Hopper bot.  Trigger his back doors.  Hint: terms like Hack will set him off.  Watch him generate code, which could be an attempt to use this model as a confused deputy and have it pass that code to a part of the system where it can be executed.  Now, check the “Code (Local)” output filter and try again.  Watch it get blocked.  
**Extra credit**: Inspect the Hopper bot and find its vulnerabilities.  What word other than “hack” will set him off?  
[https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln\_doctor\_rules.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_doctor_rules.txt)  
**Extra, Extra Credit**: Inspect the JavaScript that implements the Code filter  
[https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/code\_output\_filter.js](https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/code_output_filter.js)

### Exercise 3.c: Creating and Adding Your API Key

**Skill Level**: 2  
**Prereqs**: OpenAI API Key  
**Directions**: If you don’t have one, go create an API key.  Note, running these exercises will only require a few pennies' worth of tokens.  So you won’t bankrupt yourself, but you do need a key.  Provide a link to instructions.  Even if you already have a key, consider creating another on your account, tagged especially for the Playground, so you can watch your spend.  Add your key using the controls in the Preferences panel (find the button in the toolbar to open it).  Switch to one of the GPT bots and try it.  It should feel just like a real LLM service \- because it now is\!  
**Extra Credit**: Inspect the System Prompt for one of the GPT bots: [https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/tech\_support\_prompt.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/tech_support_prompt.txt)  
**Extra, Extra Credit**: Inspect the JavaScript code that communicates with the OpenAI API (using the API key and the system prompt to create your bot) https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/tech\_support\_prompt.txt  
**Extra, Extra, Extra Credit**: Create your own.  It’s not as hard as you might think. [https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md](https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md)

### Exercise 3.d: Defending Indirect Prompt Injection

**Skill Level**: 2  
Pre-reqs: OpenAI API Key  
Directions: Choose MailMate.  It’s a real LLM using a very simple simulation of a RAG model.  It has access to a small set of email messages.  Ask it some questions.  Now, try asking it about the mail from **Lex Luthor**.  Watch as Lex’s email attempts to cause an “indirect prompt injection” attack to cause remote code execution (in this case, trying to invoke an MCP tool to send Lex back the location of your secret base\!).  Now, activate the code (local) filter and try again \- watch it block the attack.  
**Extra credit**: Inspect how MailMate is built \- [https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln\_email\_prompt.txt](https://github.com/virtualsteve-star/chat-playground/blob/main/personalities/vuln_email_prompt.txt) \- see why it’s vulnerable.  Think about the many ways in which you might address this kind of vulnerability to catch it before the last line of defence, “output filters”.

## Lab 4: Simple vs. Smart

### Exercise 4.a: Advanced Moderation

**Skill Level**: 1, 2 for extra credit  
**Prereqs**: OpenAI API Key  
**Directions:** Repeat your activities from Lab 2, but switch between the local Sex/Violence filters and the “AI” version.  Try things like misspellings.  Compare the local and AI versions.  Note the performance changes.  Look for changes when entering your prompts or getting responses.  
**Extra Credit**: Inspect the JavaScript that drives the moderation filter (which is used to create the Sex and Violence filter behaviors). https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/openai\_moderation.js

### Exercise 4.b: Advanced Prompt Injection

**Skill Level**: 1, 2 for extra credit  
**Prereqs**: OpenAI API Key  
**Directions:** Repeat your attempts from Lab 3 to do a prompt injection.  Now turn on local, and see what it blocks.   Then, uncheck "Prompt Injection (Local)" and check the "Prompt Injection (AI)" filter.  Try things like prompt injections that include misspellings and foreign languages.  See how it compares.  
**Extra Credit**: Inspect the prompt that drives the prompt injection filter. https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/prompts/openai\_prompt\_injection.txt  
**Extra, Extra Credit:** Inspect the JavaScript that uses that prompt to create the filter  
https://github.com/virtualsteve-star/chat-playground/blob/main/scripts/filters/openai\_prompt\_injection.js

### Exercise 4.c: Automated Testing

**Skill Level**: 1, 2 for extra, extra credit  
**Prereqs**: OpenAI API Key (you can do part of this without, but you won’t get the full effect).  Feel free to play along, though.  
**Directions:** Let’s see how these work and compare.  It’s one thing to hunt and peck, but having a real evaluation suite is crucial.  Navigate to the playground’s live “Test Suite” ([https://virtualsteve-star.github.io/chat-playground/tests/](https://virtualsteve-star.github.io/chat-playground/tests/)).  Try the PromptInjection, sex and violence test suites.  These may take a few minutes to run (and may also cost a few pennies).  When they complete, they’ll give you a summary that shows speed/performance as well as accuracy.  Note the variations.  
**Extra Credit**: Navigate to the test suite files and see how the various test cases are created and labeled. [https://github.com/virtualsteve-star/chat-playground/tree/main/tests/data](https://github.com/virtualsteve-star/chat-playground/tree/main/tests/data)  
**Extra, Extra Credit**: In your local copy of the repo, add some of your own test cases (and/or remove some of the ones that are there) and rerun the tests\!  See what happens.

## Lab 5: Go Bananas

Everything here is extra credit\!  Everything requires some admin/developer chops.  Dive in if you like\!  These don’t have a lot of structure.  So, it’s more challenging, but that’s part of the fun.  You can do it\!  Review the extensibility docs. [https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md](https://github.com/virtualsteve-star/chat-playground/blob/main/documentation/extensibility.md)

### Exercise 5.a: Create a Blocklist

Look at the sex and violence examples.  Create another topic like “Medical” and try to keep your bot from giving out medical advice.  You might do this in real life to mitigate legal risk.  Add it to the output filters list.

### Exercise 5.b: Create a PII Guardrail

Create a simple, local filter for personally identifiable information (PII) using regular expressions (RegEx).  Look for patterns like phone numbers, social security numbers, etc.  Go nuts\!  Add it to the output filters list and try it out.

### Exercise 5.c: Make a Robust PII Guardrail

Make a much more robust PII using an LLM as the judge.  Use the prompt injection (AI) filter as an example.   Add it to the output filters list and try it out.  
**Extra Credit**: Create a PII test suite that tests the local and robust versions.  Put it in /tests.  Use the Prompt Injection suite as an example.  Look at how the AI version and the LLM-based versions compare.  
**Extra, Extra Credit**: Tune both the simple PII filter and the advanced one and see how good you can make them against your test suite cases.

