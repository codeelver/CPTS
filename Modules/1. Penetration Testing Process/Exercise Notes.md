![[Pasted image 20251227102659.png]]

7 Documents at least for pentest 
|**Document**|**Timing for Creation**|
|---|---|
|`1. Non-Disclosure Agreement` (`NDA`)|`After` Initial Contact|
|`2. Scoping Questionnaire`|`Before` the Pre-Engagement Meeting|
|`3. Scoping Document`|`During` the Pre-Engagement Meeting|
|`4. Penetration Testing Proposal` (`Contract/Scope of Work` (`SoW`))|`During` the Pre-engagement Meeting|
|`5. Rules of Engagement` (`RoE`)|`Before` the Kick-Off Meeting|
|`6. Contractors Agreement` (Physical Assessments)|`Before` the Kick-Off Meeting|
|`7. Reports`|


![[Pasted image 20251118060640.png]]


| **Stage**                     | **Description**                                                                                                                                                                                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `1. Pre-Engagement`           | The first step is to create all the necessary documents in the pre-engagement phase, discuss the assessment objectives, and clarify any questions.                                                                                                                                         |
| `2. Information Gathering`    | Once the pre-engagement activities are complete, we investigate the company's existing website we have been assigned to assess. We identify the technologies in use and learn how the web application functions.                                                                           |
| `3. Vulnerability Assessment` | With this information, we can look for known vulnerabilities and investigate questionable features that may allow for unintended actions.                                                                                                                                                  |
| `4. Exploitation`             | Once we have found potential vulnerabilities, we prepare our exploit code, tools, and environment and test the webserver for these potential vulnerabilities.                                                                                                                              |
| `5. Post-Exploitation`        | Once we have successfully exploited the target, we jump into information gathering and examine the webserver from the inside. If we find sensitive information during this stage, we try to escalate our privileges (depending on the system and configurations).                          |
| `6. Lateral Movement`         | If other servers and hosts in the internal network are in scope, we then try to move through the network and access other hosts and servers using the information we have gathered.                                                                                                        |
| `7. Proof-of-Concept`         | We create a proof-of-concept that proves that these vulnerabilities exist and potentially even automate the individual steps that trigger these vulnerabilities.                                                                                                                           |
| `8. Post-Engagement`          | Finally, the documentation is completed and presented to our client as a formal report deliverable. Afterward, we may hold a report walkthrough meeting to clarify anything about our testing or results and provide any needed support to personnel tasked with remediating our findings. |



Analysis of findings during testing
|**Analysis Type**|**Description**|
|---|---|
|`Descriptive`|Descriptive analysis is essential in any data analysis. On the one hand, it describes a data set based on individual characteristics. It helps to detect possible errors in data collection or outliers in the data set.|
|`Diagnostic`|Diagnostic analysis clarifies conditions' causes, effects, and interactions. Doing so provides insights that are obtained through correlations and interpretation. We must take a backward-looking view, similar to descriptive analysis, with the subtle difference that we try to find reasons for events and developments.|
|`Predictive`|By evaluating historical and current data, predictive analysis creates a predictive model for future probabilities. Based on the results of descriptive and diagnostic analyses, this method of data analysis makes it possible to identify trends, detect deviations from expected values at an early stage, and predict future occurrences as accurately as possible.|
|`Prescriptive`|Prescriptive analytics aims to narrow down what actions to take to eliminate or prevent a future problem or trigger a specific activity or process.|

| **`Evasive`** | **`Hybrid Evasive`** | **`Non-Evasive`** |
| ------------- | -------------------- | ----------------- |
Data regulations and Frameworks

|**Type of Information**|**Security Regulation**|
|---|---|
|Credit Card Account Information|`Payment Card Industry` (`PCI`)|
|Electronic Patient Health Information|`Health Insurance Portability and Accountability Act` (`HIPAA`)|
|Consumers Private Banking Information|`Gramm-Leach-Bliley` (`GLBA`)|
|Government Information|`Federal Information Security Management Act of 2002` (`FISMA`)|

Some frameworks companies may follow include:

|||
|---|---|
|(`NIST`) - National Institute of Standards and Technology|(`CIS Controls`) - Center for Internet Security Controls|
|(`ISO`) - International Organization for Standardization|(`PCI-DSS`) - The Payment Card Industry Data Security Standard|
|(`GDPR`) - General Data Protection Regulation|(`COBIT`) - Control Objectives for Information and Related Technologies|
|(`FedRAMP`) - The Federal Risk and Authorization Management Program|(`ITAR`) - International Traffic in Arms Regulations|
|(`AICPA`) - American Institute of Certified Public Accountants|(`NERC CIP Standards`) - NERC Critical Infrastructure Protection Standards|

Send `DRAFT`report and give the client a chance to review and comment


