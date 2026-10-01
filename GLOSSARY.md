# FDE Glossary

House definitions. Where a term is contested, the contest is noted. Lessons use these spellings
and these meanings; if a lesson needs a different one, the glossary is wrong and gets fixed.

---

**Forward Deployed Engineer (FDE)** — An engineer who works inside a customer's environment and
is accountable for whether the deployed system works and gets used, not for delivering a spec.
The term is Shyam Sankar's, coined at Palantir c. 2006; "forward deployed" is borrowed from
military usage, meaning stationed at the point of action rather than at a rear base.
Palantir's own title is **FDSE** (Forward Deployed Software Engineer). Anthropic files the role
under **Applied AI**.

**Echo / Delta** — Palantir's split of the forward-deployed function. *Echo* finds the right
problem and holds the customer relationship (embedded analysts, domain people). *Delta* turns
the answer into working software on site (prototyping engineers). At smaller companies one
person is both, which is the version you are training for.

**PD (Product Development)** — The non-deployed engineering org that generalises what FDEs build
for one customer into product that serves many. The FDE/PD handoff is the mechanism that keeps
the model from being consulting. Qureshi: "Your job was to solve the problem, and not worry about
overfitting; PD's job was to take whatever you'd built and generalize it."

**Capability–application gap** — The distance between what a frontier model can do and what a
specific enterprise workflow needs. The reason AI labs hire FDEs: the gap is closed per-customer,
by someone who can both read the workflow and write the code.

**Cut sheet** — (House term, this course.) The five-line scope of a first deployment: one user,
one workflow, one baseline, one thin slice, one kill criterion. Each line is one sentence and
every line must be fillable from evidence, not from the customer's aspiration.

**Thin slice** (also **walking skeleton**) — The smallest end-to-end artifact that moves the
baseline number for the named user. End-to-end is the load-bearing part: a slice that stops at a
demo is a prototype, not a slice.

**Baseline** — What the workflow costs today, *measured*. Time per instance, instances per week,
error or rework rate, cost. An executive's estimate is not a baseline; it is a hypothesis about
the baseline, and should be labelled as one until someone counts.

**Kill criterion** — The number that, unmet by a stated date, ends the pilot. Agreed with the
customer in writing before work starts. Its purpose is not pessimism — it is the thing that makes
the success number mean something.

**Pilot** — A time-boxed first deployment with real users and real data. Distinguished from a
**POC** (proof of concept), which uses sample data and proves only that the technology runs.
Most of the industry uses the words interchangeably; this course does not.

**Pilot purgatory** — The state of a deployment that works, is liked, and never enters production
because no one owns the budget, the security review, or the on-call. The MIT NANDA study's 95%
live here. Avoiding it is a scoping decision made before the pilot starts, not a sales push after.

**Time to first value (TTFV)** — Days from engagement start to the first moment the named user
gets a result they would miss if you took it away. The FDE metric that correlates with renewal.

**Design partner** — An early customer who gets access and influence in exchange for deep access
to their workflow and tolerance for roughness. The pre-product version of a deployment.

**Land and expand** — Win one workflow, prove the number, then use that proof to take the next
workflow in the same organisation. The commercial logic the cut sheet serves: a narrow first
deployment is not a small ambition, it is the cheapest route to a large one.

**Consulting death spiral** — When per-customer work never generalises, so revenue scales only
with headcount and the product never improves. The structural risk of the FDE model; the defence
is the FDE→PD feedback path and a deliberate count of what became product.

**Product leverage** — How much of what you built for one customer serves the next one. The
second half of an FDE's performance review, and the half candidates forget to mention.

**White-glove deployment** — Hands-on, high-touch delivery into an enterprise environment:
their VPC or hardware, their identity provider, their review boards. Named explicitly in
Anthropic's FDE job description.

**Ontology** — Palantir's term for the mapping between a customer's real-world entities and the
data model the software operates on. Generalise the idea, not the product: every deployment has
an ontology problem, and discovering it is usually the hardest week.

**Heretic** — Sankar's hiring heuristic: the person inside a domain who already believes the
standard way is wrong. Makes a good Echo because they will tell you where the bodies are.

**"Doing things that don't scale, at scale"** — McGrew's description of the FDE model: the
per-customer work is deliberately unscalable, and the company is built so that it still compounds.
