---
title: Ethics and Ownership Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Ethics and Ownership](00%20Overview.md)"
status: active
tags:
  - computerscience/foundations
  - solutions
---

# Ethics and Ownership Key Practice Solutions

This note gives worked solutions for [Ethics and Ownership Key Practice Problems](30%20Key%20Practice%20Problems.md). Each solution shows the full reasoning, so you can find the step where your argument diverged rather than only comparing final answers. Where a question asks you to justify a choice, the marks are in the justification tied to the scenario, not in naming the term alone.

## A. Professional ethics

### Problem 1

**Ethics** is a set of moral principles that guide how a person ought to behave. For a computing professional it supplies the judgement that the law cannot reach on its own, because software and data affect people at scale and the people affected usually cannot inspect the code to protect themselves. Two duties it imposes are:
1. To act in the public interest and avoid harming others, including reporting risks found in a system.
2. To respect privacy, confidentiality, and intellectual property, and to be honest about the limits of a system and about one's own competence.

### Problem 2

- **BCS** is the British Computer Society.
- **IEEE** is the Institute of Electrical and Electronic Engineers.

Three concrete benefits of joining one (using BCS as the example):
1. **A published code of conduct** that the member agrees to follow, covering professional competence, integrity, and the public interest, which gives a principled answer when the law is silent.
2. **Accountability.** Membership binds the professional to a body that the public and employers can complain to, and that can discipline or remove a member who breaches the code.
3. **Continuing professional development and peer support.** The body requires members to keep their skills current and provides a community of peers for advice on hard decisions. Membership also signals competence and trustworthiness.

### Problem 3

Stakeholders: the **company** (meets the launch date, avoids a late penalty), the **driver** (given a wrong route, may lose time, miss a turn, or be sent into a hazardous area), and the **developer** (pressured to ship, but bound by a professional code).

Acting *unethically*, shipping and staying quiet, transfers the cost to drivers in the form of wrong directions, lost time, and possible danger, and later to the company in the form of complaints, reputation damage, and possible legal action if the flaw was known. Acting *ethically* means reporting the weak-GPS flaw in writing, proposing a fix or a fallback (such as warning the driver or disabling rerouting until GPS recovers), and refusing to certify a release known to be faulty. The developer documents the risk so there is evidence they met their professional duty, which is the choice a BCS or IEEE code would back.

The general test: a choice that transfers cost to people who cannot see it is the unethical option.

### Problem 4

Stakeholders: the **company** (a one-off profit), the **broker** (data to target ads), and the **users** (whose private reading habits are exposed and could be used to profile or manipulate them).

Selling the data without informed consent is unethical because it breaks confidentiality and privacy: the data was shared for one purpose, running the social-media service, and is being used for another, advertising brokerage, without the users' knowledge. It is also likely illegal under data-protection law, which requires a lawful basis and transparency. The ethical response is to collect only the data the service needs, secure it, and either refuse the sale or seek explicit, informed opt-in consent, explaining what would be shared, with whom, and for what purpose, and letting users decline without losing the service.

### Problem 5

Acting *legally* means complying with the law, which sets a minimum standard that is slow to change. Acting *ethically* means following moral principles and a professional code, which can demand more than the law and can apply where the law is silent.

A computing action that could be legal but still unethical: a company uses publicly available personal data to build a face-recognition system without people's consent. In some jurisdictions no law clearly forbids it, so it may be legal, yet it is unethical because it breaches privacy and can enable surveillance and profiling, harming people who never agreed and cannot easily opt out.

## B. Copyright and ownership

### Problem 6

**Copyright** is the legal right of the creator of an original work to control how that work is copied, distributed, adapted, and sold. In computing it protects source code, object code, web content, music, images, documentation, databases, and designs: any original expression fixed in a tangible form.

Copyright legislation is *needed* because creative and intellectual work is expensive to produce but cheap to copy. Without protection, anyone could reproduce a program, game, or textbook at near-zero cost, undercut the creator, and remove the incentive to create in the first place. The law restores that incentive by giving the creator the exclusive right to copy and distribute the work, usually for the creator's life plus a number of years, and to license, sell, or defend those rights.

### Problem 7

The *idea* behind a program is the concept or method, for example "a game where birds are fired at pigs". The *expression* is the particular form the creator gave it: the specific source code, artwork, music, and text they actually wrote.

Copyright protects only the **expression**, not the idea. So another developer may lawfully write their own game based on the same general idea, but they may not copy the original code, artwork, or other fixed expression.

### Problem 8

Buying a copy of a commercial graphics program gives the buyer a **licence to use** a copy of the software. It does not transfer the **copyright**, which remains with the creator or publisher. The buyer owns the physical or downloaded copy, not the intellectual property.

The student **is** allowed to: install and run the software on the permitted number of machines, and make one backup copy for personal use (if the licence permits). The student **is not** allowed to: copy the software and give or sell it to others, or modify, reverse-engineer, or resell the code, because those rights belong to the copyright holder.

## C. Software licences

### Problem 9

| Licence | (a) Cost | (b) Freedom to view and modify source | (c) Redistribution |
| --- | --- | --- | --- |
| **FSF** (Free Software Foundation) | Free of charge | Yes; source is open, and users may run, study, modify, and redistribute | Allowed, and modified versions must keep the same free licence (copyleft) |
| **OSI** (Open Source Initiative) | Usually free | Yes; source is open and modifiable | Allowed; derivatives may be kept open or made proprietary, depending on the licence |
| **Shareware** | Free to try, then paid | No; source is closed | Usually limited to the trial terms; not freely redistributable |
| **Commercial** | Paid | No; source is closed | Not permitted; copying or resale is infringement |

The decisive distinction is between **free/open** (FSF, OSI: source is open and modifiable) and **proprietary** (shareware, commercial: source is closed and the user pays).

### Problem 10

- **Similarity.** Both expose the source code and allow users to run, study, modify, and redistribute the software, usually free of charge. In both, the freedom to inspect and adapt the code is the defining feature.
- **Difference.** FSF licences use **copyleft** (for example the GNU GPL): modified versions that are redistributed must keep the same free licence, so freedom is preserved downstream. OSI licences are more **permissive** (for example MIT, Apache): they allow modified code to be made proprietary and closed, so derivatives need not stay open.

### Problem 11

(a) **FSF or OSI.** Both are free of charge and expose the source code, so the charity can read and adapt it, which is the requirement. Either fits; FSF would force any redistributed adaptation to stay free, OSI would allow it to go closed.
(b) **Shareware.** It is distributed free on a time-limited or feature-limited basis so users can try it, and payment unlocks the full version. This matches try-before-you-buy.
(c) **Commercial.** The source stays closed and the buyer pays for a licence to use a copy, which protects the firm's proprietary code. Copying or redistribution is not permitted.
(d) **OSI.** An OSI (permissive, for example MIT or Apache) licence lets the community inspect, audit, and improve the server, and it allows derivatives, including the startup's own product, to be made proprietary. FSF would also open the source but its copyleft would force derivatives to stay free, which conflicts with the startup's wish to make derivatives proprietary.

### Problem 12

Under a permissive **OSI** licence such as MIT, the company **may** modify the library and release the modified version as a closed commercial product, because permissive licences allow derivatives to be made proprietary, provided the company keeps the original licence notice and meets any minimal conditions (such as attribution). This is exactly the freedom OSI licences grant.

If the original library had been **FSF**-licensed under the GNU GPL, the answer **changes**: the GPL's copyleft requires that any redistributed modified version be licensed under the same GPL terms, with source available. So the company could not release the modified version as a closed commercial product. It would have to either keep the modified version internal (not distribute it), or release it under the GPL with open source.

## D. AI impact

### Problem 13

- **Social impact.** Positive: AI improves access to services such as translation, tutoring, and diagnosis. Negative: it can embed and amplify bias from training data, displace jobs, and raise privacy and accountability concerns (who is responsible when an AI makes a harmful decision?).
- **Economic impact.** Positive: AI raises productivity and creates new markets and roles (data science, machine-learning engineering, dataset work). Negative: it automates existing jobs, both manual and cognitive, which can cause unemployment and widen inequality between those who own the technology and those whose labour it replaces.
- **Environmental impact.** Positive: AI can help optimise power grids, transport, and agriculture, and model climate change. Negative: training and running large models consumes large amounts of electricity and water for cooling data centres, producing carbon emissions and straining local resources.

### Problem 14

- **Social impact.** Positive: faster, more consistent decisions widen access to credit for people who might be delayed or refused by a manual process. Negative: if the training data reflects past discrimination, the AI can deny loans unfairly to certain groups, and an automated refusal raises an accountability question, namely who is responsible and how the user can appeal.
- **Economic impact.** Positive: the bank processes applications at lower cost and higher speed, freeing staff for complex cases and creating roles in AI maintenance. Negative: loan-officer jobs may be automated, which can displace staff and concentrate benefit with the bank rather than its workers or customers.

### Problem 15

- **Positive.** Optimised routes reduce the distance driven, the fuel burned, and the vehicle emissions per delivery, which lowers the carbon footprint of the logistics operation and reduces local air pollution.
- **Negative.** Running the AI at scale requires data centres whose training and inference consume significant electricity and water for cooling, producing carbon emissions that partly offset the route savings, and the hardware refresh cycle creates electronic waste.

### Problem 16

Four distinct applications of AI:
1. **Healthcare** - diagnosing disease from medical scans.
2. **Finance** - detecting fraudulent transactions in real time.
3. **Transport** - route optimisation and autonomous vehicles.
4. **Natural language** - machine translation and virtual assistants.

Linked example, healthcare: socially, faster diagnosis can improve patient outcomes and extend expert care to understaffed regions (positive), but biased training data can make diagnoses less accurate for under-represented groups and a misdiagnosis raises an accountability question (negative). Environmentally, training and running the model consumes electricity and water for cooling data centres, producing carbon emissions (negative), though AI can also help optimise hospital resource use and reduce waste (positive).
