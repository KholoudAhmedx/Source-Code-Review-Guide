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


## How To Use The Code Review Guide 
OWASP guide focues on: </br>
1. Guide you on how effort should be structured and executed
2. What are mechanics/techniques of reviewing code for security vulnerabilities </br>

**❎What does not focus on is giving you guide on how to perform source code review**

## What a Reviewer Should Look For When Reviewing Techincal Code



