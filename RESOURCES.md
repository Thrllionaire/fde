# Forward Deployed Engineering Resources

Curated 2026-10-01. Tiered by trust: **primary** = written or spoken by someone who did the
job; **secondary** = aggregation with a named author and checkable claims; **market** = job
posts and interview reports, useful as evidence of what is actually being hired for, not as
analysis. Anything that was marketing dressed as education was left out.

## Knowledge — primary (practitioner accounts)

- [Nabeel S. Qureshi, "Reflections on Palantir"](https://nabeelqu.co/reflections-on-palantir) (Oct 2024)
  Eight years as a Palantir FDE, written after leaving. The single best source on what the work
  actually felt like: the FDE/PD split, "get on a plane first, ask questions later", learning the
  customer's vocabulary ("non-conformities", "capacity management"), and why Palantir handed out
  Keith Johnstone's *Impro* to teach status-reading. Use for: the discovery lessons, the culture
  question in a values round, and anything about what separates a good FDE from a competent one.

- [Bob McGrew on the YC Lightcone podcast, "The FDE Playbook for AI Startups"](https://www.youtube.com/watch?v=Zyw-YA0k3xo) (Sep 2025)
  McGrew helped invent the role at Palantir, then ran research at OpenAI. The clearest statement
  of the *economic* argument: an FDE "bridges the gap between existing product capabilities and the
  specific needs of the customer", the Echo/Delta split, and why the model is "doing things that
  don't scale, at scale". Use for: why AI labs hire FDEs now, and the product-generalisation question.

- [Colossus, "The Patriot: Shyam Sankar of Palantir"](https://colossus.com/article/the-patriot-shyam-sankar-palantir/)
  Long-form history of how Sankar invented the model: the CIA demo loop (fly Sunday, demo Mon–Thu,
  fly back Friday, code over the weekend), the COIC deployment, Karp's French-restaurant analogy
  ("the wait staff are part of the kitchen staff"). Use for: origin story, and the argument that
  the feedback loop *is* the product process.

- [PostHog, "WTF is a forward deployed engineer?"](https://posthog.com/blog/forward-deployed-engineer)
  Interviews named Palantir FDEs. Carries the cleanest one-line statement of why AI labs need the
  role — Anjor Kanekar: "There is a gap between foundational model capabilities and the application
  of those in enterprise use cases where they can add value." Also a usable FDE-vs-SWE comparison
  table (60–80% customer time vs 10–20%). Use for: the role-definition lesson and the recruiter screen.

## Knowledge — the deployment problem itself

- [MIT Media Lab Project NANDA, "The GenAI Divide: State of AI in Business 2025"](https://www.aigl.blog/state-of-ai-in-business-2025/)
  The 95%-of-pilots-show-no-P&L-impact study. Method: 300+ public initiatives, 52 structured
  interviews, 153 survey responses, Jan–Jun 2025. Critically, the authors blame brittle workflows,
  weak contextual learning and poor fit with daily operations — *not* model capability. Use for:
  the "why scoping is the job" argument. Cite the method, not just the number; the number is widely
  overquoted and the sampling is not a random sample of enterprises.

- [Anthropic, "Building effective agents"](https://www.anthropic.com/engineering/building-effective-agents)
  Already covered in `../learnaiagents`. Reach for it here only when an FDE scoping decision turns
  into an architecture decision — workflow vs agent is a scoping question before it is a design one.

## Market evidence (what is actually being hired)

- [Anthropic — Forward Deployed Engineer, Applied AI (job description)](https://www.anthropic.com/careers/jobs/4985877008)
  The requirements list is the syllabus: ship production applications on Claude; deliver MCP
  servers, sub-agents and agent skills as customer artifacts; white-glove enterprise deployment;
  *codify repeatable deployment patterns and feed them back to Product*; 25–50% travel; 8+ years
  in technical customer-facing roles. Note the explicit ask for "evaluation frameworks" and "high
  agency with an ability to navigate ambiguity". Re-read before every mock interview.

- [Exponent, "Forward Deployed Engineer Interview: The Definitive 2026 Guide"](https://www.tryexponent.com/blog/forward-deployed-engineer-interview-the-definitive-2026-guide-fde)
  Aggregated loop structure and per-company variations (Anthropic / OpenAI / Palantir). Secondary,
  commercially motivated, and the rubric language is reconstructed rather than leaked — treat the
  *shape* as reliable and the specific wording as approximate. Use for: knowing which rounds exist.
  The decomposition/open-ended case round is reported as the highest-failure stage; that claim is
  consistent across the other interview write-ups found, which is weak but non-zero evidence.

## Wisdom (communities)

- [MLOps Community Slack](https://mlops.community/) — ~20k members. Currently the densest place
  adjacent FDE practitioners actually talk, because no large FDE-specific community exists yet.
  Use for: production-deployment war stories, and sanity-checking an architecture before a panel.
- **Palantir alumni** — the densest FDE talent network there is, and they answer cold outreach from
  people who have read their writing. Use for: one 30-minute conversation, after Lesson 02, with a
  specific question rather than "can I pick your brain".
- Not yet joined. Revisit after Lesson 03 — the right moment to join is when you have an artifact
  to get critiqued, not before.

## Gaps

- **No high-trust first-hand account of an AI-lab FDE deployment.** Everything primary is Palantir-era.
  The Anthropic/OpenAI versions of the job are documented only through job posts and interview
  reports. Watch for Applied AI engineering posts; treat current claims about the AI-lab variant as
  inference from the JD, and label them as such in lessons.
- **Nothing credible on pricing/scoping economics of an engagement.** The one 2026 "playbook" with a
  runbook and scorecard is paywalled and unverifiable; excluded deliberately.
- **No primary source on the pilot→production security gauntlet** (VPC, SSO, data residency,
  procurement) written by someone who ran one. Needed for Lesson 04 — search vendor security-review
  documentation and enterprise AI deployment guides before writing it.
