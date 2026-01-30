https://tryhackme.com/room/outputhandlingandprivacyrisks<img width="535" height="23" alt="image" src="https://github.com/user-attachments/assets/8d71a111-4115-40ec-b513-2d8ed595a060" />


## **Topic:** Learn how LLMs handle their output and the privacy risks behind it.

# 📚 Study Notes

## LLM Output Risks ##
- LLMs can unintentionally leak sensitive data (internal info, user data, system prompts) if attackers craft tricky queries.
- Risks: Injection (HTML/JS executed downstream), Prompt escalation (hidden instructions affect systems), Data leakage (API keys, tokens, internal info)

## Improper Output Handling (LLM05) ##

- Improper output handling occurs when LLM outputs are used without verification, which can introduce vulnerabilities in web pages, scripts, or automated processes since the model can generate arbitrary text or code.

- In simplier words: **LLM outputs can be unsafe if used without checking, and might cause problems in websites, scripts, or automated systems.**

- Unsafe LLM outputs can cause XSS on websites, server code to run, or dangerous commands to execute.

- Developers often trust LLM outputs, but they’re untrusted data—malicious prompts can make the model produce unsafe content if not handled properly.

<details><summary> ❓ What vulnerability refers to situations where a system blindly trusts whatever the LLM generates and uses it without verification, filtering, or sanitisation?</summary>Improper output handling</details>

## Sensitive Information Disclosure (LLM02) ##

**LLM Sensitive Info Risks**

- LLMs can leak secrets, personal info, or internal instructions.
- Why it’s different: Leaks come from the model’s memory, training data, or context—not code bugs. Attackers just need smart prompts.

**How leaks happen:** 

- Training data: Model may repeat sensitive info it learned.
- Context bleed: Runtime data (user info, prompts) can show up in responses.
- Conversation history: Past sessions may leak to new users.
- System prompts: Hidden instructions can be exposed.

**Common misconceptions:**

- Only inputs matter → Outputs can leak info too.
- Redacting stored data is enough → Model may still hold it in memory.
- Model won’t reveal secrets → It can if prompted cleverly.

⚠️**Why It Matters:** Leaked model info (API keys, URLs, prompts) lets attackers hack or steal data without touching the system.
