---
title: 5 - Manual Review and Dynamic Analysis
author: Riccardo ten Cate
category: Jekyll
layout: post
---

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
