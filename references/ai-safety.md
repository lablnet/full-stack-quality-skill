# AI/LLM Feature Safety Standards

Use for prompts, RAG, tools, agents, evals, generated content, and model-backed features.

- Define model inputs, outputs, allowed tools, and failure behavior.
- Do not send unnecessary secrets, PII, or private data to models.
- Treat retrieved content and user content as untrusted.
- Add evals or regression cases for important prompt behavior.
- Gate destructive or external side-effect tools behind explicit approval.
- Log enough for debugging without storing sensitive prompts/responses unnecessarily.

Review smells: prompt injection ignored, tools can mutate state without approval, no evals, private data sent unnecessarily, generated output trusted as fact.
