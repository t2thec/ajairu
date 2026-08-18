# AI Governance Framework for UK SMEs

A practical, lightweight AI governance framework for UK small and medium enterprises. This is not enterprise bureaucracy. It is the minimum viable governance to use AI responsibly, comply with UK regulations, and build trust with your customers. For AI consultancy support, visit [ajairu.ai](https://ajairu.ai).

## Why you need AI governance

Using AI in your business creates new risks: data protection issues, biased outputs, unreliable results, and compliance gaps. Without basic governance, these risks turn into real problems: regulatory fines, customer harm, wasted money, and reputational damage.

Good governance is not about stopping AI adoption. It is about adopting AI in a way that is safe, compliant, and sustainable. This framework gives you the structure to do that without hiring a Chief AI Officer or writing a 200-page policy.

---

## The six pillars of AI governance for SMEs

### 1. Purpose and scope

Define what AI is used for in your business and what it is not used for.

**What to document:**
- Which processes use AI (or plan to)
- What decisions AI influences or makes
- What decisions AI does NOT make (the boundaries)
- Who is accountable for AI-related decisions

**Questions to answer:**
- Is AI used to make decisions about customers or staff?
- Is AI used to generate content that reaches customers?
- Is AI used internally only, or in customer-facing contexts?

**The principle:** Be clear about where AI is in your business. If you cannot list it, you cannot govern it.

### 2. Data governance

AI runs on data. You need to know what data goes in, where it goes, and whether you are allowed to use it that way.

**What to document:**
- What data is used as input to AI systems
- Whether that data includes personal data (names, emails, customer details)
- Your lawful basis for processing that data under UK GDPR
- Where the AI service processes your data (UK, EEA, US, elsewhere)
- Data retention: how long are AI inputs and outputs kept?
- Who has access to AI systems and the data flowing through them

**Key UK GDPR considerations:**
- **Lawful basis:** You need a valid basis (consent, contract, legitimate interests) for processing personal data through AI
- **Data minimisation:** Only send the data the AI actually needs, not everything
- **International transfers:** If the AI provider processes data outside the UK, you need appropriate safeguards (UK IDTA or Addendum to the EU SCCs)
- **Transparency:** Data subjects should know their data is being processed by AI

**The principle:** Do not feed personal or sensitive data into an AI system unless you know exactly where it goes and you have a lawful basis to do so.

### 3. Model selection and evaluation

Not all AI is the same. Different models have different capabilities, costs, data policies, and risk profiles.

**What to document:**
- Which AI models or services you use (e.g. which LLM, which vision model)
- Why you chose them (capability, cost, data policy, integration ease)
- How you tested them before deployment
- What their known limitations are
- What their data handling policies are (do they train on your data?)

**Evaluation checklist:**
- [ ] Tested with realistic data from your business
- [ ] Tested for bias (does it perform worse for certain groups?)
- [ ] Tested for reliability (how often does it get things wrong?)
- [ ] Reviewed the provider's data policy (do they store your inputs? train on them?)
- [ ] Reviewed the provider's security certifications (SOC 2, ISO 27001)
- [ ] Documented the cost model (per-token, per-request, per-seat)

**The principle:** Choose AI models deliberately, not because someone tried a demo and it seemed cool.

### 4. Human oversight

AI should support decisions, not make unsupervised decisions with significant consequences.

**What to document:**
- Which AI outputs require human review before action
- Who reviews them (named roles, not "someone")
- What the escalation path is when AI output is uncertain or wrong
- How quickly a human can intervene or shut down an AI process

**Levels of human oversight:**

| Level | Description | Example |
|-------|-------------|---------|
| Human decides | AI provides information, human makes the decision | AI suggests a response, staff member sends it |
| Human reviews | AI acts, human reviews before it reaches the customer | AI drafts an email, staff approves before sending |
| Human monitors | AI acts autonomously, human monitors outcomes | AI categorises tickets, human checks the categories periodically |
| No oversight | AI acts fully autonomously | Only acceptable for low-risk, reversible actions |

**The principle:** The higher the stakes, the more human involvement. Decisions about people (customers, staff) should always have human oversight.

### 5. Transparency and communication

People should know when they are interacting with AI and when AI is being used to make decisions about them.

**What to document:**
- Your AI usage policy (what AI is used for, what it is not used for)
- How you inform customers when AI is involved in their experience
- How you inform staff when AI is used in their work
- How you handle subject access requests related to AI processing
- How you respond to questions about AI use from customers or regulators

**Practical steps:**
- Publish a simple AI usage statement on your website
- Tell customers when they are interacting with an AI system (chatbots, automated responses)
- Tell staff what AI tools are in use and what the expectations are
- Keep a record of what AI systems you use so you can answer questions

**The principle:** If your customers or staff would be surprised to learn how AI is used in your business, you need to be more transparent.

### 6. Risk management and incident response

Things will go wrong. AI outputs will be wrong, biased, or inappropriate. Plan for it.

**What to document:**
- What the top risks are for your AI use cases
- How you monitor for those risks
- What happens when something goes wrong (incident response plan)
- How you review and improve after an incident

**Risk categories to consider:**

| Risk | Description | Mitigation |
|------|-------------|------------|
| Inaccuracy | AI produces wrong information | Human review, confidence thresholds, regular testing |
| Bias | AI discriminates against certain groups | Bias testing, diverse test data, human oversight |
| Data breach | Sensitive data exposed through AI use | Data minimisation, access controls, audit logs |
| Reputational | AI output embarrasses or harms the business | Review process, escalation path, quick shutdown capability |
| Compliance | AI use breaches regulations | Legal review, GDPR assessment, documentation |
| Dependency | Business becomes reliant on a single AI provider | Exit strategy, alternative providers, data portability |

**Incident response basics:**
1. Detect (monitoring alerts, user reports, regular checks)
2. Contain (pause the AI process, prevent further impact)
3. Assess (what happened, who is affected, how bad is it)
4. Notify (inform affected parties if required by law or ethics)
5. Fix (root cause, prevent recurrence)
6. Document (what happened, what you did, what you learned)

---

## Getting started: a 30-day plan

### Week 1: Inventory
- List every AI tool and system used in your business
- Identify which ones process personal data
- Note who is responsible for each one

### Week 2: Assess
- For each AI use case, rate the risk level (low, medium, high)
- Identify the highest-risk use cases
- Check data handling policies for your AI providers

### Week 3: Document
- Write a one-page AI usage policy (use this framework as a template)
- Document the human oversight level for each use case
- Create an incident response checklist

### Week 4: Communicate
- Share the policy with your team
- Update customer-facing communications if needed
- Set a date for the first review (every 6 months minimum)

---

## AI usage policy template

Below is a minimal template you can adapt for your business.

---

**[Your Company Name] AI Usage Policy**

**Last updated:** [Date]

**Purpose:** This policy describes how [Company Name] uses AI in its operations.

**Scope:** This policy covers all AI tools and systems used by [Company Name] and its staff.

**AI use in our business:**
- [List specific use cases, e.g. "We use AI to assist with drafting customer support responses"]

**Our principles:**
1. AI supports human decisions, it does not replace them for anything significant
2. We do not feed personal data into AI systems without a lawful basis
3. We review AI outputs before they reach customers
4. We are transparent about our AI use with customers and staff
5. We monitor AI performance and stop using tools that do not meet our standards

**Data protection:**
- We comply with UK GDPR in all AI-related data processing
- We only share personal data with AI providers who have adequate data protection measures
- We retain AI-related data only as long as necessary

**Responsibility:**
- [Name/Role] is responsible for AI governance at [Company Name]
- All staff using AI tools must follow this policy
- Concerns about AI use should be reported to [Name/Role]

**Review:** This policy is reviewed every 6 months.

---

## Resources

- [ICO guidance on AI and data protection](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/) - the UK regulator's official guidance
- [AI Readiness Checklist](ai-readiness-checklist.md) - assess whether your business is ready for AI
- [ajairu.ai](https://ajairu.ai) - hands-on AI consultancy support for UK SMEs

## Disclaimer

This framework is provided as general guidance, not legal advice. UK GDPR and AI regulation are evolving areas. For compliance advice specific to your business, consult a qualified legal professional or contact [ajairu.ai](https://ajairu.ai) for practical governance support.