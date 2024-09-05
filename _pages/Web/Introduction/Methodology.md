---
title: Security Testing Methodology
author: Riccardo ten Cate
category: Jekyll
layout: post
toc: false
---

## 1. Requirements Traceability Matrix
### Objective
To systematically link each identified feature and its security considerations, ensuring that all potential security issues are accounted for and tested.
### Activities
- **Matrix Creation:** Develop a matrix that traces each feature identified in the first two phases to specific security risks and planned tests. This matrix serves as a master document to ensure completeness in testing and to track progress against security objectives.

---

## 2. Threat Modeling and Attack Surface Mapping
### Objective
To identify potential threats and comprehensively map the attack surface of the application, laying the groundwork for targeted and effective security testing.
### Activities
- **Component Mapping:** Document all components, data flows, and external interactions within the application. This helps in understanding how different parts of the application interact and where sensitive data is processed and stored.
- **Critical Assessment:** Analyze and prioritize the most business-critical parts of the application, assessing potential security risks in these areas. This step is crucial for focusing efforts on protecting parts of the system that would cause the most damage if compromised.
- **Logic Flaws Identification:** Examine the application’s business logic for potential flaws. This involves thinking like an attacker to identify non-obvious vulnerabilities that could be exploited.

---

## 3. Reconnaissance and Preliminary Analysis
### Objective
To delve deeper into the application’s structure and operational environment, refining the areas identified in the threat modeling phase for detailed security testing.

### Activities
- **Code and Route Analysis:** Conduct an in-depth analysis of the application’s code and routing to identify potentially vulnerable endpoints and functions. The aim here is to pinpoint areas in the code that may be easily exploited.
- **Runtime Examination:** Investigate components active during the application's runtime, such as XML parsers, File Upload, or other interesting features. 
- **Test List Formulation:** Based on the initial reconnaissance findings, draft a preliminary list of security tests tailored to the vulnerabilities and risks identified. This list will direct the subsequent, more detailed testing phases. (Add them to the RTM)

---

## 4. Tool-Assisted Vulnerability Identification
### Objective
Automated tools provide a rapid and scalable overview of potential security flaws, effectively identifying low-hanging fruit that might be overlooked in manual reviews, thereby enhancing the testing coverage.
### Activities
- **Static Code Analysis:** Employ tools like Semgrep and SCA to detect vulnerabilities in the codebase. This step automates the detection of common vulnerabilities and coding errors, speeding up the review process.
- **Dynamic Analysis:** Utilize tools like SonarQube to assess the complexity of functions, focusing on those with high cyclomatic and cognitive complexity as they are more prone to errors and security issues.
- **Findings Documentation:** Record all tool-generated findings for subsequent manual review and validation. This ensures that potential vulnerabilities are not only identified but also thoroughly examined and confirmed.

---

## 5. Manual Review and Dynamic Analysis
### Objective
To conduct a meticulous manual review of the code and thorough testing in a running application, particularly focusing on complex areas that automated tools cannot fully analyze, to detect subtle and intricate security issues.
### Activities
- **Review Based on Tool Outputs:** Prioritize manual reviews based on outputs from automated tools, focusing on high-risk and complex areas both in static code and during runtime.
- **Review Based on Recon Outputs:** Aggregate all data and insights from the "Threatmodeling" and "preliminairy analysis" outputs to create a detailed test plan that includes defined attack vectors.
- **Code and Runtime Review for Specific Flaws:** Systematically check the code and observe the application behavior in a live environment for:
  - **Parameter Manipulation:** Ensure all types of parameters are correctly handled, both during data entry and processing within the application.
  - **Unexpected Input:** Assess how the application handles a variety of input types, particularly those it was not explicitly designed to manage, observing responses in real-time to ensure stability and security.
  - **Null Safety:** Examine how the application deals with null parameters in both the code and during runtime interactions to prevent null pointer exceptions and related issues.
  - **Behavioral Logic Flaws Analysis:** Investigate potential flow logic issues in a live environment, such as flow bypass, repeating actions meant to be done once, performing steps out of the intended order, and handling unexpected user behavior, ensuring the application's logical flow remains secure under various conditions.

---