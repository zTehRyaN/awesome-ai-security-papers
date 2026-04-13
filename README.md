# Awesome AI Security Papers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated, up-to-speed reading list of the most impactful papers and blog posts in AI Security — with a primary focus on GenAI/LLM security, but also covering ML security and privacy at large.

This is not meant to be an exhaustive collection. It is a personal selection of the readings that left the strongest mark after going through dozens of papers, preprints, and deep dives every week. If someone asks you *"I want to access the GenAI/LLM security field, what resources could you point me to?"*, this repository aims to be the link that I'd share.

## Contents
- [Adversarial Attacks & Red Teaming](#adversarial-attacks--red-teaming)
- [Prompt Injection & Jailbreaking](#prompt-injection--jailbreaking)
- [Privacy, Data Poisoning & Extraction](#privacy-data-poisoning--extraction)
- [Guardrails, Filtering & Defense](#guardrails-filtering--defense)
- [Agent Security & Tool-Use Risks](#agent-security--tool-use-risks)
- [Emerging Topics & Miscellaneous](#emerging-topics--miscellaneous)

## Adversarial Attacks & Red Teaming

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |
| 2025 | [When Names Disappear: Revealing What LLMs Actually Understand About Code](https://www.alphaxiv.org/abs/2510.03178v1) | Introduces a suite of semantics-preserving identifier obfuscations and the ClassEval-Obf benchmark to separate structural semantics from human-interpretable naming, showing that LLMs rely heavily on identifier names for intent summarization and that name cues can enable memorization shortcuts that inflate execution benchmark scores. <br><br> _"Identifier names anchor memorized code–output pairs in training data; obfuscation disrupts this shortcut and pushes the model toward execution reasoning."_ |
| 2024 | [Black-Box Adversarial Attacks on LLM-Based Code Completion](https://www.alphaxiv.org/abs/2408.02509) | Introduces INSEC, a black-box attack that stealthily injects crafted short comment strings via a query-based optimization to bias LLM code-completion engines toward insecure code. The attack raises insecure generation rates by over 50% across 16 CWEs and 5 languages on both open-source models and commercial services (e.g., OpenAI API, GitHub Copilot), is low-cost (under $10) to develop, and is demonstrated via an IDE plugin. <br><br> _"INSEC increases the rate of generated insecure code by more than 50% while maintaining the functional correctness of generated code."_ |
| 2023 | [Explore, Establish, Exploit: Red Teaming Language Models from Scratch](https://www.alphaxiv.org/abs/2306.09442) | Presents a three-stage "Explore, Establish, Exploit" framework for red-teaming LMs without preexisting failure classifiers and applies it to find inputs that induce false claims in GPT-3. Introduces the CommonClaim dataset of 20,000 human-labeled statements and releases code and data to support tailored red-teaming. <br><br> _"red-teaming 'from scratch,' in which the adversary does not begin with a way to classify failures."_ |
| 2023 | [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://www.alphaxiv.org/abs/2307.15043) | Introduces Greedy Coordinate Gradient (GCG), an automated discrete optimization that finds universal adversarial suffixes which reliably jailbreak aligned LLMs and transfer to many black-box models; evaluated on a new AdvBench benchmark it achieves near-perfect ASRs on open models and substantial transfer to GPT-3.5, GPT-4, PaLM-2, Claude, Bard, and others. <br><br> _"Our attack constructs a single adversarial prompt that consistently circumvents the alignment of state-of-the-art commercial models including ChatGPT, Claude, Bard, and Llama-2."_ |
| 2022 | [Red Teaming Language Models with Language Models](https://www.alphaxiv.org/abs/2202.03286) | This paper uses language models to automatically generate red-team test cases that expose harmful behaviors in target LMs, uncovering tens of thousands of offensive replies in a 280B parameter chatbot. It evaluates generation methods from zero-shot to reinforcement learning and applies prompt engineering to reveal diverse harms including privacy leakage, offensive group mentions, and multi-turn conversational failures. <br><br> _"LM-based red teaming is one promising tool (among many needed) for finding and fixing diverse, undesirable LM behaviors before impacting users."_ |

## Prompt Injection & Jailbreaking

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |
| 2026 | [LLM Code Reviewers Are Harder to Fool Than You Think: Adversarial Comments Fail Where Vulnerability Patterns Succeed](https://www.alphaxiv.org/abs/2602.16741v1) | Large-scale empirical study (100 samples, 8 comment variants, 8 models, 14,012 evaluations) showing embedded adversarial comments have a minimal, statistically non-significant effect on LLM vulnerability detection. SAST cross-referencing substantially improves detection and recovers many baseline misses (96.9% detection, 47% recovery) while comment stripping can degrade performance; the authors conclude the main risk is hard vulnerability classes (race conditions, timing attacks, complex authorization) rather than comment-based manipulation. <br><br> _"The real threat to AI code review isn’t adversarial comments. It’s the inherent difficulty of certain vulnerability patterns—race conditions, timing attacks, complex authorization logic—that models miss regardless of what the comments say."_ |
| 2024 | [Jailbreaking Leading Safety-Aligned LLMs with Simple Adaptive Attacks](https://www.alphaxiv.org/abs/2404.02151v4) | Demonstrates simple, model-specific adaptive jailbreaks—combining a hand-crafted prompt template, logprob-guided random search for adversarial suffixes, self-transfer, and prefilling—that achieve 100% attack success rates on many leading safety-aligned LLMs (GPT-3.5/4o, Claude 2/3/3.5, Llama-2/3, Gemma, Mistral, R2D2, etc.). Provides broad evaluations on open-source and proprietary models and argues adaptive attacks are essential for reliable robustness assessment. <br><br> _"Adaptive attacks are crucial for accurate robustness evaluations of LLMs."_ |
| 2023 | [Jailbreaking ChatGPT via Prompt Engineering: An Empirical Study](https://www.alphaxiv.org/abs/2305.13860) | This paper classifies jailbreak prompt patterns, evaluates 3,120 jailbreaks across ChatGPT 3.5 and 4.0 in eight prohibited scenarios, and shows how prompt structure enables constraint bypassing. <br><br> _"The prompts can consistently evade the restrictions in 40 use-case scenarios."_ |
| 2023 | [Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection](https://www.alphaxiv.org/abs/2302.12173) | Introduces "Indirect Prompt Injection", showing attackers can inject prompts into retrieved data to override instructions, exfiltrate data, execute arbitrary actions, and compromise real-world LLM-integrated systems. Presents a taxonomy of impacts (data theft, worming, information ecosystem contamination) and demonstrates practical attacks against services like Bing's GPT-4 chat and code-completion engines, highlighting the lack of effective mitigations. <br><br> _"LLM-Integrated Applications blur the line between data and instructions."_ |

## Privacy, Data Poisoning & Extraction

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |
| 2024 | [TrojanPuzzle: Covertly Poisoning Code-Suggestion Models](https://www.alphaxiv.org/abs/2301.02344) | Demonstrates two novel data-poisoning attacks against code-suggestion models: Covert embeds malicious payloads in comments/docstrings to evade static-analysis filters, and TrojanPuzzle omits key payload tokens from the training data and teaches substitution patterns so the model reconstructs the full malicious code at completion. The paper evaluates both attacks on CodeGen models across multiple real-world CWEs, reports substantial attack@k success rates, and shows that simple dataset filtering and fine-pruning defenses are insufficient. <br><br> _"TrojanPuzzle is the first poisoning attack that only reveals a specific subset of the malicious payload in the poison data yet still achieves the same attack objective."_ |
| 2023 | [Poisoning Web-Scale Training Datasets Is Practical](https://www.alphaxiv.org/abs/2302.10149v2) | Introduces two practical poisoning vectors—split-view (buying expired domains to change indexed URLs) and frontrunning (timing edits to snapshotting processes like Wikipedia)—and demonstrates feasibility across 10 popular web-scale datasets, including experiments showing model corruption at realistic budgets. Proposes low-overhead mitigations such as cryptographic integrity verification and randomized or time-gated snapshots. <br><br> _"For just $60 USD, we could have poisoned 0.01% of the LAION-400M or COYO-700M datasets in 2023."_ |
| 2020 | [Extracting Training Data from Large Language Models](https://www.alphaxiv.org/abs/2012.07805) | This paper shows that adversaries can extract verbatim training examples from large language models by querying them, recovering hundreds of sequences including personally identifiable information, IRC conversations, code, and UUIDs. It evaluates factors that affect extraction success and discusses defenses and safeguards. <br><br> _"Worryingly, we find that larger models are more vulnerable than smaller models."_ |

## Guardrails, Filtering & Defense

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |
| 2024 | [SmoothLLM: Defending Large Language Models Against Jailbreaking Attacks](https://www.alphaxiv.org/abs/2310.03684v4) | Introduces SmoothLLM, a black-box randomized perturbation-and-aggregation wrapper that defends LLMs against suffix-based jailbreaks without retraining and empirically reduces attack success rates for GCG, PAIR, RandomSearch, and AmpleGCG across multiple models. The paper also gives closed-form probabilistic guarantees under an instability assumption, evaluates adaptive attacks, and characterizes the trade-off between robustness, nominal performance, and query efficiency. <br><br> _"Adversarially-generated prompts are brittle to character-level changes."_ |
| 2024 | [RigorLLM: Resilient Guardrails for Large Language Models against Undesired Content](https://www.alphaxiv.org/abs/2403.13031) | Proposes RigorLLM, which uses energy-based (Langevin) training data augmentation, minimax optimization of a safe suffix, and a fusion model combining robust KNN with LLMs to enforce guardrails. Experimental results show it outperforms OpenAI and Perspective APIs at harmful-content detection and is highly resilient to jailbreaking attacks. <br><br> _"RigorLLM exhibits unparalleled resilience to jailbreaking attacks."_ |
| 2023 | [Llama Guard: LLM-based Input-Output Safeguard for Human-AI Conversations](https://www.alphaxiv.org/abs/2312.06674) | This paper introduces Llama Guard, an instruction-finetuned Llama2-7b model and a safety-risk taxonomy for classifying both prompts and model responses, and releases a ~14k annotated prompt-response dataset and model weights. Llama Guard achieves strong in-domain performance and adapts via zero-/few-shot prompting or fine-tuning to external taxonomies, matching or outperforming existing moderation APIs on ToxicChat and the OpenAI moderation evaluation. |

## Agent Security & Tool-Use Risks

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |
| 2026 | [The Attack and Defense Landscape of Agentic AI: A Comprehensive Survey](https://www.alphaxiv.org/abs/2603.11088v1) | This paper provides the first comprehensive systematization of agentic AI security, surveying agent design dimensions, a taxonomy of attack vectors and risks, and a defense-in-depth landscape with concrete case studies. It introduces seven design dimensions, maps threats to defenses, and highlights practical gaps in real-world agents (e.g., AutoGPT) while identifying open research challenges. <br><br> _"We present the first systematic framework for understanding the security risks and defense strategies of AI agents."_ |
| 2023 | [Identifying the Risks of LM Agents with an LM-Emulated Sandbox](https://www.alphaxiv.org/abs/2309.15817) | Introduces ToolEmu, an LM-based tool emulator and automatic safety evaluator that enables large-scale testing of LM agents across diverse tools and scenarios without manual setup, and provides a benchmark of 36 high-stakes tools and 144 test cases. Reports that 68.8% of emulator-identified failures correspond to real-world agent failures and that even the safest agent fails 23.9% of the time. <br><br> _"Even the safest LM agent exhibits failures 23.9% of the time according to our evaluator."_ |

## Emerging Topics & Miscellaneous

| Year | Paper | Key Takeaways & Description |
| :--- | :---- | :-------------------------- |

---

## Contribute

Contributions are welcome. Please ensure your submission fully follows the requirements outlined in [`CONTRIBUTING.md`](CONTRIBUTING.md), including formatting, scope alignment, and category placement.

Pull requests that do not adhere to the contribution guidelines may be closed.

## License

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This repository is licensed under the [MIT License](LICENSE).
