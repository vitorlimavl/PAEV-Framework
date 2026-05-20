<div align="center">

# PAEV Framework

### A Collaborative Approach for Technical Alignment and Evidence-Based Communication

**Problem → Analysis → Evidence → Validation**

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Version](https://img.shields.io/badge/version-1.0-blue.svg)](#)
[![Status](https://img.shields.io/badge/status-active-success.svg)](#)
[![DOI](https://img.shields.io/badge/DOI-pending-orange.svg)](#)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

*A structured communication framework for technical teams who want alignment, not arguments.*

[**Read the paper**](#-the-paper) · [**Quick start**](#-quick-start) · [**Examples**](#-examples) · [**Contributing**](#-contributing)

</div>

---

## What is PAEV?

PAEV is a four-step protocol for structuring technical conversations - particularly when something doesn't add up and you need to talk to a stakeholder about it.

It was created from a recurring frustration: technical teams spend enormous amounts of time resolving conflicts that don't come from a lack of information, but from misalignment in interpretation. Two dashboards show different revenue. A field arrives empty. A KPI definition is contested.

Most communication frameworks (SCQA, SCR, Pyramid Principle) optimize for **persuasion** - you have the answer, and you want to convince the audience.

PAEV optimizes for something different: **collaborative alignment**. You have a diagnosis, but the final answer belongs to whoever owns the business rule.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│   P  →  A  →  E  →  V                                    │
│                                                          │
│   Problem    State the observable issue, without blame.  │
│   Analysis   Show the technical interpretation.          │
│   Evidence   Back it up with data, logs, examples.       │
│   Validation Hand the decision back to the right owner.  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

## Why it exists

After years leading data and analytics teams, I noticed the same pattern over and over:

- A discrepancy is found in a metric.
- Someone raises it in a meeting.
- The phrasing sounds accusatory - even when no one intended it.
- The business team gets defensive.
- The conversation turns into a search for who's at fault.
- The actual rule never gets defined.
- Three months later, the same discrepancy reappears.

The problem was never the technical investigation. The problem was the **structure of the conversation**.

PAEV is the structure I started using to fix this. After enough times of it working, I wrote it down.

---

## The four stages

### **P** - Problem
> State the observable issue. No interpretation, no blame, just the fact.

The audience needs to understand *what* is happening before they hear *why* you think it's happening.

**Good:** *"47 orders arrived without a CPF field in the last 15 days."*
**Bad:** *"Someone messed up the validation and orders are coming through broken."*

### **A** - Analysis
> Show how you investigated and what the technical interpretation is.

This is where you demonstrate that you've done the work. Analysis converts a complaint into a diagnosis.

**Good:** *"Our investigation shows the field isn't being validated as required at submission time. Since CPF is needed for invoicing, this may be generating invalid orders downstream."*

### **E** - Evidence
> Back the analysis with measurable information.

Numbers, logs, queries, screenshots, examples. Evidence shifts the conversation from opinion to diagnosis.

**Good:** *"In October, the dashboard showed R$2.3M and the financial report R$1.9M. The R$400K gap corresponds exactly to orders placed in October but paid in November."*

### **V** - Validation
> Hand the decision back. Ask the question that closes the loop.

This is the step that doesn't exist in other frameworks. Instead of imposing a conclusion, you return ownership to whoever has the authority to define the rule.

**Good:** *"Should revenue be recognized by order date or by payment date? That answer lets us standardize the criterion across all sources."*

---

## Quick start

You don't install PAEV. You use it the next time you need to raise a technical issue with someone.

The minimal template, in any channel (Slack, email, meeting, ticket):

```
P - [What is observable and specific]
A - [How you investigated it and what you think]
E - [What data backs that up]
V - [The exact question you need answered, or the confirmation you need]
```

That's it. Four lines, four minutes to write, and the conversation changes.

---

## Examples

### Example 1 - Revenue discrepancy in a data platform

**Without PAEV** *(typical failure mode)*

> "The dashboard is showing a different number from the financial report. Someone did something wrong."

*Outcome: defensive reactions, blame-seeking, issue unresolved.*

**With PAEV**

> **P** - A discrepancy was identified between the sales dashboard and the monthly financial report.
>
> **A** - The dashboard calculates revenue based on order date, while the financial report uses payment confirmation date.
>
> **E** - October: R$2.3M vs R$1.9M. The R$400K gap matches exactly the orders placed in October but paid in November.
>
> **V** - Should revenue be recognized by order date or by payment date? That definition lets us align all downstream systems.

*Outcome: business owns the rule, all reports get aligned, the problem doesn't come back.*

### Example 2 - Missing field in an integration

**Without PAEV**

> "Orders are coming through without the CPF. That validation is broken."

**With PAEV**

> **P** - Orders are arriving in the system without a CPF value.
>
> **A** - The field isn't being validated as required at submission time. Since CPF is required for invoicing, this may be generating invalid orders downstream.
>
> **E** - 47 orders in the last 2 weeks have arrived with this field empty. Report available on request.
>
> **V** - Should CPF be required in all cases, or is there a business exception we haven't mapped yet?

### Example 3 - KPI definition conflict

> **P** - Marketing's "active user" count differs from Product's by ~12% every week.
>
> **A** - Marketing counts any user with a session in the period. Product requires at least one meaningful action (defined by the events table). Both definitions are internally consistent.
>
> **E** - Week of Nov 11: Marketing = 84,302; Product = 74,118. The 10,184 delta corresponds entirely to users who opened the app but didn't complete a tracked action.
>
> **V** - Which definition should be the company-wide "active user"? Or should we maintain both with distinct names (e.g., *sessions* vs *engaged users*)?

---

## When to use PAEV

PAEV works well when:

- You've identified a discrepancy, inconsistency, or unclear behavior.
- You have a technical analysis, not just a complaint.
- The decision involves business interpretation, not pure engineering.
- You need alignment, not just approval.
- A definition or rule needs to be established or confirmed.

## When *not* to use PAEV

- **Emergencies.** When the building is on fire, raise the alarm first; structure the conversation later.
- **Pure execution tasks.** If the rule is already defined, just do the work.
- **Persuasion contexts.** If you already know the answer and need to sell it, SCQA or SCR fit better.
- **Pure information sharing.** A status update doesn't need a validation step.

---

## How PAEV differs from other frameworks

| Framework | Optimizes for | Final step | When the answer is known |
|---|---|---|---|
| **SCQA** *(Minto)* | Persuasion | Answer | Speaker has it |
| **SCR** *(McKinsey)* | Persuasion | Resolution | Speaker has it |
| **Pyramid Principle** | Structured argument | Conclusion | Speaker has it |
| **PAEV** | Collaborative alignment | Validation | **Co-constructed** |

PAEV is closer in spirit to diagnostic medicine or technical investigation than to consulting communication. The investigator presents findings; the person with authority decides what they mean.

---

## The paper

The full framework is documented in a paper available in this repository.

| Format | File | Use for |
|---|---|---|
| **PDF** | [`paper/PAEV_Framework_v1.pdf`](paper/PAEV_Framework_v1.pdf) | Reading, citing, sharing |
| **DOCX** | [`paper/PAEV_Framework_v1.docx`](paper/PAEV_Framework_v1.docx) | Editing, translating, adapting |
| **Markdown** | [`paper/PAEV_Framework_v1.md`](paper/PAEV_Framework_v1.md) | Web, blog adaptation |

The paper has also been deposited on **Zenodo** for permanent archiving and citation:

> Vasconcelos de Lima, V. H. (2026). *The PAEV Framework: A Collaborative Approach for Technical Alignment and Evidence-Based Communication.* Zenodo. DOI: *pending*

---

## Templates

Drop-in templates for common channels.

### Email / Slack message

```
Hi [name],

I want to flag something we identified while looking at [area].

Problem
[Observable issue, specific and neutral.]

Analysis
[How we investigated and what we currently understand.]

Evidence
[Numbers, logs, or examples that back this up.]

Question
[The exact thing we need confirmed or defined.]

Happy to go deeper on any of the points.
```

### Ticket / issue description

```markdown
## Problem
<!-- What's observable? Be specific. -->

## Analysis
<!-- What did we investigate? What's our current interpretation? -->

## Evidence
<!-- Logs, screenshots, queries, numbers. -->

## Validation needed
<!-- What decision do we need, and from whom? -->
```

### Meeting opener (60 seconds)

> "Quick framing before we get into it. We've identified that [P]. Based on our investigation, [A]. We can see this because [E]. What we need from you in this meeting is [V]."

---

## FAQ

**Is PAEV only for data teams?**
No. It was developed in data and analytics contexts, but the structure works for any technical discipline that interfaces with business stakeholders: software engineering, infrastructure, security, QA, ML.

**Can I use it internally too, with my own team?**
Yes - particularly in 1-on-1s and incident postmortems. The Validation step works just as well when the "rule owner" is another engineer or a tech lead.

**Is there a tool or library?**
Not yet. PAEV is a protocol, not software. If you want to build a Slack bot, a ticket template, or an LLM prompt around it, you're welcome to. See [Contributing](#-contributing).

**How is this different from "Five Whys" or RCA?**
Root cause analysis tries to find the cause. PAEV structures the *conversation* about a finding. They compose well: use RCA to investigate, use PAEV to communicate the result.

**Can I translate PAEV to my language?**
Please do. The acronym happens to work in Portuguese (Problemática, Análise, Evidência, Validação) and English (Problem, Analysis, Evidence, Validation). For other languages, prioritize meaning over the acronym.

---

## Contributing

PAEV is a young framework. Contributions are welcome in several forms:

- **Case studies.** If you've used PAEV in a real situation, write it up and open a PR adding it to `examples/`.
- **Translations.** Translate the README or paper into another language.
- **Templates.** Adapt the framework to specific tools (Jira, Linear, GitHub Issues, Notion).
- **Critique.** Open an issue if you've tried PAEV and it didn't work, or if you see a flaw in the reasoning.
- **Empirical work.** If you're a researcher interested in studying the framework's effectiveness, get in touch.

For substantive changes to the framework itself, open an issue first to discuss.

---

## Roadmap

Planned, in rough priority order:

- [ ] Empirical case studies across different organizations
- [ ] Portuguese version of the paper
- [ ] Templates for Jira, Linear, and GitHub Issues
- [ ] LLM prompt library for drafting PAEV-structured messages
- [ ] Comparison study with SCQA in a controlled context
- [ ] Conference submission (DataHackers, QCon, or similar)

---

## Citation

If you reference PAEV in academic or professional work:

```bibtex
@misc{vasconcelos2026paev,
  author       = {Vasconcelos de Lima, Vitor Hugo},
  title        = {The {PAEV} Framework: A Collaborative Approach for
                  Technical Alignment and Evidence-Based Communication},
  year         = {2026},
  publisher    = {Zenodo},
  version      = {1.0},
  doi          = {pending},
  url          = {https://github.com/<your-username>/paev-framework}
}
```

---

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to share, adapt, and use the framework in any context - including commercial - as long as appropriate credit is given.

---

## Author

**Vitor Hugo Vasconcelos de Lima**
Data & Analytics Leadership · Pernambuco, Brazil

The PAEV framework was developed in response to recurring alignment challenges observed in stakeholder-facing technical work. Correspondence and collaboration inquiries are welcome.

---

<div align="center">

*Better conversations produce better decisions.*

</div>
