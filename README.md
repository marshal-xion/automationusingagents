# automationusingagents

Automation steps - we will create 3 agents - 1 create tests 2 run cases and report 3 check report and fix any issue in run

Step 1: Tell Copilot Chat to Remember Your 3 Agents

Prompt1

Act as an Agent Orchestrator. From now on, you host three distinct agents inside this chat session. They are optimized to save tokens by using local Playwright CLI commands rather than reading raw HTML code:

- "Agent 1 (Architect)": Focuses on creating modular test case steps.
- "Agent 2 (Runner)": Focuses on providing exact, optimized Playwright CLI commands to execute.
- "Agent 3 (Debugger)": Focuses on reading single-line CLI errors and giving surgical code fixes.

Whenever I ask for a specific agent by name (e.g., "Agent 1, give me..."), switch to that persona completely. Acknowledge this setup by introducing all three agents briefly.


Step 2: Put Agent 1 to Work (Create Test Cases)

Prompt2 
Agent 1: Give me a step-by-step functional checklist to test the login, product page, and checkout on https://saucedemo.com. Keep it short to save tokens.


Step 3: Use Playwright CLI codegen to Save Tokens

npx playwright codegen saucedemo.com
do some case and save the case in a file in tests folder as sauce.spec.js

Step 4: Put Agent 2 to Work (Run & Report)
It will give an efficient command to run the test

Prompt3 

Agent 2: What is the exact CLI command to run my new 'tests/sauce.spec.js' file using the most condensed, single-line text output format?

it will give a command - npx playwright test tests/sauce.spec.js --reporter=line - run this command and it should pass.


Step 5: Put Agent 3 to Work (Fixing Issues)

Make some error in code and run the nex prompt- 


prompt4

Agent 3: My test failed. Here is the single-line error message from the terminal: 
[PASTE JUST THE 1 or 2 LINES OF ERROR HERE]

Here is my test file:
#codebeat:tests/sauce.spec.js 
(Or select the text in your file and type "Look at my selected code")

Fix the selector or timeout using minimal code changes.


