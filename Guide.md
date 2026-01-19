# Source Code Review
Trying to secure systems only by finding and fixing vulnerabilities (pentesting) is an unfair fight that defenders are likely to lose. Therefore, we need to integrate proper code review function into the SDLC to produce better code from a security standpoint and a cost-effective software. </br>
## Secure Code Review & How to Introduce It Into Company's S-SDLC
This section discusses the advantages secure code review can bring to a development organization. </br>
**Objectives**: </br>
- Secure code techinques
- How code review compares other techniques for analyzing secure code. </br>
### Why Secure Code Review?
Secure code review is the single-most effective technique to identify security bugs early in the system development life cycle. When used together with manual and automated penetration testing, code review can significantly increase the cost effectivness of an application security verification effort. </br>
### Why Does Code Have Vulnerabilities?
1. Technologies and protocols have increased seriously at a fast rate, and the ability to invent a technology has outstripped the ability to secure it.
2. Busnisses does not spend the appropriate amount of time on security because software is a blackbox and customers are not able to distinguish the bad code from the secure code, which makes vendors unencouraged to spend time on securing code. 
<img width="1525" height="231" alt="image" src="https://github.com/user-attachments/assets/dd3ba653-be8a-4bf1-be8e-7594aa9e82c6" />

### What Is Secure Code Review? 
Code review is the process of identifying security flaws in the application related to its features and design, along with the exact root cause. </br>
To identify security flaws in the code, one should understand: </br>
1. Code of the application
2. External component
3. Configurations </br>
**Code Reviews are a combination of human efforts and a technology support (SAST).**; </br>
**SAST tools are great for coverage and setting a minimum baseline but they miss dynamic data flow or business logic.**  </br>
>[!Note]
>Tools can assess in discovering issues in the code but a human is necessary to verify these issues to be real ones, define whether they are exploitable or not and calculate the risk to the enterprise. Human reviewers are important to fill in the significant blind spots that tools simply don't. </br>

|Code Review | Secure Code Review|
|------------|-------------------|
|standard code review focuses mainly on general code quality and correctness without a security-driven decision process.|Secure code review extends standard code review by explicitly prioritizing security considerations (such as security standards, risk level, reviewer security expertise, and deeper inspection of high-risk code)|

### Level of Secure Code Review
Level of secure code review is determined depending on: </b>
1. Business need of the software
2. Size of development organization that implemented the software
3. Skill of the personnel. </br>

### Key takeaways 
1. Assessing the risk of vulnerabilities identified during white box penetration test is critical because the vulenrability may not be exposed to the attacker and they won't have access to internal code, so the risk is lower.
2. Results of penetration test can be used to target additional areas for code review; It's good practice to look for additional places where that same class of vulnerability is present even if not mentioned in the test. </br>

### Advantages Of Code Review To Development Practices
1. Provides an historical record
2. Verification that the change has been tested
3. Coding education for junior developers
4. Gain familarity with code base
5. Provides pre-warning of integration clashes </br>

### How To Perform Code Review
1. If any security controls are implemented, study them well as they may be fool-proof
2. Source to sink analysis; Determine all possible inputs to the application (source) and how they are being processed by it(sink: could be insecure code patterns)
3. 
**Security is a non-functional requirement that should be built into every application or tool.** </br>

## How To Use The Code Review Guide 
OWASP guide focues on: </br>
1. Guide you on how effort should be structured and executed
2. What are mechanics/techniques of reviewing code for security vulnerabilities </br>

**❎What does not focus on is giving you guide on how to perform source code review**
## Methodology
Code review is a systematic examination of computer source code and reviews are done in many forms and can be accomplished in various phases/stages of each organization S-SDLC. </br>
The following methodology would cover: </br>
1. Informal walkthoughs
2. Formal inspections
3. Tool assisted code reviews </br>

### Factors To Consider When Developing a Code Review Process
Why considering multiple factors because each secure code review is unique to its context. </br>
1. Consider technical/business related factors (deadlines, resources) as these factor decide the most effective way to execute code review.
2. Risks -- we cannot secure applications 100%, therefore, we need to prioritize components and features that must be securely reviewed.
3. Pruposes & contexts -- depending on the purpose and context of the application, the grade of security will vary (payment web applications vs promotional web application)
    1. **Stay reminded of what the business wants to protect**
4. Lines of code -- is an indicator of the amount of work (lines of code to be reviewed). The more lines of code a program contains, the greater the chances that errors are present in the code
5. Programming languages -- the kind of language will determine the type of expected bugs which would help in secure code reviews (e.g., typed safe languages such as Java and C# are not vulnerable to bugs such as buffer overflows, etc.)
6. Resources, Time & Deadlines -- proper resources should be allocated to avoid the risk(analytical skills, efficient time, etc)

### When to Code Review
3 possible phases in SDLC, where code can be reviewed:
1. Pre-commit; before submitting the code to the repo
    1. Disadvantage: slow down checking code in
    2. Advatage: code sumbitted is at the quality that has been stipulated
1.  Post-commit; after sumbitting code
    1. Disadvantage: lesser quality code
    2. Advantage: Dev team won't wait on a gate to pass before they check-in their code
3. When code audits are done
    4. Review code at intervals (i.e. yearly) or when vulenrable code is found
    5. (Review the whole code not only a single submission) </br>
### Assess Risk To Code Modules
To define the risk of a module or piece of code should be based on **solid cost benefit analysis**. </br>
**3 main techniques to establish Risk**:
1. Quantitative -> in terms of money (potenital loss associated with the code)
2. Qualitative -> in terms of quality of code (what level of loss is associated with the modules
3. Delphi -> independantly interview people on losses and level of compormises and let them know the feedback is anon to give honest feedback

**Criteria for establishing the risk profile of a code module:**
1. Ease of expose -- is the code directly exposed to the internet?
2. Value of loss -- how much could be lost if the module has a vulnerability?
3. Regulatory controls -- if a piece of code implements busniess logic that is associated with a standard that must be complied with should be defined as high risk as there might be penalities for non-conformity </br>

**Options for handling risks in a code review** </br>
If a code changes introduces risk to the code, there are 3 options available: </br>
1. Accept
2. Reduce
3. Avoid </br>
In order to perform source code review, the reviewer should understand the business purpose of the app and the critical business impacts and identify the attack surface. </br>

### Basic Items The Reviewer Should Understand About Application Subjected To a Secure Code Review
(Regarding small organizations) </br>
1. **Application features and business rules**
    1. What are concequences of this system failing?
    2. Shall the enterprise be affected in a great way?
2. **Context** -- context is the "Holy Grail" of secure code insepection and risk assessment
3. **Sensitive Data** -- make note of data entities like account numebrs, passwords, etc. to help you in determining the impact if any data loss happend
4. **User roles & access rights**
    1. Attacks targeted for apps that is designed for internal users is different than attacks targeted for apps that is designed for external users (external users can access it) 
5. **Application Type**
    6. Defining the application type helps look for sepcific security flaws regarding that type (web service, browser bases app, mobile app, etc.)
6. **Code** -- langauges used and the issues and features of these langauges from a security prespective
7. **Design**
8. **Company standards and guidelines**
   1. If the company has secure code guideliness document, the reviewer should adhere to it. </br>

### Code Review Discovery 
1. To gather information about the code read design documents, business requirements, functioanl specifications, etc. </br>
2. Understand the desing
3. Analyze threats to the design </br>
### Code Review Checklist

The checklist should cover the most critical security controls and vulnerability areas such as:

- [ ]  Data Validation
- [ ]  Authentication
- [ ]  Authorization
- [ ]  Session Management
- [ ]  Cryptography
- [ ]  Error Handling
- [ ]  Logging
- [ ]  Security Configurations
- [ ]  Network Architecture
### Static Code Analysis

**Automated analysis can be carried on the application through either of the two options:**

1. Static code scanner scripts based on pattern search (in house and opensource)
2. Static code analyzers (commercial and open source)

| Advatages of source code scanners | Disadvantages of code scanners|
|----------------------------|-------------------------------|
|Reduction in minmal effors; Type of vulnerabilities to be scanned remained common across all applications|Business logic flaws remain untouched|
|Find all instances of the vulenrabilities ; Scanners are effective in this|Limited scope -- scanners are desgined for specific frameworks or languages and they search for certain patterns if not found they cannot identify it|
|Source to sink analysis; Help you better understand data flow|Desgin flaws -- since desgin flaws are not specific to code structure, code analyzers fail to identify it by looking at the code|
|Elaborate reporting format|False positives -- code analyzers identify lots of not real issues so manual intervention is required|

static code analyzers fill the gap of not being able to follow data flow/execution.
#### Choosing A Static Analysis Tool
Choosing a static analysis tool can be decided based on the following questions: </br>
1. Does the tool support the programming language?
2. Is there a prefrence between commercial or free tools?
3. What type of analysis being carried out? Is it security? Quality? Static or Dynamic analysis? </br>
Next step requires some work is done because it is quiet objective: test a few tools to see if team is satisfied with it? user experience, reporting, level of false positives, etc. </br>

### Threat Modeling
Threat modeling --> is an in-depth approach for analyzing the security of the application to provide a context and risk analysis of the app. </br>
Threat modeling is benefical when a source code analysis is performed on an existing application, because: </br>
1. **The results of it help in reducing the complexity of the source code analysis by promoting a risk based approach (instead of reviewing all source code with equal focus, we can prioritize the security code review of components whos threat modeling has randked with high risk threats.** </br>

## What a Reviewer Should Look For When Reviewing Techincal Code

# References 
- OWASP Source Code Review Guide 2.0 </br>

