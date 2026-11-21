# Emerging AI Roles: What They Do and the Skills You Need

**A practical map of 13 role families, two technical specializations, and the AI Generalist label—across engineering, marketing, creative work, and organizational adoption.**

[فارسی](emerging-ai-roles.fa.md) · [Repository home](../README.md) · [Source notes](../resources/ai-roles-sources.md) · [AI Full Stack guide](ai-full-stack.en.md)

**Evidence reviewed:** November 21, 2026. **Audience:** people choosing an AI career direction, professionals adding AI to an existing specialty, and teams defining responsibilities.

AI creates new work in several ways. Someone must build the application, connect its tools, test its behavior, operate it, and help people use it. Elsewhere, marketing, creative production, and business operations acquire new technical responsibilities. These changes do not produce one universal job called “the person who does everything with AI.”

This guide covers the roles discussed in that landscape. It distinguishes **observed job titles**, **specializations**, and **descriptive labels**. An employer posting supports the existence of a particular responsibility bundle; it does not establish the title's invention date, market size, or universal definition. Some examples are visible through indexed employer-page excerpts rather than a readable live application page. We do not present every example as a confirmed open vacancy; see the [evidence notes](../resources/ai-roles-sources.md).

**How to read the skills:** the lists below are an editorial competency guide, not copied qualification lists or requirements shared by every employer. “Core” means a useful baseline for the scope described here. “Extend” means knowledge to add when the work demands it. Portfolio exercises are original suggestions, not completed experiments or employment guarantees.

## Contents

- [The complete role map](#role-map)
- [Shared foundations](#foundations)
- [Building products and systems: roles 1–5](#engineering)
- [Marketing, growth, and creative work: roles 6–9](#growth)
- [Deployment, adoption, governance, and data: roles 10–13](#organizations)
- [Context engineering, LLMOps, and AI Generalist](#specializations)
- [Choosing a direction and demonstrating competence](#direction)

<a id="role-map"></a>
## The complete role map

| # | Role family or label | Main ownership | How to interpret it |
|---|---|---|---|
| 1 | AI Product Engineer / Full Stack AI Engineer | A usable AI product across application layers | Product/software engineering expanded around AI |
| 2 | Agent Engineer | Tool-using, multi-step AI systems | Specialization in agentic software |
| 3 | AI Automation Engineer | AI-enabled business workflows | Automation/integration engineering with AI |
| 4 | Prompt Engineer | Instructions and tested model behavior | A documented specialty; may be a role or part of another job |
| 5 | AI Evaluation Engineer | Evidence of capability, quality, and failure | Evaluation/testing specialization for AI |
| 6 | AI Growth Engineer | Acquisition, activation, and commercial experiments | Growth engineering combined with AI |
| 7 | GTM Engineer | Connected marketing and sales systems | Technical go-to-market work; AI use varies |
| 8 | GEO / AI Search Specialist | Brand discoverability in AI answers/search | Search specialization extending SEO |
| 9 | AI Creative Strategist | AI-assisted creative strategy and iteration | Creative/marketing work with new production capabilities |
| 10 | AI Deployment Engineer / AI-focused FDE | Customer-specific AI delivery | Customer engineering applied to AI; FDE predates this wave |
| 11 | AI Enablement Engineer / Lead | Effective organizational adoption | A family spanning technical building and enablement |
| 12 | AI Governance Specialist | Accountability, oversight, and risk controls | Governance/risk specialization focused on AI |
| 13 | Human Data Engineer | Systems for human feedback and model-improvement data | Software/data engineering supporting AI research |
| 14 | Context Engineering | Information available to a model at each step | Technical discipline; not necessarily a standalone job |
| 15 | LLMOps | Deployment and operation of LLM systems | Operational discipline; titles and team boundaries vary |
| 16 | AI Generalist | Breadth across several AI applications | Descriptive label requiring a concrete scope |

This is a practical classification, not a statistical ranking of job demand. Many roles overlap; title alone does not tell you seniority, coding depth, or business ownership.

<a id="foundations"></a>
## Shared foundations

Whatever the direction, learn to define a task, assess outputs, handle data responsibly, and explain results. Specifically:

- **AI literacy:** tokens, context, probabilistic outputs, retrieval, tool use, and common failure modes. Know when ordinary software is sufficient.
- **Domain knowledge:** understand the actual workflow, vocabulary, users, constraints, and consequences of error.
- **Measurement:** choose a baseline, define success, record failures, and compare alternatives fairly. A persuasive demo is not a quality measurement.
- **Data judgment:** verify provenance and access rights; minimize sensitive information; inspect generated claims and artifacts.
- **Communication:** turn an ambiguous request into a scoped deliverable and explain uncertainty and tradeoffs.

Engineering tracks additionally need programming, APIs, Git, testing, databases, authentication/authorization, and deployment. Creative and enablement tracks can start with less code, but still require technical literacy. Neither “all AI jobs require deep learning research” nor “AI jobs require no technical knowledge” is a useful rule.

For study material, use [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development), [Google's ML Crash Course](https://developers.google.com/machine-learning/crash-course), and the [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter1/1). Treat them as resources for relevant gaps, not a requirement to finish everything before starting.

<a id="engineering"></a>
## Building products and systems

### 1. AI Product Engineer / Full Stack AI Engineer

**Owns:** turning a user problem into an application with working UI, services, data, model behavior, and release practices. “AI Product Engineer” and “Full Stack AI Engineer” overlap, but are not guaranteed synonyms. Rollout's product-engineering description illustrates work spanning an application, an AI pipeline, and an agent. [Employer example](https://jobs.ashbyhq.com/rollout/ec01b62a-b185-4104-a87a-8b0592510257).

**Core skills:**

- Build a usable interface and backend in an appropriate stack; understand HTTP, APIs, SQL, and Git.
- Implement identity, permissions, validation, automated tests, and deployment.
- Integrate model APIs, manage prompts/context, and handle structured outputs and failures.
- Build retrieval or tool use when the task needs them; evaluate quality alongside latency and cost.
- Make product decisions from user evidence and provide correction/error flows.

**Extend:** distributed systems, multimodal input, model adaptation, or inference infrastructure as needed.

**Prove it:** deliver a document assistant with citations, access checks, a deployed interface, and a reproducible evaluation report. Use the [full-stack roadmap](ai-full-stack.en.md) for a deeper path.

### 2. Agent Engineer

**Owns:** systems in which a model chooses actions, uses tools, and works over several steps. Jeevy's example includes agents for fabrication estimating and production monitoring. [Employer example](https://jobs.ashbyhq.com/jeevyfabrication/1ee1537e-8443-483e-a9b0-fb12386827b9).

**Core skills:**

- Python or TypeScript, API integration, and explicit workflow/state design.
- Tool schemas, context assembly, retrieval, and state persistence.
- Authorization outside the model, approval gates, and safe handling of tool results.
- Time/step/spend limits, bounded retries, and protection against duplicate side effects.
- Evaluate both the final environment state and the path taken; debug traces.

**Extend:** MCP integration, long-running tasks, sandboxed execution, and multi-agent coordination when justified.

**Prove it:** build a support agent that retrieves evidence and drafts a ticket update, with writes bound to user approval. Demonstrate denied access, timeout, and retry behavior. Compare it with an explicit workflow before claiming an agent is better. [Architectural background](https://www.anthropic.com/research/building-effective-agents).

### 3. AI Automation Engineer

**Owns:** reducing manual work by connecting business systems, automation platforms, and AI. Myriad360's description includes internal applications, agents, APIs, webhooks, testing, and monitoring. [Employer example](https://job-boards.greenhouse.io/myriad360/jobs/8930382002).

**Core skills:**

- Map a process, its exceptions, owners, inputs, and expected outputs.
- Use APIs, webhooks, JSON, basic SQL, and scripting to connect systems.
- Work competently with a relevant automation platform, such as Power Automate, Zapier, or n8n; the brand is secondary to understanding execution.
- Use models for appropriate tasks such as classification/extraction, with validation.
- Handle duplicates, retries, logs, credentials, access restrictions, and user acceptance testing.

**Extend:** queues, event-driven architectures, orchestration, and deeper application development.

**Prove it:** turn an incoming request into a validated CRM record and a proposed reply. Measure manual effort and failure cases; do not merely show the happy path.

### 4. Prompt Engineer

**Owns:** designing and testing instructions, examples, and response contracts that produce useful model behavior. Anthropic has documented this specialty through its practitioners. This evidence does not imply that prompting is always a separate position. [First-party discussion](https://www.youtube.com/watch?v=T9aRN5JkmL8).

**Core skills:**

- Clear task specification, structured instructions, examples, and output schemas.
- Understand context limits, model variability, refusals, and unsupported claims.
- Create test cases and rubrics; compare prompt versions against a baseline.
- Apply domain knowledge and analyze recurring failures rather than collecting “magic phrases.”
- Maintain versioned prompts and document changes; use basic scripting for repeatable tests where practical.

**Extend:** tool-use design, retrieval, multilingual evaluation, and behavioral safety.

**Prove it:** publish a versioned extraction or classification prompt with shareable test cases and an error analysis. Separate schema-valid responses from factually correct responses. [Structured-output limitations](https://developers.openai.com/api/docs/guides/structured-outputs).

### 5. AI Evaluation Engineer

**Owns:** developing tests and infrastructure that reveal whether AI systems meet defined objectives. Anthropic's Cyber Evaluations Engineer is a specialist example; cybersecurity experience is specific to that variant, not every evaluation role. [Employer example](https://job-boards.greenhouse.io/anthropic/jobs/5406367008-24).

**Core skills:**

- Python, evaluation runners, data handling, and reproducible experiment configuration.
- Curate representative datasets with development/test separation and clear labels.
- Define task-level metrics, grading rubrics, and regression tests.
- Understand sampling, variation, uncertainty, bias, and limitations of small datasets.
- Combine deterministic checks, human assessment, and calibrated model judges; investigate disagreements.

**Extend:** adversarial testing, domain-specific safety, benchmark design, and statistical experimental design.

**Prove it:** compare two configurations on a documented dataset, report category-level failures and uncertainty, and verify actual tool outcomes rather than trusting an agent's success message. [Evaluation guidance](https://www.anthropic.com/research/demystifying-evals-for-ai-agents).

<a id="growth"></a>
## Marketing, growth, and creative work

### 6. AI Growth Engineer

**Owns:** building and testing AI-enabled acquisition and growth systems. Telnyx's posting separates AI growth, conversion, and distribution missions, illustrating that even one family can contain different jobs. [Employer example](https://job-boards.greenhouse.io/telnyx54/jobs/8207203003).

**Core skills:**

- Understand customer segments, acquisition channels, activation, retention, and revenue metrics.
- SQL or equivalent analysis, event instrumentation, and experiment design.
- Build landing pages, demos, scripts, or integrations using appropriate web/API skills.
- Use AI for research, personalization, and workflow building with quality checks.
- Interpret attribution limits, cohort behavior, and the difference between activity and commercial results.

**Extend:** product-led growth, lifecycle systems, advanced experimentation, and channel expertise.

**Prove it:** create an instrumented landing-page/onboarding experiment with clear conversion definitions. Separate actual findings from hypotheses; simulated traffic is not customer acquisition evidence.

### 7. GTM Engineer

**Owns:** the technical connections that make go-to-market processes work across marketing and sales. Clay's marketing variant includes lead/account data, qualification, routing, and measurement. [Employer example](https://jobs.ashbyhq.com/claylabs/9f8067d1-61cf-42cd-aad7-0ac54de8b345).

**Core skills:**

- Understand CRM objects, lead/account lifecycles, sales handoffs, and marketing operations.
- Integrate APIs/webhooks, transform data, and maintain identity/deduplication rules.
- Design scoring, enrichment, routing, and follow-up workflows.
- Use AI research/classification while checking source quality and data permissions.
- Measure funnel movement and maintain reliable, auditable systems.

**Extend:** SQL/Python/JavaScript, warehouse integrations, attribution, lifecycle marketing, and deliverability.

**Prove it:** build a synthetic-data pipeline from inbound inquiry to enriched record, qualification, and assigned follow-up. Document routing exceptions and auditability. GTM engineering can be highly technical, but does not automatically include owning the customer-facing product.

### 8. GEO / AI Search Specialist

**Owns:** understanding and improving how a brand is discovered or represented in AI search and answers. Harvey's SEO/GEO role combines traditional search and AI-answer visibility. GEO means **Generative Engine Optimization**. AEO means **Answer Engine Optimization**; usage overlaps across employers. [Employer example](https://jobs.ashbyhq.com/Harvey/26eb4ce2-0904-412d-a6b4-ce0cabf1fda5).

**Core skills:**

- Technical SEO: crawling, indexing, page rendering, structured data, and site information architecture.
- Understand audience questions, content quality, source credibility, and clear answer structure.
- Design repeatable query samples and track mentions, citations, referrals, and downstream outcomes.
- Know that answers vary by system, time, language, and user context.
- Collaborate with content, communications, web, and analytics teams.

**Extend:** scripting for monitoring, entity analysis, content experimentation, and analytics engineering.

**Prove it:** audit a public site, propose evidence-based improvements, and record before/after observations with query set, dates, and conditions. Do not promise placement or claim that a mention caused sales without evidence.

### 9. AI Creative Strategist

**Owns:** connecting audience insight and creative ideas to AI-assisted production and iteration. Gamma's example links creative production with advertising performance feedback. [Employer example](https://jobs.ashbyhq.com/gamma/ec461546-f994-46ec-a4b1-659dce3e4703).

**Core skills:**

- Audience research, positioning, copywriting, hooks, storyboarding, and creative briefs.
- Visual judgment: composition, typography, brand consistency, and editing.
- Use relevant image/video/audio generation tools and finish assets for the actual channel.
- Inspect factual claims, visual artifacts, usage rights, and suitability for the intended audience.
- Read creative-test results and propose the next iteration from evidence.

**Extend:** motion design, compositing, creative automation, and deeper performance-marketing analysis.

**Prove it:** create a small campaign pack with several variants, a consistent brand brief, an explanation of creative choices, and a test plan. Production quality and strategic reasoning matter together; generated asset volume alone is not a result.

<a id="organizations"></a>
## Deployment, adoption, governance, and data

### 10. AI Deployment Engineer / AI-focused Forward Deployed Engineer

**Owns:** delivering AI solutions in a customer's environment and working through real integration constraints. OpenAI describes FDE work as turning research advances into production systems with customers. FDE is an older role family applied here to AI, and should not be described as invented by generative AI. [Employer example](https://openai.com/careers/forward-deployed-engineer-%28fde%29-nyc-new-york-city/).

**Core skills:**

- Discover workflows with users and translate requirements into a feasible architecture.
- Build applications/integrations; understand customer databases, identity, APIs, and cloud services.
- Prototype quickly, then harden access, evaluation, deployment, and operational behavior.
- Communicate with technical and business stakeholders; document decisions and tradeoffs.
- Define adoption and business-success criteria and hand over a maintainable system.

**Extend:** industry knowledge, enterprise architecture, and specialized security/infrastructure requirements.

**Prove it:** build a permitted or simulated customer integration with a discovery brief, architecture, evaluation, deployment guide, and handover plan. Label simulated components clearly.

### 11. AI Enablement Engineer / Lead

**Owns:** making AI useful in an organization's work. The title family ranges from hands-on engineering to training and change management. ASG's engineer variant includes workflow redesign and implementation; do not assume every enablement lead has the same coding responsibilities. [Employer example](https://job-boards.greenhouse.io/asg/jobs/8716127002).

**Core skills:**

- Identify valuable use cases and diagnose existing process bottlenecks.
- Understand AI capabilities, limitations, access/data boundaries, and suitable review steps.
- Facilitate workshops, teach practical workflows, and produce usable documentation.
- Plan pilots with owners, support channels, and measures of successful adoption.
- Evaluate whether use improves task outcomes, not merely whether employees opened a tool.

**Extend:** technical variants need APIs, automation, prototyping, deployment, and monitoring; training-focused variants need deeper instructional design and organizational-change skills.

**Prove it:** develop a pilot package for one team: workflow, training exercise, usage guidance, feedback mechanism, and an outcome-measurement plan. Demonstrate that a user can complete the task independently.

### 12. AI Governance Specialist

**Owns:** organizing accountability and oversight for AI use. State Street's example concerns governance and responsible adoption. This work builds on risk, governance, privacy, and compliance disciplines; it is not simply writing a policy document. [Employer example](https://statestreet.wd1.myworkdayjobs.com/en-US/Global/job/AI-Governance-Specialist--Officer_R-794571-1).

**Core skills:**

- Maintain an AI-use inventory with owners, intended uses, affected users, and review status.
- Understand model/data lifecycles, third-party services, and the difference between technical evidence and assurance claims.
- Coordinate risk/impact assessments, control evidence, and escalation paths.
- Communicate with engineering, security, legal, privacy, procurement, and business teams.
- Establish monitoring and review triggers when use, data, or system behavior changes.

**Extend:** sector-specific governance and applicable legal requirements with qualified specialists; audit and vendor-risk experience.

**Prove it:** create a governance package for a hypothetical assistant: inventory entry, risk assessment, responsibility map, control evidence, and review schedule. NIST AI 600-1 is a voluntary risk resource, not a certification. [NIST](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

### 13. Human Data Engineer

**Owns:** software and data systems for collecting human feedback and producing useful training/evaluation signals. OpenAI's example is specifically a software-engineering role supporting Human Data. It should not be confused with every annotator or expert-contributor position. [Employer example](https://openai.com/careers/software-engineer-research-human-data-san-francisco/).

**Core skills:**

- Build backend services, data pipelines, SQL models, and interfaces for review tasks.
- Model annotation schemas, task assignment, data lineage, and dataset versions.
- Design quality checks, reviewer calibration, disagreement handling, and audit trails.
- Understand how feedback can become preference, training, or evaluation data.
- Protect sensitive content and collaborate with researchers and data operations.

**Extend:** distributed data processing, experimental interfaces, and model-training pipeline integration.

**Prove it:** build a review platform with a clear rubric, quality controls, versioned exports, and an analysis of reviewer disagreement. A labeling interface without data-quality reasoning is incomplete evidence.

<a id="specializations"></a>
## Three additional terms: specialization, operations, and breadth

### 14. Context Engineering

**Meaning:** curating what a model can see at each step: instructions, retrieved evidence, tool descriptions/results, history, and memory. Anthropic describes it as a broader discipline than arranging a single prompt. The source establishes the discipline, not universal recognition of a standalone “Context Engineer” job. [Technical source](https://www.anthropic.com/research/effective-context-engineering-for-ai-agents).

**Skills to develop:** retrieval measurement, token budgeting, provenance, relevance filtering, conversation-state design, memory boundaries, and tests for missing or conflicting evidence. **Extend:** long-task state management and tool-result design.

**Prove it:** compare two context-assembly strategies on the same questions and document quality, cost, and failure differences.

### 15. LLMOps

**Meaning:** practices for developing, deploying, observing, and maintaining LLM systems. Responsibilities may sit with AI, platform, MLOps, or application teams. The discipline does not mandate one job title or a single platform. [IBM overview](https://www.ibm.com/think/topics/llmops).

**Skills to develop:** CI/CD, configuration and prompt/model versioning, evaluation gates, traces, latency and usage monitoring, quotas, secrets, rollout/rollback, and incident response. **Extend:** model serving, GPU capacity, batching, or quantization when self-hosting is part of the job.

**Prove it:** operate a small AI service with a regression gate, redacted traces, a cost dashboard, and a demonstrated rollback. [Tracing concepts](https://opentelemetry.io/docs/concepts/signals/traces/).

### 16. AI Generalist

**Meaning in this guide:** a descriptive label for someone applying AI across several activities. This guide does not claim it is a standardized occupation or establish its prevalence from the reviewed sources.

**Skills to develop:** problem framing, AI literacy, research, structured writing, output review, basic data analysis, light automation, and effective handoff. Add deep competence in at least one domain—such as marketing, operations, product, or creative production.

**Prove it:** explain three scoped workflows you can deliver and their quality criteria. Write a concrete professional description such as “I build AI-assisted content and research workflows for marketing teams.” A list of tools alone does not tell an employer what you can own.

<a id="direction"></a>
## Choosing a direction and demonstrating competence

The following matches are editorial starting points, not labor-market forecasts:

| Your existing strength | Directions worth testing with a project |
|---|---|
| Software engineering | AI product, agents, automation, evaluation, deployment, LLMOps |
| Marketing and analytics | AI growth, GTM engineering, GEO |
| Design, writing, or video | AI creative strategy; add measurement and production discipline |
| Operations, consulting, or training | AI automation, deployment, enablement |
| Risk, privacy, or audit | AI governance; add AI system literacy |
| Data engineering or research tooling | Human Data engineering, evaluation, context engineering |

Build depth in one primary role and literacy in an adjacent one. For example, growth plus automation can help you build marketing systems; product engineering plus evaluation can help you ship measurable AI behavior. These combinations describe useful scope, not a requirement to become expert at every row.

A practical learning sequence is: choose one real workflow → learn the missing foundation → build a narrow deliverable → measure failures and outcomes → document decisions → obtain user or peer feedback. Use actual work samples to decide which specialty fits you.

For a portfolio or interview, be ready to answer:

1. What exact problem and user did you choose?
2. Why did you use AI, and what was the baseline?
3. What did you personally build or evaluate?
4. Which evidence supports the result, under what conditions?
5. What fails, what needs human review, and who owns operations?

Read job descriptions for **outputs, decision authority, coding depth, domain requirements, and success metrics**. A familiar title can describe very different work at two companies. The durable skill is being able to own a clearly defined outcome and show how you achieved it.

---

**Scope:** 13 role families plus Context Engineering, LLMOps, and AI Generalist. No salary ranking, hiring-growth estimate, or job guarantee is implied. Sources establish examples and technical concepts; the skills framework and exercises are the guide's synthesis. [Evidence and source notes](../resources/ai-roles-sources.md).
