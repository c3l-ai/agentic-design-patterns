# From Objects to Agents
## Repurposing Classical Design Patterns for Agentic AI Systems

**Srecko Joksimovic & George Siemens**

Centre for Change and Complexity in Learning (C3L), Adelaide University · Southern New Hampshire University

---

This book presents a formal mapping between the classical Gang of Four (GoF) design pattern catalogue and the emerging architectural problems of agentic AI systems. Fourteen of the original twenty-three GoF patterns map meaningfully to recurring problems in multi-agent system design — and each requires extension to account for the *stochasticity delta*: the set of properties that LLM-based agents possess that classical software components do not.

### Read the book

**[c3l-ai.github.io/agentic-design-patterns](https://c3l-ai.github.io/agentic-design-patterns)**

---

### Pattern catalogue

**Creational**

| Pattern | Agentic Role | Status |
|---|---|---|
| Abstract Factory | Eval suite generation per agent type | Complete |
| Builder | Multi-agent pipeline assembly | Complete |
| Singleton | Shared configuration and governed data product singletons | Complete |

**Structural**

| Pattern | Agentic Role | Status |
|---|---|---|
| Adapter | Tool layer, model layer, and data layer interface translation | Complete |
| Decorator | Composable agent wrappers — guardrails, logging, reflection, rate limiting | Complete |
| Facade | Data fabric, inference, and tool registry simplification | Complete |
| Composite | Hierarchical agent, pipeline, and eval suite trees | Complete |

**Behavioural**

| Pattern | Agentic Role | Status |
|---|---|---|
| Strategy | Interchangeable reasoning strategies — ReAct, Reflection, Planning, Tool Use, Multi-Agent | Complete |
| Chain of Responsibility | Sequential agent routing and triage | In progress |
| Command | Encapsulated, replayable, auditable tool invocations and eval traces | In progress |
| Observer | Event-driven agent triggers and longitudinal monitoring | In progress |
| Template Method | Fixed workflow with pluggable reasoning steps | In progress |
| Mediator | Centralised multi-agent coordination without direct coupling | In progress |
| Memento | State snapshots, context handoff, construction rollback | In progress |
| State | Agent mode switching — exploring, executing, reflecting | In progress |

---

### Key concepts

**Stochasticity delta** — the set of architectural extensions required because LLM-based agents are non-deterministic, fail ambiguously, accumulate context, and require meta-evaluation. Documented explicitly for each pattern.

**Eval as data product** — evaluation outputs should be versioned, schematised, and queryable governed assets, not transient signals. The Abstract Factory, Command, Memento, and Observer patterns compose into a complete eval data product infrastructure.

**Two singleton classes** — configuration singletons (eval thresholds, tool schemas, safety constraints) and active data product singletons (learner wellness profiles, shared session state). Both require singleton treatment in multi-agent systems but for different reasons.

**Three adapter layers** — tool layer (canonical tool interface over heterogeneous APIs), model layer (canonical LLM interface over providers), data layer (canonical data product schema over custodial domain sources). Each with a distinct stochasticity delta property.

**Decorator ordering as safety constraint** — the order of the decorator stack has safety consequences. GuardrailDecorator must be outermost; LoggingDecorator must log guardrail-approved outputs only. This is a safety requirement, not a style preference.

**Factory Method absorbed into Strategy** — in GoF, Factory Method governs creation and Strategy governs execution. In agentic AI these concerns collapse: selecting a reasoning strategy is itself a reasoning act. Factory Method does not earn a standalone entry; its concern is absorbed into the AgentRunner's selectStrategy() logic.

---

### Repository structure

```
_quarto.yml                      # Book configuration
index.qmd                        # Preface
01-introduction.qmd              # Introduction
02-framework.qmd                 # GoF mapping criteria, stochasticity delta, responsible AI thread
patterns/
  creational/
    abstract-factory.qmd         # Complete
    builder.qmd                  # Complete
    singleton.qmd                # Complete
  structural/
    adapter.qmd                  # Complete
    decorator.qmd                # Complete
    facade.qmd                   # Complete
    composite.qmd                # Complete
  behavioural/
    strategy.qmd                 # Complete
    chain-of-responsibility.qmd  # In progress
    command.qmd                  # In progress
    observer.qmd                 # In progress
    template-method.qmd          # In progress
    mediator.qmd                 # In progress
    memento.qmd                  # In progress
    state.qmd                    # In progress
06-composability.qmd             # Cross-pattern composition and eval data product infrastructure
07-case-study.qmd                # NLI system as worked example
figures/                         # SVG diagrams (minimal per completed pattern)
references.bib                   # BibTeX references
custom.scss                      # Book theme — Playfair Display, Source Serif 4, IBM Plex Mono
```

---

### Building locally

```bash
# Install Quarto: https://quarto.org/docs/get-started/
quarto preview --to html    # Live preview
quarto render --to html     # Full render to docs/
```

### Companion system

Several canonical examples are drawn from the Next Level Insight (NLI) system — a person-centred, governed AI platform for wellness and learning analytics developed at C3L, Adelaide University. NLI sits on top of the Global Data Consortium federated data architecture and implements the pattern catalogue described here across a full multi-agent pipeline.

---

### License

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

### Citation

```bibtex
@book{joksimovic2026objects,
  title     = {From Objects to Agents: Repurposing Classical Design Patterns
               for Agentic {AI} Systems},
  author    = {Joksimovic, Srecko and Siemens, George},
  year      = {2026},
  publisher = {C3L, Adelaide University},
  url       = {https://c3l-ai.github.io/agentic-design-patterns}
}
```
