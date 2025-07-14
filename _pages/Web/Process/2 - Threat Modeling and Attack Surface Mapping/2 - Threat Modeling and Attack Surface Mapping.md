---
title: 2 - Threat modeling and attack surface mapping
author: Riccardo ten Cate
category: Jekyll
layout: post
---

### Objective
To identify potential threats and comprehensively map the attack surface of the application, laying the groundwork for targeted and effective security testing.
### Activities
- **Component Mapping:** Document all components, data flows, and external interactions within the application. This helps in understanding how different parts of the application interact and where sensitive data is processed and stored.
- **Critical Assessment:** Analyze and prioritize the most business-critical parts of the application, assessing potential security risks in these areas. This step is crucial for focusing efforts on protecting parts of the system that would cause the most damage if compromised.
- **Logic Flaws Identification:** Examine the application’s business logic for potential flaws. This involves thinking like an attacker to identify non-obvious vulnerabilities that could be exploited.

### Framing threat modeling sessions
To structure our threat modeling sessions effectively, we use **Adam Shostack’s four-question framework**. This helps ensure we cover the essentials in a structured, repeatable way that’s easy for developers to follow. You can learn all about it in Adam's youtube series here [The Worlds Shortest Threat Modeling Course](https://www.youtube.com/watch?v=2pvprvsr1lo&list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf).

**1. What are we working on?**  
This question ensures everyone is aligned on the scope and understands the system or feature under review. It involves clarifying functionality, architecture, and data flows, so we all start from the same shared mental model.

**2. What can go wrong?**  
This step drives the identification of potential threats and misuse cases. We explore how an attacker might abuse the system, where data could leak, or where controls might fail. It’s the point where we actively look for STRIDE categories of threats or relevant business-specific risks.

**3. What are we going to do about it?**  
Once we’ve identified possible issues, we discuss mitigations, design changes, or additional controls. This ensures the output is actionable — not just a list of theoretical risks, but clear next steps to improve security posture.

**4. Did we do a good job?**  
Finally, we reflect on the process and the results: did we thoroughly explore the threats, cover the critical paths, and produce concrete outcomes? This closes the loop and gives us a chance to adjust our approach for future sessions.