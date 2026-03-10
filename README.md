# Knowledge Pipeline Prompts

A collection of eight structured AI prompt templates that form a five-stage workflow for turning raw papers, videos, and lectures into processed, actionable knowledge.

Built for knowledge workers who consume large volumes of information — researchers, analysts, students, or anyone who needs to process more than they can read.

---

## The Pipeline

Each prompt handles one stage of the workflow. The stages are designed to be used in sequence, though each prompt works independently.

| Stage | Purpose | Prompts |
|-------|---------|---------|
| 01 Triage | Decide if a paper is worth reading in full | `research_summary.md` |
| 02 Summarise | Extract signal from videos and lectures | `yt_transcript_summary.md`, `lecture_study.md` |
| 03 Audit | Challenge and validate what you just processed | `auditor.md`, `reproducibility_audit.md` |
| 04 Test | Verify you actually understood the material | `questions.md` |
| 05 Benchmark | Map your skills against real job requirements | `reverse_job_resume.md` |

A meta-layer prompt (`prompt_optimizer.md`) sits above the pipeline and is used to refine any rough prompt ideas before use.

---

## Folder Structure

```
knowledge-pipeline-prompts/
├── README.md
├── LICENSE
├── analysis/
│   ├── auditor.md              # Logic auditing and stress-testing arguments
│   ├── lecture_study.md        # Processing lecture transcripts and Coursera videos
│   ├── research_summary.md     # Rapid triage and deep extraction from research papers
│   └── yt_transcript_summary.md # Decoding YouTube video transcripts
├── generation/
│   ├── prompt_optimizer.md     # Rewriting rough prompt ideas into clean instructions
│   └── reverse_job_resume.md   # Reverse-engineering job descriptions into resume profiles
└── evaluation/
    ├── questions.md            # Generating high-level questions from any source material
    └── reproducibility_audit.md # Auditing research papers for reproducibility standards
```

---

## How to Use

Each prompt is a standalone instruction set. Copy the contents of the relevant `.md` file and paste it into your AI assistant of choice (Claude, GPT-4, Gemini, etc.) as the system prompt or opening instruction, then follow up with your source material.

### Recommended workflow

**For a research paper:**
1. Run `analysis/research_summary.md` — quick triage, extract core findings
2. Run `evaluation/reproducibility_audit.md` — check if the methods hold up
3. Run `evaluation/questions.md` — test your understanding

**For a YouTube video:**
1. Run `analysis/yt_transcript_summary.md` — strip filler, extract argument and evidence
2. Run `analysis/auditor.md` — get the counter-arguments and blind spots

**For a lecture or Coursera video:**
1. Run `analysis/lecture_study.md` before watching for context, or after to check for gaps
2. Run `evaluation/questions.md` for active recall

**For career benchmarking:**
1. Find a job description you are interested in
2. Run `generation/reverse_job_resume.md` — see yourself as High, Medium, and Borderline match
3. Use the gap analysis to decide what to learn next

---

## Prompt Design Principles

All prompts in this collection follow the same conventions:

- **Role declaration** — each prompt defines a specific expert persona
- **Input type** — each prompt states exactly what kind of content it expects
- **Interaction rule** — each prompt handles missing input gracefully
- **Zero-fluff output** — no "the author says" or "in this video" preamble in any output
- **Structured output** — all prompts produce consistent, scannable formats

---

## Background

These prompts emerged from a practical problem: three-plus years working in research generates an unmanageable backlog of papers, videos, and lectures. The prompts were built iteratively to solve specific bottlenecks in that workflow, then mapped into a coherent five-stage pipeline.

The `reproducibility_audit.md` prompt is bioinformatics-specific by default (referencing FAIR principles, COUSS, and ISO/TS 22692). All other prompts are domain-agnostic and work equally well in any research, academic, or knowledge-intensive field.

For the full story behind this system, see the accompanying blog post:
[The 8-Prompt System That Turns Raw Papers, Videos, and Lectures Into Structured Knowledge](#) *(link to be updated on publication)*

---

## Contributing

Improvements, adaptations, and new prompt suggestions are welcome. If you extend a prompt for a specific domain (e.g., law, medicine, economics), feel free to open a pull request.

When contributing:
- Follow the existing prompt structure (Role, Input Type, Interaction Rule, Output Format)
- Keep output format sections explicit and scannable
- Do not add emojis or decorative formatting to prompt files

---

## License

This work is licensed under the Creative Commons Attribution 4.0 International License.
You are free to use, adapt, and redistribute these prompts for any purpose, provided you give appropriate credit.

See [LICENSE](./LICENSE) for full terms.
