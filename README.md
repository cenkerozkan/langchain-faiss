# langchain-faiss

A standalone LangChain integration package for [FAISS](https://github.com/facebookresearch/faiss) (Facebook AI Similarity Search), extracted from `langchain-community` for continued maintenance and long-term support.

---

## Background

### The langchain-community Sunset

The [`langchain-community`](https://github.com/langchain-ai/langchain-community) repository, which served as the central hub for all third-party LangChain integrations, has been officially marked as **no longer maintained** by the LangChain OSS team (see [issue #674](https://github.com/langchain-ai/langchain-community/issues/674)).

The reason is straightforward: the repository grew too large to govern effectively. With hundreds of integrations maintained by contributors with varying levels of commitment, the codebase became difficult to test, release, and keep consistent. Bugs would linger, dependencies would go stale, and the sheer size of the package meant users had to install a heavy dependency just to use a single integration.

### The New Direction: Standalone Integration Packages

The LangChain team's answer to this was to encourage the community to move integrations into their own dedicated packages — `langchain-{name}` — following the pattern already established by first-party packages like `langchain-openai` and `langchain-anthropic`. This approach offers several concrete advantages:

- **Independent versioning**: each integration can be released and patched on its own schedule.
- **Isolated dependencies**: users only install what they actually need.
- **Clearer ownership**: a dedicated maintainer owns the package end-to-end.
- **Better testability**: a focused package is easier to test thoroughly.

The official LangChain contribution guide provides a [template repository](https://github.com/langchain-ai/integration-repo-template) and a [how-to guide](https://python.langchain.com/docs/contributing/how_to/integrations/from_template/) for creating these standalone packages.

---

## Why langchain-faiss?

FAISS is one of the most widely used vector stores in the LangChain ecosystem. It is fast, runs locally without any external service, and is well-suited for prototyping and production workloads that do not require a managed vector database. The integration, currently living at `langchain_community.vectorstores.faiss`, is used in countless RAG pipelines and semantic search applications.

With `langchain-community` being sunset, the FAISS integration has no official standalone home. Rather than waiting for it to disappear or become unmaintained, this package was created to:

1. Preserve the FAISS integration as a dedicated, installable package (`pip install langchain-faiss`).
2. Keep it compatible with current and future versions of `langchain-core`.
3. Provide a single, focused place to track issues, improvements, and releases specifically related to FAISS.

---

## What is FAISS?

FAISS (Facebook AI Similarity Search) is a library developed by Meta AI Research for efficient similarity search and clustering of dense vectors. It is designed to handle very large collections of vectors and supports both CPU and GPU execution.

In the context of LangChain, FAISS is used as a **vector store**: a data structure that stores document embeddings and enables fast nearest-neighbor retrieval, which is the core operation behind Retrieval-Augmented Generation (RAG).

---

## Status

This package is currently in early development. The goal is to provide a drop-in replacement for `langchain_community.vectorstores.faiss` with minimal migration friction.
