# BOHEME Ecosystem

**BOHEME** — *Bridging Observations to Hypotheses through Executable Model Engineering*

BOHEME is an AI-enabled ecosystem connecting biological knowledge, executable modeling, and scientific discovery. It transforms scientific observations into structured and verified knowledge, integrates that knowledge into executable models, and enables simulation and analysis to explain biological behavior, generate predictions, and formulate new hypotheses.

BOHEME builds on the MeLoDy Lab's earlier **DySE framework** with a new generation of AI- and LLM-supported tools spanning the modeling and discovery process.

- **Web interface:** https://boheme.pitt.edu/
- **DySE (previous generation):** https://www.nmzlab.pitt.edu/sites/default/files/assets/DySE%202026.png

---

## Tools

### BioRECIPE
**Bio**logical system **R**epresentation for **E**valuation, **C**uration, **I**nteroperability, **P**reserving, and **E**xecution

A standardized, interoperable schema for representing biological knowledge and executable models in alignment with FAIR principles. BioRECIPE captures biochemical interactions and their biological context in a structured, machine-readable format accessible to computational tools, modelers, and biological domain experts.

Use the BioRECIPE web interface within BOHEME to translate existing representations (JSON, BioPAX, SIF) into the BioRECIPE schema, or to build interaction lists and models directly in BioRECIPE.

- **Publication:** Holtzapple, E., Zhou, G., Luo, H., Tang, D., Arazkhani, N., Hansen, C., Telmer, C. A., & Miskov-Zivanov, N. (2024). *The BioRECIPE Knowledge Representation Format.* ACS Synthetic Biology, 13(8), 2621–2624. https://doi.org/10.1021/acssynbio.4c00096
- **Funding:** DARPA Big Mechanism award AIMCancer (W911NF-17-1-0135); NSF EAGER award CCF-2324742

### VIOLIN
**V**ersatile **I**nteraction **O**rganizing to **L**everage **I**nformation in **N**etworks

A modular framework for reconciling new biological knowledge with existing knowledge graphs and mechanistic models. VIOLIN systematically compares literature-derived interactions with structured baseline knowledge to determine whether new evidence corroborates, contradicts, or extends what is already known — accounting for biological context and other interaction attributes. Its configurable graph-based approach supports heterogeneous knowledge sources and alternative reconciliation strategies, enabling transparent and scalable knowledge integration, model verification, refinement, and extension.

Uses the BioRECIPE format. Available as VIOLIN 2.0 within the BOHEME web interface.

- **Publication:** Luo, H., Hansen, C. E., Arazkhani, N., Telmer, C. A., Tang, D., Zhou, G., Spirtes, P., & Miskov-Zivanov, N. (2024). *VIOLIN: A modular framework for scalable reconciliation of heterogeneous interaction graphs.* bioRxiv. https://doi.org/10.1101/2024.07.21.604448
- **Funding:** DARPA Big Mechanism W911NF-17-1-0135; NSF EAGER Award #2324742; NIH R01LM014673

### DiSH
**Di**screte **S**tochastic **H**eterogeneous simulator

A flexible simulator for hybrid biological models with multiple deterministic and stochastic simulation schemes and customizable timing behaviors. DiSH supports models where individual elements can have different numbers of discrete activity levels and use logical or arithmetic update functions, combining qualitative regulatory relationships with quantitative detail when available. Additional flexibility comes from regulator weights, element memory, delayed responses, and spontaneous/unbalancing behaviors — enabling exploration of system dynamics at varying resolutions without the extensive kinetic parameters required by continuous models.

Earlier versions were presented at WSC'17 and WSC'21. A hardware (Verilog/FPGA) implementation was also developed (EMBC paper). **DiSH 2.0** is coming soon to the BOHEME web interface.

### CELESTA
**C**ontext **E**xtraction through **LE**arning with **S**emi-supervised multi-**T**ask **A**rchitecture

An AI framework for extracting the biological context needed to interpret interactions described in biomedical text. CELESTA uses open-set semi-supervised multi-task learning to identify contextual information tied to biological interactions — cell type, cell line, disease, organ, and intracellular location — by combining relation and context classification and leveraging both labeled and unlabeled data.

Use the CELESTA web interface within BOHEME to extract and assign biological context to interactions from biomedical text.

- **Publication:** Tang, D., Chow Tam, T. Y., Luo, H., Telmer, C. A., & Miskov-Zivanov, N. (2025). *An open-set semi-supervised multi-task learning framework for context classification in biomedical texts.* Journal of Biomedical Informatics, 169, 104886. https://doi.org/10.1016/j.jbi.2025.104886
- **Code/data:** GitHub (implementation, dataset, docs)
- **Funding:** NSF EAGER award CCF-2324742

### KALIMBA
**K**nowledge-**A**ssisted **L**iterature **M**ining for **B**iological Interaction **A**nalysis

A human-in-the-loop platform for extracting, curating, and exploring biological interactions from scientific literature. KALIMBA integrates NLP- and LLM-based interaction extraction with expert annotation and evidence-grounded conversational querying (RAG chat) in a unified workflow. Users can search the literature, extract interactions via NLP-only, LLM-only, or hybrid approaches, review and correct extracted knowledge, and interactively query the supporting source literature.

Available within the BOHEME web interface.

- **Publication:** Arazkhani, N., Kotecki, M., Cochran, B., & Miskov-Zivanov, N. (2026). *KALIMBA: Knowledge-Assisted Literature Mining for Biological Interaction Analysis.* Proceedings of the 25th Workshop on Biomedical Natural Language Processing (BioNLP 2026), 880–889. https://doi.org/10.18653/v1/2026.bionlp-1.71

### ACCORDION
**ACC**elerating and **O**ptimizing model **R**ecommen**D**at**ION**s

A model recommendation tool for context-aware knowledge selection and automated recommendation of executable biological models. Starting from a baseline model and candidate knowledge retrieved from literature and databases, ACCORDION uses graph-based clustering to identify relevant model extensions, then evaluates candidate models via simulation and formal analysis to recommend models that best reproduce known or desired system behavior — enabling systematic exploration of alternative mechanisms while cutting down large candidate interaction sets to those most relevant to the modeled biological context.

Works with discrete network models in the BioRECIPE format.

- **Publication:** Ahmed, Y., Telmer, C. A., Zhou, G., & Miskov-Zivanov, N. (2024). *Context-aware knowledge selection and reliable model recommendation with ACCORDION.* Frontiers in Systems Biology, 4, 1308292. https://doi.org/10.3389/fsysb.2024.1308292
- **Also:** ReadTheDocs documentation, GitHub source, Jupyter notebook for workflows/benchmarks
- **Funding:** DARPA Big Mechanism award AIMCancer (W911NF-17-1-0135); University of Pittsburgh, Swanson School of Engineering

### CLARINET
**CLARI**fying **NET**works

A model recommendation tool that evaluates literature-derived event collaboration graphs to identify useful extensions to existing biological network models. CLARINET organizes literature-extracted interactions into event collaboration graphs, evaluating them by occurrence/co-occurrence across publications and connectivity to a baseline model. It groups related interactions and ranks candidate extensions, helping modelers identify connected sets of new biological knowledge to incorporate. Parametrizable, and designed to efficiently process large sets of literature-extracted interactions.

Extends discrete network models in the BioRECIPE format using knowledge from literature.

- **Publication:** Ahmed, Y., Telmer, C. A., & Miskov-Zivanov, N. (2021). *CLARINET: efficient learning of dynamic network models from literature.* Bioinformatics Advances, 1(1), vbab006. https://doi.org/10.1093/bioadv/vbab006
- **Also:** ReadTheDocs documentation, GitHub repository, Jupyter notebook
- **Funding:** DARPA Big Mechanism award AIMCancer (W911NF-17-1-0135); University of Pittsburgh, Swanson School of Engineering

---

## How the pieces fit together

```
Literature / biomedical text
        │
        ▼
  CELESTA (context extraction)
  KALIMBA (interaction extraction, curation, RAG chat)
        │
        ▼
   BioRECIPE (shared knowledge representation format)
        │
        ├──▶ VIOLIN      (reconcile new knowledge against baseline models)
        ├──▶ ACCORDION    (recommend model extensions from candidate knowledge)
        ├──▶ CLARINET     (rank extensions via event collaboration graphs)
        │
        ▼
   DiSH (simulate the resulting executable model)
        │
        ▼
   Predictions / new hypotheses
```

All tools are developed and maintained by the **Miskov-Zivanov Lab (MeLoDy Lab)**, University of Pittsburgh — https://www.nmzlab.pitt.edu/