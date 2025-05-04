This repository serves as the master index for all assets of the open-source khub.ai project. It is the foundation of an ambitious initiative to create a Knowledge Hub tailored for the era of Generative AI.

## Project goals

### Long-term goal

**Build an open-source framework that serves as a Knowledge Hub for the Generative AI era.**

We envision a future platform where any person with domain expertise can converse with AI agents to capture and share their knowledge. This shared knowledge forms a repository of specialized “knowledge modules” that can be combined to build larger intelligent systems. In other words, we aim to democratize AI knowledge creation: experts contribute their know-how in a natural dialog with AI, and that expertise is preserved for others to reuse and build upon, much like open-source code.

As an analogy, imagine a GenAI-era hybrid of Facebook and GitHub, centered around a community-driven knowledge repository. In this paradigm:

- LLMs (including the multimodal types) are the new CPUs – Large Language Models and Vision-Language Models become the core computation engines of the platform.
- Knowledge modules are the new programming language – Modular chunks of expert knowledge act like the “code” or libraries that power specialized capabilities.
- Highly specialized GenAI bots are the new software applications – Each bot is an AI application focused on a niche domain or task, built by combining relevant knowledge modules with foundation models.
- Smart agents, people, and organizations are the users – These are the end-users (human or AI) that interact with the bots to solve problems, much as one would use software applications.

To realize this vision, we have identified several key insights that guide our approach:

- **Continuous and Efficient Incremental Learning**: Real-world problem domains often follow long-tail distributions, meaning there are endless edge cases. Traditional batch-based training and fine-tuning are inadequate because a truly expert system must learn continuously and never stop adapting, and also doing it with good efficiency.
- **Transparency and Trust**: Many expert systems are mission-critical, so the knowledge embedded in them must be transparent, human-auditable, traceable, portable, and explainable. Opaque, monolithic LLMs can serve as powerful foundations, but by themselves they cannot meet these stringent requirements for trust and verification.
- **Model‑Friendly Architecture**: Our platform is designed to ride the wave of rapid LLM and multimodal innovation. Instead of competing to build the next breakthrough model, we focus on making it straightforward to integrate whichever engines prove most capable at any given time. This plug‑and‑play flexibility lets us adopt the best models from any vendor or open‑source community while we concentrate on the unique value layer—capturing, organizing, and serving domain knowledge. In practice, this keeps the framework future‑proof and vendor‑neutral without imposing the overhead of supporting every model under the sun.
- **Lowering the Knowledge‑Acquisition Barrier—While Guarding Quality**: Making contributions as easy as chatting sparks the viral network effect we need; more experts join because the process is effortless. To keep that growth trustworthy, the platform automatically checks new modules for consistency, accuracy, drift, and provenance. This blend of frictionless input and built‑in QA lets the knowledge base scale rapidly without sacrificing reliability.

### Mid-term goal

**Develop and validate the core components of the Knowledge Hub platform**

In the mid term, our focus is on implementing the key features that will make the Knowledge Hub concept a reality. This includes prototyping the **inference-time learning** mechanism and establishing a framework for community-driven knowledge module management. We aim to release an initial open-source platform where domain experts can begin contributing knowledge modules and AI agents can utilize them in real time. Achieving this intermediate milestone will prove out our approach and set the stage for scaling up towards the long-term vision.

#### Inference-time learning for GenAI

Addressing these challenges calls for a shift toward an inference-time learning paradigm. Rather than relying solely on offline training, our approach enables the AI to learn and update its knowledge during inference (on-the-fly as it interacts with users). This inference-time learning methodology is at the heart of how we plan to keep the knowledge hub continuously improving and responsive to new information.

With this inference-time learning methodology we aim to achieve the following:

- The learnring process is increment, instant, and interactive.
- The learnring process can be multimodal.
- The knowledge acquired this way is in plain text, it is thus transparent, auditable by humans, and relatively portable among LLMs. 
- The knowledge acquired are typically generalized from specific instances, thus applicable to a wider context.

**Updating near-term goals**

The user has provided a draft for the near-term goals and wants it to be made clearer and more structured. I'll rewrite it to maintain the professional, succinct, and structured tone they prefer. I'll focus on integrating "inference-time learning", highlighting proof-of-concept tasks, and correcting typos like "genealized" to "generalized". I'll ensure a consistent heading style, refine language, and clarify analogies from earlier sections. I'll also emphasize near-term deliverables and reduce unnecessary details, especially about viral effects and knowledge acquisition.

### Near‑Term Milestones

Our immediate goal is to **prove and refine inference‑time learning** across several challenging use cases:

* **One‑shot / few‑shot image classification**
  Validate that the framework can absorb new visual classes after only a handful of examples, confirming multimodal adaptability.

* **ARC‑AGI‑v2 puzzle benchmark**
  A rigorous testbed for emergent reasoning, where we will measure:

  1. **Skill accumulation** across hundreds of puzzles.
  2. **Human‑guided adaptation** from sparse expert hints.
  3. **Concept grounding** in notions such as gravity, containment, and diffusion—precursors to capturing higher‑level human preferences.

* **Minimal “Jarvis” personal agent**
  A lightweight assistant that continuously tailors its behavior to a user’s habits (e.g., file retrieval, command shortcuts) without offline retraining.

* **Adaptive‑robotics sandbox**
  Demonstrate real‑time policy updates for a simulated robot facing unseen tasks or environments.

* **Exploratory pilots**
  Additional studies—such as conversational tutoring or social‑empathy modules—will test how well inference‑time learning captures nuanced human factors.

* **Normative‑Knowledge Pilot**
  Test whether inference‑time learning can capture value‑laden domains such as ethics or statutory law. A small panel of legal/ethics experts will iteratively correct the model on real‑world dilemmas and case snippets, while automated checks monitor consistency, provenance, and bias. Success metrics include alignment with expert judgments and stability under new, unseen scenarios.

  Our interest in this stems from the following observations related to solving the ARC-AGE-v2 puzzles:

| Aspect                 | Why ARC‑style interaction helps                                                                                                                                                              | Extra hurdles in ethics / law                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Concept formation**  | ARC‑AGI‑v2 shows an LLM can internalize abstract visual notions (e.g., gravity, containment) by iteratively proposing solutions and updating from sparse hints  | Ethical/legal norms are *value‑laden* and often contested; the “correct” answer may differ by culture or jurisdiction.                                           |
| **Sparse supervision** | Inference‑time learning lets experts teach concepts that are too rare for batch datasets                                                                                         | Expert reviewers must be accredited (lawyers, ethicists), raising cost and slowing the feedback loop.                                                            |
| **Drift handling**     | Interactive updates keep the system aligned with new puzzle variants; analogous mechanisms could track new statutes or precedents in real time.                                              | Norms evolve unpredictably and sometimes contradict earlier rulings; the system needs conflict‑resolution logic plus provenance tracking.                        |
| **Evaluation**         | ARC puzzles have binary pass/fail tests.                                                                                                                                                     | Measuring success in ethics (e.g., “fairness”) or law (e.g., “sound legal reasoning”) requires nuanced, often subjective metrics and multi‑stakeholder review.   |
| **Safety & bias**      | Puzzle mis‑generalisations carry minimal risk.                                                                                                                                               | Errors in legal or moral advice can have serious real‑world consequences, so verification pipelines and liability shields become mandatory.

<!-- [1]: https://arcprize.org/blog/announcing-arc-agi-2-and-arc-prize-2025?utm_source=chatgpt.com "Announcing ARC-AGI-2 and ARC Prize 2025"
[2]: https://www.reddit.com/r/singularity/comments/1jwb0s5/arcagi2_overview_indepth_presentation/?utm_source=chatgpt.com "ARC-AGI-2 Overview (in-depth presentation) : r/singularity - Reddit"
[3]: https://arxiv.org/html/2412.14352v1?utm_source=chatgpt.com "A Survey on LLM Inference-Time Self-Improvement - arXiv" -->

These milestones stress‑test scalability, human‑in‑the‑loop learning, and cross‑modal knowledge transfer, which are critical steps toward a robust Knowledge Hub platform.


## Other khub.ai github repos

  - [datasets](https://github.com/dev-khub-ai/datasets): this contains a number of datasets used in our experiments.
  - [arctest2025](https://github.com/dev-khub-ai/arctest2025): this contains the puzzles from the ARC-AGI-v2 dataset, with its JSon data refactored into textual form for ease of use with chatbots, as well as rendered images of the puzzles based on code posted by [Oleg X](https://www.kaggle.com/code/allegich/arc-2024-show-all-400-training-tasks).

## Related kHub articles

- [The Path from LLMs to the Knowledge-Centric Industry](https://www.linkedin.com/posts/kaihuchen_the-path-from-llms-to-the-knowledge-centric-activity-7304518124882579456-bWGc?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAHN2vgBBuFwWduk6vy4GHJTEpTEPOtSKe0)
- [The Knowledge Acquisition Bottleneck in the GenAI Era](https://www.linkedin.com/posts/kaihuchen_the-knowledge-acquisition-bottleneck-in-activity-7309754261846831104-OGbS?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAHN2vgBBuFwWduk6vy4GHJTEpTEPOtSKe0)
- [Improving the Knowledge Bottleneck in GenAI Applications with i3-learning](https://www.linkedin.com/posts/kaihuchen_improving-the-knowledge-bottleneck-in-genai-activity-7311920515034546176-3mXa?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAHN2vgBBuFwWduk6vy4GHJTEpTEPOtSKe0)


## Q&A

- **Q**: Can this be used to build a standalone Expert System, without the community hub?
  **A**: Certainly, and we'd encourage people to do so.
- **Q**: What's the business model here?
  **A**: There is none at this time. We want to build something useful first, then worry about business model later.
- **Q**: Aren't the so-called "plain text knowledge modules" simply LLM prompts?
  **A**: While it is not wrong to say so, it is perhaps missing the point. An LLM "prompt" is intended only as intial instructions to guide the inference process of an LLM chatbot. Unlike a kHub knowledge module, it is never intended to be a representation of complex knowledge, to be updated/generalized constantly, to be indexed for re-use, or persisted for use across sessions or even LLMs. 
- **Q**: How is the *inference-time learning* mentioned here differs from other methods with similar name (e.g., inference-time self-improrvement, test-time training, etc.)?
  **A**: it might be revealing to compare kHub's method with what's discussed in this paper: [A Survey on LLM Inference‑Time Self‑Improvement”, Dong et al., 2024](https://arxiv.org/html/2412.14352v1?utm_source=chatgpt.com)

| Dimension                     | **kHub** inference‑time learning                                                                               | ITSI methods catalogued by Dong et al.                                                                                            | Key contrast                                                  |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Primary aim**               | Capture expert knowledge as **persistent, reusable modules** that continually enrich the Knowledge Hub.           | Raise **per‑query answer quality** or efficiency for a fixed LLM by spending more compute or context at test‑time.   | System‑level knowledge growth vs. single‑response polishing.  |
| **Persistence of gains**      | New insights are stored outside the LLM and remain available to *any* future model.        | Improvements are mostly **ephemeral** (better decoding, temporary retrieval cache) and vanish when the session ends.              | Durable knowledge vs. transient heuristics.                   |
| **Human involvement**         | Domain experts teach concepts interactively; platform logs provenance and runs automated QA.                      | Largely **automatic**: self‑consistency voting, k‑NN aides, or model‑self‑critique need little or no human feedback. | Human‑centric loop vs. self‑contained algorithms.             |
| **Knowledge representation**  | **Explicit**: modules annotated with sources, scope, and versioning.                                              | **Implicit**: knowledge stays in token sequences, retrieval vectors, or hidden activations.                                       | Traceable artifacts vs. black‑box memories.                   |
| **Update mechanism**          | Writes to an external knowledge store; multiple LLMs can read it later (“model‑friendly, not model‑fixed”).       | No parameter change; relies on *runtime* tricks—e.g., reranking candidates, adding CoT prompts, storing k‑NN keys.                | Externalized learning vs. in‑context tweaks.                  |
| **Scope of concepts**         | Targets *hard, evolving* human domains (e.g., law, ethics, robotics) that demand provenance and revision control. | Benchmarks stress factual QA, reasoning puzzles, or code, where correctness is easier to score automatically.                     | Normative, safety‑critical domains vs. bounded tasks.         |
| **Taxonomy overlap**          | May **embed** ITSI components (retrieval, self‑reflection) inside agents for better per‑query reasoning.          | Survey groups techniques into **Independent**, **Context‑Aware**, and **Model‑Aided** self‑improvement classes.      | Complementary layers: kHub is a host; ITSI gives plug‑ins. |
| **Governance & auditability** | Built‑in provenance, conflict detection, version deprecation.                                                     | Governance rarely addressed beyond prompt‑level safety filters.                                                                   | Strong lifecycle management vs. minimal oversight.            |

<!-- [1]: https://arxiv.org/html/2412.14352v1?utm_source=chatgpt.com "A Survey on LLM Inference-Time Self-Improvement - arXiv"
[2]: https://arxiv.org/pdf/2412.14352?utm_source=chatgpt.com "[PDF] arXiv:2412.14352v1 [cs.CL] 18 Dec 2024"
[3]: https://arxiv.org/abs/2412.14352?utm_source=chatgpt.com "A Survey on LLM Inference-Time Self-Improvement" -->


<!-- 
- **Q**:
  **A** 
-->

   
