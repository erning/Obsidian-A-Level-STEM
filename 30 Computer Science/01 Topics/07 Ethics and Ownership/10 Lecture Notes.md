---
title: Ethics and Ownership Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/07 Ethics and Ownership/00 Overview|Ethics and Ownership]]"
status: active
tags:
  - computerscience/foundations
  - lecture-notes
---

# Ethics and Ownership Lecture Notes

Computing does not just produce code; it acts on people, money and the planet. A programmer's decision about whether to ship a flawed release, copy someone else's work, or deploy an AI system can harm millions, so the syllabus asks you to think as a *professional*, not only as a technician. This note covers the ethics expected of a computing professional, the legislation that protects creative work, the licences that govern software, and the impact of AI on society, the economy and the environment.

## Source Route

- Syllabus **9618 AS Section 7 - Ethics and Ownership**.
- 7.1 Ethics and Ownership: the need for and purpose of ethics as a computing professional; the importance of joining a professional ethical body (**BCS** - British Computer Society, and **IEEE** - Institute of Electrical and Electronic Engineers); the need to act ethically and the impact of acting ethically or unethically for a given situation; the need for copyright legislation; the different types of software licencing (Free Software Foundation, Open Source Initiative, shareware, commercial software) and justifying a choice for a given situation; Artificial Intelligence (AI) - its social, economic and environmental impact and its applications.
- Assessed in **Paper 1**. Note: the *technical* basis of AI is A Level Section 18; here you are responsible only for its **impact and applications**.

## 1. Ethics for the computing professional

**Ethics** is a set of moral principles that guide how a person ought to behave. For a computing professional the need is acute, because software and data affect people at scale: a bug, a data leak or a biased algorithm can cause real harm, and the people affected usually cannot inspect the code to protect themselves. Ethics supplies the judgement that the law (which is slow and minimum-standard) cannot reach on its own.

The *purpose* of professional ethics is therefore to give a principled answer to "what is the right thing to do?" when the law is silent, ambiguous, or simply has not caught up. It frames duties that recur across computing: act in the public interest; respect privacy and confidentiality; be honest about your competence and the limits of a system; avoid harming others; respect intellectual property; and take responsibility for your work and for reporting risks you find.

Two **professional bodies** set and uphold these standards, and joining one matters:

| Body | Full name | Role |
| --- | --- | --- |
| **BCS** | British Computer Society | The UK chartered body for IT; publishes a Code of Conduct covering professional competence, integrity, and the public interest; offers professional registration such as Chartered IT Professional (CITP). |
| **IEEE** | Institute of Electrical and Electronic Engineers | The international body for electrical, electronic and computing engineers; its Code of Ethics commits members to hold paramount the safety, health and welfare of the public. |

**Why joining matters.** Membership is not a decoration; it binds a professional to a published code of conduct, gives them a community of peers for advice on hard decisions, requires continuing professional development so their skills stay current, and gives the public and employers an accountable body to complain to. It also signals competence and trustworthiness, which is itself a protection for the people who depend on the professional's work. In an exam, the marks are for these concrete benefits - a code to follow, accountability, professional development, and public trust - not for "it looks good on a CV".

## 2. Acting ethically vs unethically

The syllabus asks you to reason about the *impact* of acting ethically or unethically in a specific situation. The method is: name the stakeholders, weigh the harms and benefits for each, and check the decision against a professional code. A worked example shows the shape of the reasoning.

*Case: a developer is told to release a payment app a week early, knowing the refund module fails on a slow network.* The stakeholder view:

- The **company** gains a week of revenue and meets a marketing deadline if the app ships now.
- The **customer** whose refund silently fails loses money and loses trust in the product.
- The **developer** is pressured, but their professional code (BCS, IEEE) requires them to hold the public interest paramount and to be honest about the limits of a system.

Acting *unethically* - shipping and staying quiet - delivers a short-term gain for the company but transfers the cost to customers in the form of lost money, and to the company later in refunds, complaints, reputation damage and possible legal action under consumer-protection law. Acting *ethically* - reporting the flaw in writing, proposing a fix or a delayed module, and refusing to certify a release known to be faulty - protects customers, produces defensible evidence that the professional met their duty, and is the choice a professional body's code would back. The general pattern is that unethical choices privatises a quick benefit and socialises a larger harm, while ethical choices internalise the cost now to prevent a bigger loss later.

A second common scenario is *handling user data*: selling or loosely sharing customer data for profit is unethical (and often illegal) because it breaks confidentiality and privacy; the ethical response is to collect only what is needed, secure it, and be transparent about its use. The same reasoning - stakeholders, harms and benefits, code of conduct - applies.

## 3. Copyright legislation

**Copyright** is the legal right of the creator of an original work to control how that work is copied, distributed, adapted and sold. In computing it protects source code, object code, web content, music, images, documentation, databases and designs - essentially any original expression fixed in a tangible form. The *need* for copyright legislation is that creative and intellectual work is expensive to produce but cheap to copy: without protection, anyone could reproduce a program, a game or a textbook at near-zero cost, undercut the creator, and remove the incentive to create in the first place. Copyright law restores that incentive by giving the creator (or their employer, or whoever they assign it to) the exclusive right to copy and distribute the work, usually for the creator's life plus a number of years, and by allowing them to license, sell or defend those rights.

Two points are commonly tested. First, copyright protects the ***expression*** of an idea, not the idea itself - you cannot copyright "a game where birds are fired at pigs", but you can copyright the specific code and artwork you wrote. Second, copyright is **automatic** in most jurisdictions: once an original work is recorded, it is protected; a licence (section 4) is how the owner then *allows* others to use it. Note that buying a copy of software buys you a licence to *use* it, not ownership of the copyright - you do not gain the right to copy, modify or resell the code.

## 4. Software licences

A **software licence** is the legal agreement that states what a user may and may not do with a piece of software. The copyright holder always retains copyright; the licence grants specific permissions. The syllabus names four categories, and you must be able to compare them and justify one for a given situation.

| Licence type | Cost | Freedom to view / modify source | Distribution |
| --- | --- | --- | --- |
| **Free Software Foundation (FSF)** | Free of charge | Yes - source is open, and users are free to run, study, modify and redistribute it; modified versions must stay free under a compatible licence ("copyleft", e.g. GNU GPL) | Allowed, and derivatives must keep the same freedoms |
| **Open Source Initiative (OSI)** | Usually free | Yes - source is open and modifiable; licences are more permissive than FSF and may allow the modified code to be made proprietary (e.g. MIT, Apache) | Allowed; terms on derivatives vary by licence |
| **Shareware** | Free to try, then paid | No - source is closed; user may try a limited or time-limited version and must pay to continue or unlock full features | Usually not redistributable beyond the trial terms |
| **Commercial software** | Paid | No - source is closed; the buyer purchases a licence to *use* a copy, not the software itself | Not permitted; copying or redistribution is infringement |

The decisive distinction is between **free/open** and **proprietary**. FSF and OSI both expose the source code and permit modification; the difference is ideological and contractual - FSF insists that freedom is preserved downstream through copyleft, while OSI accepts more permissive licences that let derivatives become closed. **Shareware** and **commercial** software are proprietary: the source stays closed, and the user pays (shareware after a trial, commercial up front).

*Justifying a choice for a scenario.* Pick the licence whose properties match the requirement, and name the property:

- A school with **no budget** that wants to study and adapt a program uses **FSF/OSI** software, because it is free of charge and the source is available to inspect and modify.
- A company that needs **security auditability and a community of contributors** for its web server chooses **OSI** open source (e.g. an Apache or MIT-licensed server).
- A developer who wants users to **try before they buy** but eventually earn revenue uses **shareware**.
- A business selling a **proprietary product** whose source must stay secret to protect its competitive advantage uses **commercial** software licensing.

## 5. Artificial Intelligence: impact and applications

**Artificial Intelligence (AI)** is the use of computer systems to perform tasks that normally require human intelligence. For this syllabus you cover its **impact** and **applications** only; the technical basis (how AI is built and trained) is A Level Section 18.

### Impact

AI's impact is felt across three areas the syllabus names explicitly.

- **Social impact.** AI changes how people work and live. It can improve access to services (translation, tutoring, diagnosis), but it also displaces jobs, can embed and amplify bias from training data, and raises concerns about privacy (mass surveillance, profiling) and accountability (who is responsible when an AI makes a harmful decision?). The digital divide widens when only some groups can access or understand AI tools.
- **Economic impact.** AI raises productivity and creates new markets and roles (data science, ML engineering, prompt and dataset work), but it also automates existing jobs - both manual and cognitive - which can cause unemployment and widen inequality between those who own the technology and those whose labour it replaces. New legal and economic questions arise over who owns AI-generated work and over liability for AI decisions.
- **Environmental impact.** Training and running large AI models consumes large amounts of electricity and water (for cooling data centres), producing carbon emissions and straining local resources. On the positive side, AI can *help* the environment by optimising power grids, transport and agriculture, and by modelling climate change.

### Applications

Be ready to name concrete applications and what each does:

- **Healthcare** - diagnosing diseases from scans, drug discovery, personalised treatment plans.
- **Finance** - fraud detection, credit scoring, algorithmic trading.
- **Transport** - route optimisation, autonomous vehicles, traffic management.
- **Natural language** - machine translation, virtual assistants, chatbots, accessibility tools.
- **Manufacturing and agriculture** - predictive maintenance, defect detection, crop monitoring.
- **Education** - personalised learning, automated marking.

A good exam answer pairs each application with its relevant impact - for example, "AI in healthcare can improve diagnosis (social benefit) but the training data centre increases energy use (environmental cost), and a misdiagnosis raises accountability questions (social/legal)".

## Worked-Thinking Routine

1. For an *ethics* question, name the stakeholders first, then weigh harms and benefits for each, then check the decision against a professional code (BCS/IEEE).
2. For a *professional body* question, give the full name and the concrete benefits of membership: a published code of conduct, accountability, continuing professional development, peer support, and public trust.
3. For a *copyright* question, state what it protects (original expression fixed in a form), why it is needed (incentive to create), and that the idea itself is not protected, only its expression.
4. For a *licence* question, compare on cost / freedom to modify / distribution, then justify by matching a licence property to the scenario's need.
5. For an *AI* question, split the impact into social, economic and environmental, give at least one positive and one negative point for each, and name a concrete application.

## Common Mistakes

- Answering "why join a body" with "it looks good on a CV". The marks are for a code of conduct, accountability, professional development and public trust.
- Treating FSF and OSI as identical. Both expose source, but FSF uses copyleft to *preserve* freedom downstream, while OSI accepts more permissive licences that can let derivatives go closed.
- Confusing **shareware** (free trial, then pay) with **freeware** (free of charge, not in the syllabus) or with free/open software (free plus open source).
- Saying copyright protects the *idea*. It protects the *expression* of an idea.
- Claiming that buying software transfers copyright. The buyer gets a licence to use, not ownership of the copyright.
- Listing only the benefits of AI. The syllabus wants the *impact*, which includes negative effects on jobs, bias, privacy, accountability and the environment.
- Writing about how AI works (training, neural networks). At AS this section covers impact and applications only; the technical content belongs to A Level Section 18.
- Vague applications ("AI helps medicine"). Name the specific task, e.g. diagnosing disease from scans.

## Quick Self-Check

- Define ethics for a computing professional and give two duties it imposes.
- Name the two professional bodies in the syllabus (full names), and three concrete benefits of joining one.
- For the "ship a flawed app" case, list the stakeholders and the impact of acting ethically vs unethically.
- State what copyright protects, why it is needed, and one thing it does *not* protect.
- Explain why buying a copy of software does not transfer copyright.
- Compare FSF, OSI, shareware and commercial software on cost, freedom to modify source, and distribution.
- Justify a licence choice for each of: a no-budget school that wants to read the code, a developer wanting try-before-you-buy, and a firm protecting a proprietary product.
- Give one positive and one negative point of AI for each of social, economic and environmental impact.
- Name four distinct AI applications and, for one, link it to its social and environmental impact.

## Connections

- [[30 Computer Science/01 Topics/18 Artificial Intelligence/00 Overview|Artificial Intelligence]] (A Level) supplies the technical basis - how AI and machine-learning systems are built and trained - that underlies the impact discussed here.
- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] provides the security measures, access rights and privacy concepts that an ethical professional must respect when handling data.

## Study Sequence

1. Read this note top to bottom, then close it and write your own definitions of ethics, copyright and software licence from memory.
2. Memorise the professional-bodies table and the three concrete benefits of membership until they are automatic.
3. Rehearse the stakeholder method on two ethics scenarios of your own, stating the ethical and unethical choice each time.
4. Drill the four-way licence comparison until you can produce the cost / modify / distribution row for each from a blank page.
5. Practise justifying a licence for an unseen scenario by naming the licence property that matches the need.
6. For AI, prepare a short list of applications and, for each of social, economic and environmental impact, one gain and one cost you could write in an exam.
7. Finish with the syllabus checklist: tick each "need for", "importance of" and "justify" point against what you can now explain without notes.
