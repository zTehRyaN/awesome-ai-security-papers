# Contributing to Awesome AI Security Papers

Thank you for your interest in contributing to this curated list of AI Security research.

I welcome milestone papers and a small number of complementary learning resources. Paper contributions must follow the table format below; courses, tutorials, and explanatory guides belong in the separate Learning Resources section.

## How to Add a Paper

### 1. The PR Workflow
1. **Fork the repository**.
2. **Create a new branch** (`git checkout -b add-paper-title`).
3. **Make your edits** to `README.md` following the exact template below.
4. **Submit a Pull Request** with a brief explanation of why this paper is a milestone or highly relevant.

### 2. The Exact Entry Format

Add your paper as a new row in the relevant category table in `README.md`. Copy and paste the following structure, replacing the bracketed text:

```markdown
| [YYYY] | [Paper Title](URL) | [1-2 sentence description.] <br><br> _"[Optional short quote or key takeaway]"_ |
```

**Example:**
```markdown
| 2023 | [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://www.alphaxiv.org/abs/2307.15043) | This paper demonstrates suffix-based adversarial attacks that bypass aligned LLM safety mechanisms across multiple models. <br><br> _"A simple concatenation of adversarial tokens can reliably jailbreak multiple production LLMs."_ |
```

### 3. Category Rules

Place the paper under one of the six categories:
- **Adversarial Attacks & Red Teaming**: adversarial examples, evasion attacks, red-teaming methodologies, robustness evaluations.
- **Prompt Injection & Jailbreaking**: direct/indirect prompt injection, jailbreak techniques, guardrail bypass.
- **Privacy, Data Poisoning & Extraction**: training data extraction, membership inference, model inversion, backdoor attacks, data poisoning, differential privacy.
- **Guardrails, Filtering & Defense**: alignment-based defenses, content filtering, safety fine-tuning, detection systems, watermarking.
- **Agent Security & Tool-Use Risks**: agentic AI attack surfaces, tool-calling vulnerabilities, multi-agent exploitation, sandboxing.
- **Emerging Topics & Miscellaneous**: everything else that doesn't fit above (e.g. AI governance/policy, supply chain attacks, novel threat models).

### 4. Quality Guidelines

- **High Quality**: Papers must be significant milestones or highly relevant to AI security. Avoid highly niche or low-effort preprints.
- **Concise Descriptions**: Keep the description to 1-2 plain English sentences. Explain *what* it does and why it matters.
- **Provide Context**: Only if there is a genuinely impactful quote or takeaway, append it with `<br><br> _"Quote text"_`. If there is no standout insight, omit the quote entirely.
- **Working Links**: Ensure your link resolves correctly to the paper (e.g., arXiv, Nature, or the primary blog post).

## How to Suggest a Learning Resource

Use a pull request with a brief explanation of the resource's value and its overlap with existing entries.

- Follow the existing `Resource | Format / starting point | Why choose it` table under the appropriate learning subsection.
- Distinguish safety and alignment, security of AI systems, and evaluation of AI capabilities. State the intended scope rather than presenting them as interchangeable.
- Prefer freely accessible original resources. Give a useful entry point and any prerequisite knowledge, rather than adding an entire catalog.
- Keep dated evaluation results in context. Do not equate benchmark success, model alignment, or the presence of guardrails with demonstrated security.
- Avoid duplicate introductions, vendor marketing without technical substance, personal completion claims, and private bootcamp or application materials.
- Keep learning entries separate from the six paper categories. Paper formatting, category placement, and year ordering remain unchanged.
- Check links and descriptions, and keep descriptions concise and in English.

Thanks for contributing.
