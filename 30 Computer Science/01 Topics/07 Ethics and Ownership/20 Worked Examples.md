---
title: Ethics and Ownership Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/07 Ethics and Ownership/00 Overview|Ethics and Ownership]]"
status: active
tags:
  - computerscience/foundations
  - worked-examples
---

# Ethics and Ownership Worked Examples

Ethics, copyright, and licensing decisions are about people and consequences, not just rules. The worked examples below model the reasoning the syllabus rewards: name the stakeholders and harms before judging an action; give the concrete benefits of a professional body rather than vague prestige; apply copyright to what it actually protects (the expression of an idea); compare software licences on cost, freedom to modify the source, and redistribution; and split AI impact into social, economic, and environmental before reaching a verdict. Cover each solution, attempt the prompt on paper, then compare.

## Source Route

- Syllabus **9618 AS Section 7 - Ethics and Ownership**.
- 7.1 Ethics and Ownership: ethics as a computing professional; professional bodies (**BCS** - British Computer Society, and **IEEE** - Institute of Electrical and Electronic Engineers); acting ethically versus unethically and its impact; copyright legislation; software licences (Free Software Foundation, Open Source Initiative, shareware, commercial); Artificial Intelligence and its social, economic, and environmental impact and applications.
- Assessed in **Paper 1**. The technical basis of AI is A Level Section 18; here only impact and applications are in scope.

The recurring skill is to justify a choice against the scenario, not to recite definitions. The marks are in the reasoning tied to stakeholders, licence properties, or impact categories.

## Example 1: Reason about an ethical dilemma using stakeholders and harms

**Prompt.** A developer is told to release a payment app one week early, knowing that the refund module fails silently when the network is slow. Use stakeholders and harms to weigh acting ethically against acting unethically, and state what an ethical professional should do.

**Solution.** Name the stakeholders first, then weigh the benefit and harm for each.

- **The company** gains a week of revenue and meets a marketing deadline if the app ships now. This is the short-term benefit that tempts the unethical choice.
- **The customer** whose refund silently fails loses real money and loses trust in the product. The harm falls on someone who cannot inspect the code to protect themselves.
- **The developer** is pressured, but their professional code (BCS or IEEE) requires them to hold the public interest paramount and to be honest about the limits of a system.

Acting *unethically*, shipping and staying quiet, privatises a quick benefit for the company and socialises a larger harm: customers lose money, and the company later faces refunds, complaints, reputation damage, and possible legal action under consumer-protection law. Acting *ethically* means reporting the flaw in writing, proposing a fix or a delayed module, and refusing to certify a release known to be faulty. This protects customers, produces defensible evidence that the professional met their duty, and is the choice a professional body's code would back.

**Check.** The general test is: does the decision transfer cost to people who cannot see it? If yes, it is the unethical option. An ethical professional documents the risk, offers a remedy, and refuses to sign off a faulty release.

## Example 2: Handling user data ethically

**Prompt.** A fitness-app company is offered money by an insurer for the raw health data of its users. Explain why selling the data without informed consent is unethical, and describe the ethical response.

**Solution.** Stakeholders: the company (a one-off payment), the insurer (data to price premiums), and the users (whose health data is confidential and could raise their insurance cost or expose private conditions).

Selling the data without informed consent is unethical because it breaks confidentiality and privacy. The users shared their data for one purpose, the fitness service, and it is being used for another, insurance underwriting, without their knowledge. It is also likely illegal under data-protection law, which requires a lawful basis and transparency. The ethical response is to collect only the data the service needs, secure it, and either refuse the sale or seek explicit, informed opt-in consent from users, explaining what would be shared, with whom, and for what purpose, and letting them decline without losing the app.

**Check.** Apply the purpose-and-consent test: was the data collected for this use, and has the user meaningfully agreed? If either answer is no, the use is unethical.

## Example 3: Why joining a professional body matters

**Prompt.** State the full names of BCS and IEEE, and give three concrete benefits to a computing professional of joining one of them.

**Solution.**
- **BCS** is the British Computer Society, the UK chartered body for IT.
- **IEEE** is the Institute of Electrical and Electronic Engineers, the international body for electrical, electronic, and computing engineers.

Three concrete benefits of joining (using BCS as the example):
1. **A published code of conduct** that the member agrees to follow, covering professional competence, integrity, and the public interest. It gives a principled answer to "what is the right thing to do?" when the law is silent.
2. **Accountability.** Membership binds the professional to a body that the public and employers can complain to, and that can discipline or remove a member who breaches the code. This protects the people who depend on their work.
3. **Continuing professional development and peer support.** The body requires members to keep their skills current and provides a community of peers for advice on hard decisions. Membership also signals competence and trustworthiness to employers and clients.

**Check.** Avoid "it looks good on a CV". The marks are for a code to follow, accountability, professional development, peer support, and public trust.

## Example 4: Apply copyright to a scenario

**Prompt.** A student writes an original mobile game and posts the code and artwork online. A company copies the code, rebrands it, and sells it without permission. Explain what copyright protects here, why the protection is needed, and what the student can argue.

**Solution.** Copyright protects the original **expression** of an idea once it is fixed in a tangible form, which here means the specific source code and the artwork the student wrote and drew. It does not protect the underlying idea, a game of a certain genre, only the particular expression of it. The protection is automatic in most jurisdictions once the work is recorded, so the student does not have to register it to own it.

The protection is *needed* because creative work is expensive to produce but cheap to copy. Without it, anyone could reproduce the game at near-zero cost, undercut the creator, and remove the incentive to create. That is exactly what happened here.

The student can argue that the company reproduced and distributed copyrighted code and artwork without a licence, which is infringement, and can require the company to stop, remove the copies, and pay damages. The student may have granted a licence by posting the code online, so the precise terms of that licence matter, but unless those terms allowed commercial resale, the copying is not permitted.

**Check.** Two traps: copyright protects expression, not the idea; and posting work online does not abandon copyright, it remains with the creator unless a licence says otherwise.

## Example 5: Choose a software licence for a named project and justify

**Prompt.** For each project, choose the most appropriate licence type from FSF, OSI, shareware, and commercial, and justify by naming the licence property that matches the need.
(a) A school programming club with no budget wants to read, study, and adapt the source of a drawing tool.
(b) A solo developer wants users to try a utility for 30 days and then pay to unlock the full version.
(c) A company is building a proprietary game engine whose source code must stay secret to protect its competitive advantage.

**Solution.**
(a) **FSF or OSI (free or open source).** Both are free of charge and expose the source code, so the club can read, study, and adapt it, which is exactly the requirement. (FSF adds copyleft; OSI is more permissive. Either fits the stated need.)
(b) **Shareware.** It is distributed free on a time-limited or feature-limited basis so users can try it, and payment unlocks the full version. This matches the try-before-you-buy requirement.
(c) **Commercial.** The source stays closed and the buyer pays for a licence to use a copy, which protects the company's proprietary code and competitive advantage. Copying or redistribution is not permitted.

**Check.** Match the licence property to the need: free plus open source for study and adaptation; free trial then pay for try-before-you-buy; closed source plus payment for a protected proprietary product.

## Example 6: Compare FSF and OSI

**Prompt.** Explain one similarity and one difference between Free Software Foundation (FSF) and Open Source Initiative (OSI) licences.

**Solution.**
- **Similarity.** Both expose the source code and allow users to run, study, modify, and redistribute the software, usually free of charge. In both, the freedom to inspect and adapt the code is the defining feature.
- **Difference.** FSF licences use **copyleft** (for example the GNU GPL): if a user modifies and redistributes the software, the modified version must keep the same free licence, so freedom is preserved downstream. OSI licences are more **permissive** (for example MIT, Apache): they allow the modified code to be made proprietary and closed, so derivatives need not stay open.

The distinction is ideological and contractual, not technical. FSF treats software freedom as a value to be enforced; OSI treats open source as a practical development model.

**Check.** Do not say they are identical. Both open the source; FSF forces derivatives to stay free, OSI allows derivatives to go closed.

## Example 7: Discuss AI impact for an application

**Prompt.** A hospital deploys an AI system that diagnoses disease from X-ray scans. Discuss the social, economic, and environmental impact of this application, giving at least one positive and one negative point for each.

**Solution.**
- **Social impact.** Positive: faster and more consistent diagnosis can improve patient outcomes and extend expert-level care to understaffed regions. Negative: if the training data is biased, for example under-representing some groups, diagnoses may be less accurate for those groups; and a misdiagnosis raises an accountability question, namely who is responsible, the AI or the clinician.
- **Economic impact.** Positive: higher productivity and lower cost per diagnosis free clinician time and create new roles in data science and AI maintenance. Negative: some routine diagnostic work may be automated, which can displace staff and widen inequality between those who own the technology and those whose labour it replaces.
- **Environmental impact.** Positive: AI can help optimise hospital scheduling and resource use, reducing waste. Negative: training and running a large model consumes significant electricity and water for cooling data centres, producing carbon emissions that scale with use.

A paired application-and-impact statement would be: AI diagnosis can improve care (social benefit) but its data centres increase energy use (environmental cost), and a harmful error raises an accountability question (social and legal).

**Check.** The syllabus wants *impact*, which includes negatives. Cover all three categories, and for each give at least one gain and one cost, paired with the specific application. Do not write about how the AI is trained; that is A Level Section 18.

## Study Routine

1. For an ethics question, name the stakeholders first, weigh harms and benefits for each, then check the decision against a professional code (BCS or IEEE).
2. For a professional-body question, give the full name and the concrete benefits: a code of conduct, accountability, continuing professional development, peer support, and public trust.
3. For a copyright question, state what it protects (original expression fixed in a form), why it is needed (incentive to create), and that the idea itself is not protected, only its expression.
4. For a licence question, compare on cost, freedom to modify the source, and redistribution, then justify by naming the licence property that matches the scenario's need.
5. For an AI question, split the impact into social, economic, and environmental, give at least one positive and one negative point for each, and pair each impact with a concrete application.
