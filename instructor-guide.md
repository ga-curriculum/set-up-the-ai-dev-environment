# Instructor Guide: Setting Up the AI Development Environment

## Module Overview

In this module, learners configure their workspace for AI web development, connecting APIs, SDKs, and environment variables securely. The focus shifts from theoretical architecture to practical implementation, ensuring students have the necessary tooling (Node.js, GitHub, Postman) to build secure AI applications.

## Learning Objectives

By the end of this session, students will be able to:

* 
**Configure** an AI-ready web development environment by installing Node.js and setting up version control.


* 
**Implement** secure environment management practices using `.env` files to protect API credentials.


* 
**Execute** API authentication to connect to the OpenAI API and test connections using Postman.



## Session Pacing Guide (120 Minutes total)

| Duration | Segment | Instructor Action |
| --- | --- | --- |
| **30 min** | **The AI-Ready Workspace** | Verify installations of Node.js and Git. Explain the role of the runtime (Node.js) in server-side AI requests. |
| **30 min** | **Security & Environment Variables** | Lecture on API Key safety. Demonstrate the `.env` + `.gitignore` workflow live. Use the "Credit Card" analogy. |
| **20 min** | **API Authentication with Postman** | Live demo of generating an OpenAI key and testing it in Postman. Show how to troubleshoot a `401 Unauthorized` error. |
| **40 min** | **Lab: Connecting to the OpenAI API** | Facilitate the lab where students set up their local environment, connect to the OpenAI API, and test authentication.

 |

---

## Delivery Notes & Teaching Tips

### 1. The Workspace (Node.js & GitHub)

* **The "Engine" Analogy:** Explain that while HTML/CSS is the "body" of the car, Node.js is the "engine." We need the engine to securely talk to the gas station (AI Provider).
* **Version Control Check:** Ensure students understand that `git init` should happen at the root of their project. A common mistake is nesting git repositories.

### 2. Security & Environment Variables

* **The "Credit Card" Analogy:** Treat the API Key like a credit card.
* *Hardcoding a key:* Like writing your credit card number on a post-it note and sticking it to a telephone pole (GitHub).
* *Environment Variables:* Like keeping the card in a safe inside your house. Only you (the running application) can open it.


* **Live Demo:** Create a dummy file `secret.js` with a fake key. `git add .` it. Then stop. Ask the class: "If I push this, what happens?" Then show how to fix it with `.gitignore`.

### 3. API Authentication

* **Bearer Tokens:** Explain the term "Bearer." "Whoever *bears* (holds) this token has the right to enter."
* **Postman First:** Emphasize that if it doesn't work in Postman, it won't work in code. This isolates variables.

---

## Lab Guide: Connecting to the OpenAI API

**Lab Objective:** Set up a local environment, connect to the OpenAI API, and test authentication.

### Setup

* 
**Tools Required:** Node.js, GitHub, Postman.


* **Account:** Students need an active OpenAI platform account (or the instructor provides a temporary key for the session).

### Common Student Issues & Solutions

* **Issue:** "My terminal says `node: command not found`."
* *Solution:* They likely installed Node.js but didn't restart their terminal. Have them restart the terminal or VS Code.


* **Issue:** `401 Unauthorized` in Postman.
* *Solution:* Usually a copy-paste error. Check for extra spaces at the start/end of the key. Or, they haven't set up a payment method (if using their own accounts).


* **Issue:** "I accidentally pushed my `.env` file to GitHub."
* *Solution:* **Panic moment (Simulated).** Walk them through the fix: 1. Rotate the key (generate a new one immediately). 2. Add `.env` to `.gitignore`. 3. Remove the file from git cache (`git rm --cached .env`).



### Debrief Questions

At the end of the lab, ask:

1. "Why did we use `dotenv` instead of just typing the key into the variable?"
2. "If you were working on a team, how would you share the `.env` file?" (Answer: You don't. You share a `.env.example` file and they fill in their own keys).

---

## Resources for the Instructor

* **Reference:** [Node.js Official Downloads](https://nodejs.org/en/download/)
* **Reference:** [NPM dotenv Documentation](https://www.npmjs.com/package/dotenv)
* **Troubleshooting:** [OpenAI Error Codes](https://platform.openai.com/docs/guides/error-codes)
* **AI Prompt Bank:**
* *"I am getting a 'Module not found' error in Node.js. What command did I forget to run?"* (Expected answer: `npm install`)
* *"Explain what an Environment Variable is to a non-technical manager."*