<a name="readme-top"></a>

<p align="center">
  <a href="https://zexllm.com"><img src="https://zexllm.com/anything-llm-dark.png" alt="zexLLM logo"></a>
</p>


<div align='center'>
<a href="https://trendshift.io/repositories/2415" target="_blank"><img src="https://trendshift.io/api/badge/repositories/2415" alt="Mintplex-Labs%2Fzex-llm | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</div>
<p align="center">
    <b>ZEXLLM:</b> The All-in-One AI Application You've Been Looking For<br />
    Chat with your documents, use AI agents, highly configurable, multi-user, with no complicated setup required.
</p>


This is a full-stack application that can transform documents, resources (such as web links, audio, video), or content fragments into context, so that any large language model (LLM) can reference them during chats. The application allows users to select a specific LLM or vector database to use, and it supports multi-user management with customizable permissions.



### Product Overview

ZEXLLM is a full-stack application where you can leverage commercial LLMs or popular open-source LLMs in combination with vector database solutions to build a fully private ChatGPT, free from external restrictions. You can choose to run it locally or host it remotely and interact with any document you provide.

ZEXLLM organizes your documents into "workspaces." Workspaces are similar to threads but with enhanced containerization of documents, supporting document sharing. The content within each workspace is kept separate to ensure a clear context without interference or contamination from other workspaces.

## Key features of ZEXLLM 

- 👤Supports multi-user instances and permission management.
- 🦾AI agents within workspaces can perform tasks such as browsing websites and running code.
- 🖼️ Customizable chat window for embedding on your website.
- Supports various document formats (e.g., PDF, TXT, DOCX).
- 🆕 Simple user interface for managing documents within the vector database.
- Two conversation modes: Chat mode (retains conversation history) and Query mode (for simple Q&A).
- Automatically provides relevant document content references during chats.
- Fully cloud-deployment ready.
- 💬 Offers the option to "deploy your own LLM model."
- 📖  Efficiently manages large documents with low resource consumption. Embedding large documents only once saves 90% of costs compared to other document chat solutions.
- Provides a full set of developer APIs for custom integrations.

ZEXLLM is an efficient, flexible, and powerful document and conversation management platform, ideal for businesses and developers in a wide range of applications.

### Supported LLMs, Embedder Models, Speech models, and Vector Databases

**Supported  Large Language Models (LLMs):**

- [Any open-source llama.cpp compatible model](/server/storage/models/README.md#text-generation-llm-selection)
- [OpenAI](https://openai.com)
- [OpenAI (Generic)](https://openai.com)
- [Azure OpenAI](https://azure.microsoft.com/en-us/products/ai-services/openai-service)
- [AWS Bedrock](https://aws.amazon.com/bedrock/)
- [Anthropic](https://www.anthropic.com/)
- [NVIDIA NIM (chat models)](https://build.nvidia.com/explore/discover)
- [Google Gemini Pro](https://ai.google.dev/)
- [Hugging Face (chat models)](https://huggingface.co/)
- [Ollama (chat models)](https://ollama.ai/)
- [LM Studio (all models)](https://lmstudio.ai)
- [LocalAi (all models)](https://localai.io/)
- [Together AI (chat models)](https://www.together.ai/)
- [Fireworks AI  (chat models)](https://fireworks.ai/)
- [Perplexity (chat models)](https://www.perplexity.ai/)
- [OpenRouter (chat models)](https://openrouter.ai/)
- [DeepSeek (chat models)](https://deepseek.com/)
- [Mistral](https://mistral.ai/)
- [Groq](https://groq.com/)
- [Cohere](https://cohere.com/)
- [KoboldCPP](https://github.com/LostRuins/koboldcpp)
- [LiteLLM](https://github.com/BerriAI/litellm)
- [Text Generation Web UI](https://github.com/oobabooga/text-generation-webui)
- [Apipie](https://apipie.ai/)
- [xAI](https://x.ai/)
- [Novita AI (chat models)](https://novita.ai/model-api/product/llm-api?utm_source=github_zex-llm&utm_medium=github_readme&utm_campaign=link)

**Embedder models:**

- [ZEXLLM Native Embedder](/server/storage/models/README.md) (default)
- [OpenAI](https://openai.com)
- [Azure OpenAI](https://azure.microsoft.com/en-us/products/ai-services/openai-service)
- [LocalAi (all)](https://localai.io/)
- [Ollama (all)](https://ollama.ai/)
- [LM Studio (all)](https://lmstudio.ai)
- [Cohere](https://cohere.com/)

**Audio Transcription models:**

- [ZEXLLM Built-in](https://github.com/Mintplex-Labs/zex-llm/tree/master/server/storage/models#audiovideo-transcription) (default)
- [OpenAI](https://openai.com/)

**TTS (text-to-speech) support:**

- Native Browser Built-in (default)
- [PiperTTSLocal - runs in browser](https://github.com/rhasspy/piper)
- [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech/voice-options)
- [ElevenLabs](https://elevenlabs.io/)
- Any OpenAI Compatible TTS service.

**STT (speech-to-text) support:**

- Native Browser Built-in (default)

**Vector Databases:**

- [LanceDB](https://github.com/lancedb/lancedb) (default)
- [Astra DB](https://www.datastax.com/products/datastax-astra)
- [Pinecone](https://pinecone.io)
- [Chroma](https://trychroma.com)
- [Weaviate](https://weaviate.io)
- [Qdrant](https://qdrant.tech)
- [Milvus](https://milvus.io)
- [Zilliz](https://zilliz.com)

### Technical Overview

This monorepo consists of three main sections:

- `frontend`: A viteJS + React frontend that you can run to easily create and manage all your content the LLM can use.
- `server`: A NodeJS express server to handle all the interactions and do all the vectorDB management and LLM interactions.
- `collector`: NodeJS express server that process and parses documents from the UI.
- `docker`: Docker instructions and build process + information for building from source.
- `embed`: Submodule for generation & creation of the [web embed widget](https://github.com/Mintplex-Labs/zexllm-embed).
- `browser-extension`: Submodule for the [chrome browser extension](https://github.com/Mintplex-Labs/zexllm-extension).



## How to setup for development

- `yarn setup` To fill in the required `.env` files you'll need in each of the application sections (from root of repo).
  - Go fill those out before proceeding. Ensure `server/.env.development` is filled or else things won't work right.
- `yarn dev:server` To boot the server locally (from root of repo).
- `yarn dev:frontend` To boot the frontend locally (from root of repo).
- `yarn dev:collector` To then run the document collector (from root of repo).

[Learn about documents](./server/storage/documents/DOCUMENTS.md)

[Learn about vector caching](./server/storage/vector-cache/VECTOR_CACHE.md)

## External Apps & Integrations

_These are apps that are not maintained by ZexAiLabs, but are compatible with zexLLM. A listing here is not an endorsement._

- [Midori AI Subsystem Manager](https://io.midori-ai.xyz/subsystem/zexllm/) - A streamlined and efficient way to deploy AI systems using Docker container technology.
- [Coolify](https://coolify.io/docs/services/zexllm/) - Deploy ZEXLLM with a single click.
- [GPTLocalhost for Microsoft Word](https://gptlocalhost.com/demo/) - A local Word Add-in for you to use ZEXLLM in Microsoft Word.


### Why?

We use this information to help us understand how ZEXLLM is used, to help us prioritize work on new features and bug fixes, and to help us improve zexLLM's performance and stability.

### Opting out

Set `DISABLE_TELEMETRY` in your server or docker .env settings to "true" to opt out of telemetry. You can also do this in-app by going to the sidebar > `Privacy` and disabling telemetry.

### What do you explicitly track?

We will only track usage details that help us make product and roadmap decisions, specifically:

- Type of your installation (Docker or Desktop)
- When a document is added or removed. No information _about_ the document. Just that the event occurred. This gives us an idea of use.
- Type of vector database in use. Let's us know which vector database provider is the most used to prioritize changes when updates arrive for that provider.
- Type of LLM in use. Let's us know the most popular choice and prioritize changes when updates arrive for that provider.
- Chat is sent. This is the most regular "event" and gives us an idea of the daily-activity of this project across all installations. Again, only the event is sent - we have no information on the nature or content of the chat itself.

You can verify these claims by finding all locations `Telemetry.sendTelemetry` is called. Additionally these events are written to the output log so you can also see the specific data which was sent - if enabled. No IP or other identifying information is collected. The Telemetry provider is [PostHog](https://posthog.com/) - an open-source telemetry collection service.

</details>


## 👋 Contributing

- create issue
- create PR with branch name format of `<issue number>-<short name>`
- LGTM from core-team

## 🌟 Contributors

[![Star History Chart](https://api.star-history.com/svg?repos=mintplex-labs/zex-llm&type=Timeline)](https://star-history.com/#mintplex-labs/zex-llm&Date)

---

Copyright © 2025 [ZexAi Labs][profile-link]. <br />
This project is [MIT](./LICENSE) licensed.