https://tryhackme.com/room/outputhandlingandprivacyrisks<img width="535" height="23" alt="image" src="https://github.com/user-attachments/assets/8d71a111-4115-40ec-b513-2d8ed595a060" />


## **Topic:** Learn how LLMs handle their output and the privacy risks behind it.

# 📚 Study Notes

LLMs can unintentionally leak sensitive data (internal info, user data, system prompts) if attackers craft tricky queries.

Improper output handling occurs when LLM outputs are used without verification, which can introduce vulnerabilities in web pages, scripts, or automated processes since the model can generate arbitrary text or code.

In simplier words: **LLM outputs can be unsafe if used without checking, and might cause problems in websites, scripts, or automated systems.**

Unsafe LLM outputs can cause XSS on websites, server code to run, or dangerous commands to execute.

Developers often trust LLM outputs, but they’re untrusted data—malicious prompts can make the model produce unsafe content if not handled properly.

<details><summary> ❓ What vulnerability refers to situations where a system blindly trusts whatever the LLM generates and uses it without verification, filtering, or sanitisation?</summary>Improper output handling</details>
