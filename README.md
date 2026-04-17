# From Objects to Agents
## Repurposing Classical Design Patterns for Agentic AI Systems

**Srecko Joksimovic & George Siemens**

Centre for Change and Complexity in Learning (C3L), Adelaide University

---

This book presents a formal mapping between the classical Gang of Four (GoF) design pattern catalogue and the emerging architectural problems of agentic AI systems. Twelve of the original twenty-three GoF patterns map meaningfully to recurring problems in multi-agent system design — and each requires extension to account for the *stochasticity delta*: the set of properties that LLM-based agents possess that classical software components do not.

### Read the book

**[c3l-ai.github.io/agentic-design-patterns](https://c3l-ai.github.io/agentic-design-patterns)**

### Pattern catalogue

**Creational**
- Abstract Factory → Eval suite generation per agent type
- Builder → Multi-agent pipeline assembly
- Singleton → Shared singleton resources and governed data products

**Structural**
- Decorator → Composable agent wrappers (guardrails, logging, reflection)
- Facade → Tool abstraction layer
- Composite → Hierarchical agent / sub-agent trees

**Behavioural**
- Strategy → Interchangeable reasoning strategies (ReAct, Reflection, Planning, Tool Use, Multi-Agent)
- Chain of Responsibility → Sequential agent routing and triage
- Command → Encapsulated, replayable, auditable tool invocations
- Observer → Event-driven agent triggers and longitudinal monitoring
- Template Method → Fixed workflow with pluggable reasoning steps
- Mediator → Centralised multi-agent coordination
- Memento → State snapshots, context handoff, rollback
- State → Agent mode switching (exploring, executing, reflecting)

### Key concepts

**Stochasticity delta** — the set of architectural extensions required because LLM-based agents are non-deterministic, fail ambiguously, accumulate context, and require meta-evaluation. Documented for each pattern.

**Eval as data product** — evaluation outputs should be versioned, schematised, and queryable governed assets, not transient signals. The Abstract Factory, Command, Memento, and Observer patterns compose into a complete eval data product infrastructure.

### Repository structure

```
_quarto.yml              # Book configuration
index.qmd                # Preface
01-introduction.qmd      # Introduction
02-framework.qmd         # GoF mapping criteria and stochasticity delta
patterns/
  creational/            # Abstract Factory, Builder, Singleton
  structural/            # Decorator, Facade, Composite
  behavioural/           # Strategy, CoR, Command, Observer, ...
06-composability.qmd     # Cross-pattern composition
07-case-study.qmd        # NLI system as worked example
figures/                 # SVG diagrams (minimal + conceptual per pattern)
references.bib           # BibTeX references
custom.scss              # Book theme
```

### Building locally

```bash
# Install Quarto: https://quarto.org/docs/get-started/
quarto preview           # Live preview
quarto render            # Full render to docs/
```

### License

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

### Citation

```bibtex
@book{joksimovic2026objects,
  title     = {From Objects to Agents: Repurposing Classical Design Patterns for Agentic {AI} Systems},
  author    = {Joksimovic, Srecko and Siemens, George},
  year      = {2026},
  publisher = {C3L, Adelaide University},
  url       = {https://c3l-ai.github.io/agentic-design-patterns}
}
```
