# AI-103 study guide and practice questions

Exam AI-103, Developing AI Apps and Agents on Azure, is for developers who build, deploy, and run generative AI apps and agents on Microsoft Foundry and who already write Python. Passing it earns the Microsoft Certified: Azure AI Apps and Agents Developer Associate certification, which replaced the Azure AI Engineer Associate (AI-102) on June 30, 2026. This repository holds a study guide built on the official skills outline, a six week study plan, a cheat sheet, links to free Microsoft resources, and 15 original practice questions with explained answers.

> Unofficial study notes by [Examice](https://examice.com/exams/microsoft/ai-103?utm_source=github&utm_medium=social&utm_campaign=ai-103-study-guide-and-practice-questions&utm_content=link_1). Not affiliated with or endorsed by Microsoft. The practice questions are original, written for this guide, and not taken from the exam.

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [What the exam covers](#what-the-exam-covers)
- [Study plan](#study-plan)
- [Cheat sheet](#cheat-sheet)
- [Free official resources](#free-official-resources)
- [Practice questions](#practice-questions)
- [Exam day tips](#exam-day-tips)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## Exam at a glance

| Item | Official detail |
| --- | --- |
| Exam | AI-103: Developing AI Apps and Agents on Azure |
| Certification earned | Microsoft Certified: Azure AI Apps and Agents Developer Associate |
| Level | Intermediate |
| Expected background | Experience building apps in Python, plus familiarity with general AI, generative AI, and Azure services |
| Time to complete | 120 minutes |
| Passing score | 700 on a scaled range of 1–1,000 |
| Price | $165 in the United States; the price depends on the country or region where you take the exam |
| Languages | English, Chinese (Simplified), Chinese (Traditional), French, German, Japanese, Korean, Italian, Portuguese (Brazil), and Spanish |
| Delivery | Proctored, scheduled through Pearson VUE; the exam may include interactive components |
| Skills outline | Version dated April 16, 2026 |
| Renewal | Expires after one year; renew for free by passing an online assessment on Microsoft Learn during the six month window before it expires |
| Retakes | Wait 24 hours after a first failed attempt, then 14 days between later attempts, with at most 5 attempts in 12 months |
| Replaces | AI-102 and the Azure AI Engineer Associate certification, both retired on June 30, 2026 |

Sources: the [AI-103 certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-ai-apps-and-agents-developer-associate/), the [AI-103 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103), [exam scoring](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports), the [retake policy](https://learn.microsoft.com/en-us/credentials/support/retake-policy), [certification renewal](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification), and Microsoft's [retirement announcement](https://techcommunity.microsoft.com/blog/skills-hub-blog/the-ai-job-boom-is-here-are-you-ready-to-showcase-your-skills/4494128) of March 3, 2026, checked October 28, 2026. The price is the US figure on the certification page; pick your country there to see yours.

## What the exam covers

| Domain | Weight |
| --- | --- |
| [Plan and manage an Azure AI solution](#plan-and-manage-an-azure-ai-solution-2530) | 25–30% |
| [Implement generative AI and agentic solutions](#implement-generative-ai-and-agentic-solutions-3035) | 30–35% |
| [Implement computer vision solutions](#implement-computer-vision-solutions-1015) | 10–15% |
| [Implement text analysis solutions](#implement-text-analysis-solutions-1015) | 10–15% |
| [Implement information extraction solutions](#implement-information-extraction-solutions-1015) | 10–15% |

The weights come from the [study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103). Microsoft says most questions cover generally available features, and some cover preview features that are in common use. Foundry changes fast, so learn each concept first and then check the current name in the docs.

### Plan and manage an Azure AI solution (25–30%)

- **Choose models and services.** Match each task to a model type: a large language model for open reasoning, a small language model when a compact model is enough, a multimodal model for image or audio input, or a Foundry Tool (Speech, Language, Translator, Content Understanding) when a dedicated API fits. Pick a retrieval approach (keyword, vector, hybrid, or semantic ranking) and decide how agents get tools, knowledge, and memory. Docs: [What is Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/what-is-foundry), [Foundry Models overview](https://learn.microsoft.com/en-us/azure/foundry/concepts/foundry-models-overview), [Foundry IQ](https://learn.microsoft.com/en-us/azure/foundry/agents/concepts/what-is-foundry-iq).
- **Set up AI solutions in Foundry.** One Foundry resource holds your projects, model deployments, access control, and networking. Choose a deployment option and type, configure model and agent deployments, and wire projects into CI/CD with Bicep or Terraform and automated evaluations. Docs: [Deployment overview](https://learn.microsoft.com/en-us/azure/foundry/concepts/deployments-overview), [Deployment types](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/concepts/deployment-types), [Create projects](https://learn.microsoft.com/en-us/azure/foundry/how-to/create-projects), [Run evaluations in GitHub Actions](https://learn.microsoft.com/en-us/azure/foundry/how-to/evaluation-github-action).
- **Manage, monitor, and secure.** Quota is assigned in tokens per minute (TPM) per subscription, region, and model, and each deployment also gets a requests per minute (RPM) limit. Track cost and scale, monitor model quality, safety events, grounding, and search index health, and secure everything with Microsoft Entra ID (keyless) authentication, managed identities, private networking, and Azure RBAC. Docs: [Manage Azure OpenAI quota](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/quota), [Monitor model deployments](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/how-to/monitor-models), [Configure keyless authentication](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/how-to/configure-entra-id), [Configure network isolation](https://learn.microsoft.com/en-us/azure/foundry/how-to/configure-private-link), [RBAC for Foundry](https://learn.microsoft.com/en-us/azure/foundry/concepts/rbac-foundry).
- **Implement responsible AI.** Configure guardrails for harmful content, prompt attacks, groundedness, protected material, and personal data. Measure risk with safety evaluators and the AI red teaming agent, keep an audit trail with tracing, and limit what agents can do with tool restrictions and approval steps. Docs: [Guardrails overview](https://learn.microsoft.com/en-us/azure/foundry/guardrails/guardrails-overview), [Evaluators reference](https://learn.microsoft.com/en-us/azure/foundry/concepts/built-in-evaluators), [AI red teaming agent](https://learn.microsoft.com/en-us/azure/foundry/concepts/ai-red-teaming-agent), [Agent tracing](https://learn.microsoft.com/en-us/azure/foundry/observability/concepts/trace-agent-concept).

### Implement generative AI and agentic solutions (30–35%)

- **Build generative applications.** Deploy LLMs, small models, code models, and multimodal models, then call them from Python through the project endpoint with the Foundry SDK, which gives you an OpenAI client for the Responses API. Implement RAG, design flows that call tools over several steps, and evaluate apps for fabrication, relevance, quality, and safety. Docs: [Foundry SDK quickstart](https://learn.microsoft.com/en-us/azure/foundry/quickstarts/get-started-code), [Endpoints for Foundry Models](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/concepts/endpoints), [RAG in Foundry](https://learn.microsoft.com/en-us/azure/foundry/concepts/retrieval-augmented-generation), [Evaluation overview](https://learn.microsoft.com/en-us/azure/foundry/concepts/evaluation-overview).
- **Build agents.** Foundry Agent Service runs prompt agents (instructions, a model, and tools defined as configuration) and hosted agents (your own code in a container). Define each agent's role, goals, conversation handling, and tool schemas; add retrieval, function calling, and memory; orchestrate several agents; and put approval steps in front of risky actions. Then monitor and evaluate the deployed agents. Docs: [Agent Service overview](https://learn.microsoft.com/en-us/azure/foundry/agents/overview), [Function calling](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/function-calling), [MCP tools](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/model-context-protocol), [Agent Framework orchestrations](https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/), [Agent evaluators](https://learn.microsoft.com/en-us/azure/foundry/concepts/evaluation-evaluators/agent-evaluators).
- **Optimize and operationalize.** Tune prompts and model parameters, add reflection or critique steps, trace runs, track tokens, safety signals, and latency, and route work across several models or between a model and a rules engine. Docs: [Prompt engineering](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering), [System message design](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/advanced-prompt-engineering), [Observability](https://learn.microsoft.com/en-us/azure/foundry/concepts/observability), [Model router](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/model-router).

Foundry workflows, the visual builder for agent sequences, retire on December 1, 2026, and the docs send new orchestration work to Microsoft Agent Framework ([source](https://learn.microsoft.com/en-us/azure/foundry/agents/concepts/workflow)).

### Implement computer vision solutions (10–15%)

- **Generate and edit images and video.** Create images from text and reference images, edit part of an image with a mask (inpainting), and generate or remix video from text and images. Docs: [Image generation](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/dall-e), [Video generation (preview)](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/video-generation).
- **Build multimodal understanding workflows.** Send images to vision models for short or detailed captions, alt text, and answers grounded in what the image shows. Use Content Understanding analyzers to pull visual attributes from images and segments from video. Docs: [Images in chat prompts](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/gpt-with-vision), [Content Understanding for images](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/image/overview), [Content Understanding for video](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/video/overview).
- **Apply responsible AI to visual content.** Filter unsafe images, defend against instructions hidden in text inside images, and enforce visual policies such as watermarks and brand rules. Docs: [Harm categories and severity levels](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/content-filter-severity-levels), [Prompt Shields](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/content-filter-prompt-shields), [Azure AI Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview).

Two changes to know. Azure Vision Image Analysis (versions 3.2 and 4.0) retires on September 25, 2028, and Microsoft's [migration guide](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/migration-options) points to generative models and Content Understanding. The study guide also names Content Understanding "pro mode"; that preview API is retired, and the docs now describe [agentic mode (preview)](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/concepts/agentic-mode) for reasoning across a document.

### Implement text analysis solutions (10–15%)

- **Apply language model text analysis.** Extract entities, topics, summaries, and JSON with prompts and structured outputs, or with Azure Language. Detect sentiment, tone, safety issues, and sensitive data. Translate with Azure Translator or a model, and adapt outputs to a domain, such as compliance summaries. Docs: [Structured outputs](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/structured-outputs), [Azure Language overview](https://learn.microsoft.com/en-us/azure/ai-services/language-service/overview), [Azure Translator overview](https://learn.microsoft.com/en-us/azure/ai-services/translator/overview).
- **Implement speech.** Add speech to text and text to speech to agents, train custom speech models, reason over audio input with multimodal models, and translate speech. Docs: [Azure Speech overview](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/overview), [Custom speech](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/custom-speech-overview), [Voice Live API](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/voice-live), [Speech translation](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-translation).

Azure Language now calls PII detection, language detection, named entity recognition, and Text Analytics for health its core capabilities, and lists key phrase extraction, sentiment analysis, summarization, conversational language understanding, and question answering as legacy capabilities kept for existing workloads ([source](https://learn.microsoft.com/en-us/azure/ai-services/language-service/overview)).

### Implement information extraction solutions (10–15%)

- **Build retrieval and grounding pipelines.** Ingest documents, images, audio, and video into Azure AI Search with indexers, enrich content with skills (OCR, text splitting, embeddings, layout) or your own custom skills, configure keyword, vector, hybrid, and semantic search, and connect the index to agents. Docs: [Indexers](https://learn.microsoft.com/en-us/azure/search/search-indexer-overview), [AI enrichment](https://learn.microsoft.com/en-us/azure/search/cognitive-search-concept-intro), [Integrated vectorization](https://learn.microsoft.com/en-us/azure/search/vector-search-integrated-vectorization), [Hybrid search](https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview), [Azure AI Search tool for agents](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/ai-search).
- **Extract content from documents.** Combine OCR, layout analysis, and field extraction, and use Content Understanding analyzers to return clean markdown for RAG and agents or structured fields for automation. Docs: [Content Understanding overview](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/overview), [Prebuilt analyzers](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/concepts/prebuilt-analyzers), [Document Intelligence](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/overview).

## Study plan

The plan assumes 8–10 hours a week for six weeks and an Azure subscription for the labs. The four learning paths behind the course AI-103T00 add up to about 30 hours by Microsoft's estimates (1,776 minutes).

| Week | Focus | Tasks | Hours |
| --- | --- | --- | --- |
| 1 | Foundry setup and planning | Create a Foundry resource and project, deploy a model, and call it from Python with the Foundry SDK. Read the deployment types and quota pages. Do the first three modules of [Develop generative AI apps on Microsoft Foundry](https://learn.microsoft.com/en-us/training/paths/develop-generative-ai-apps/). | 8 |
| 2 | Generative apps and responsible AI | Finish that path. Build a small RAG app, run the groundedness and relevance evaluators on it, configure a guardrail, and test Prompt Shields with a planted instruction in a document. | 9 |
| 3 | Agents | Work through [Develop AI agents on Azure](https://learn.microsoft.com/en-us/training/paths/develop-ai-agents-azure/). Build an agent with file search, a function tool, and an MCP tool that requires approval, then an orchestration of two agents in Microsoft Agent Framework. Turn on tracing and read a trace span by span. | 10 |
| 4 | Vision, text, and speech | Do [Extract insights from visual data on Azure](https://learn.microsoft.com/en-us/training/paths/insight-visual-data/) through the Content Understanding modules, then [Develop natural language solutions in Azure](https://learn.microsoft.com/en-us/training/paths/develop-language-solutions-azure-ai/) for Language, Speech, Voice Live, and Translator. | 10 |
| 5 | Information extraction | Finish the visual data path. Build an Azure AI Search index with a skillset and integrated vectorization, compare keyword, vector, hybrid, and semantic results for the same queries, and connect the index to an agent. Analyze a scanned document with a Content Understanding analyzer. | 9 |
| 6 | Security and review | Set up a managed identity, keyless authentication, and a private endpoint on a test resource. Take the free practice assessment, review weak areas against the skills outline, and work through [practice-questions.md](practice-questions.md). | 8 |

## Cheat sheet

### Plan and manage

**Deployment types** ([source](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/concepts/deployment-types))

| Type | Where inference runs | Billing | Use it for |
| --- | --- | --- | --- |
| Global Standard | Any Azure region | Per token | The default start: new models arrive here first, lowest price, highest initial limits |
| Data Zone Standard | Inside the US, EU, or Asia Pacific data zone | Per token | Data zone residency with variable traffic |
| Standard | Inside the resource's Azure geography | Per token | Geography residency at low volume |
| Global, Data Zone, or Regional Provisioned | Same scopes as the rows above | Reserved provisioned throughput units (PTUs) | Steady high volume and low latency variance |
| Global or Data Zone Batch | Any region, or inside the data zone | 50% less than Global Standard, 24 hour target turnaround | Large asynchronous jobs |
| Developer | Any Azure region | Per token | Evaluating a model after fine-tuning only; no SLA |

**Rate limits** ([source](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/quota))

- A deployment's RPM limit is set in proportion to its TPM; for older chat models, 1 unit of capacity is 1,000 TPM and 6 RPM.
- The TPM check uses an estimate made when the request arrives, and that estimate includes `max_tokens`. Set `max_tokens` close to the response length you expect.
- RPM is checked over short windows of 1 or 10 seconds, so a burst can get HTTP 429 even when the minute's total is under the limit.
- On a 429, wait for the `retry-after-ms` header if it's present; otherwise retry with exponential backoff and random jitter.

**Identity and network**

| Need | Use | Source |
| --- | --- | --- |
| An Azure app calls Foundry with no stored secrets | Managed identity plus an Azure RBAC role on the Foundry resource | [Keyless authentication](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/how-to/configure-entra-id) |
| Turn off API keys | Set `disableLocalAuth` to `true` on the resource | [Keyless authentication](https://learn.microsoft.com/en-us/azure/foundry/foundry-models/how-to/configure-entra-id) |
| One identity shared by several resources | User assigned managed identity | [Managed identities](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview) |
| An identity deleted with its resource | System assigned managed identity | [Managed identities](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview) |
| Private inbound access | Private endpoint, with public network access disabled or limited to selected IP addresses | [Network isolation](https://learn.microsoft.com/en-us/azure/foundry/how-to/configure-private-link) |

Foundry roles were renamed recently: Foundry User was Azure AI User, and the same pattern applies to Foundry Owner, Foundry Account Owner, and Foundry Project Manager. Owner and Contributor can manage resources but don't include the data actions you need to build in a project, and an API key bypasses RBAC entirely ([source](https://learn.microsoft.com/en-us/azure/foundry/concepts/rbac-foundry)).

**Guardrails** ([overview](https://learn.microsoft.com/en-us/azure/foundry/guardrails/guardrails-overview), [defaults](https://learn.microsoft.com/en-us/azure/foundry/guardrails/default-safety-policies), [Prompt Shields](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/content-filter-prompt-shields))

| Control | What it detects | Default and notes |
| --- | --- | --- |
| Hate, sexual, violence, self-harm | Harmful text and images, classified as safe, low, medium, or high severity | On, at the Medium blocking level: medium and high severity are blocked in prompts and completions |
| Prompt Shields for user prompts | Attempts in the user input to override the system message (formerly jailbreak risk detection) | On |
| Prompt Shields for documents | Instructions hidden in documents, emails, web pages, or tool output (indirect attacks) | Off; turn it on in the guardrail |
| Groundedness detection (preview) | Claims not supported by the source material sent with the request | Needs the grounding documents in the request |
| Protected material | Known copyrighted text or public code in completions | On for text models |
| Personal data (preview) | PII in inputs or outputs | Configurable |

Controls run at four intervention points: user input, tool call (agents, preview), tool response (agents, preview), and output.

**Evaluators** ([source](https://learn.microsoft.com/en-us/azure/foundry/concepts/built-in-evaluators))

| Evaluator | Measures |
| --- | --- |
| Groundedness | How well the response sticks to the retrieved context (score 1–5) |
| Relevance | How well the response answers the query |
| Retrieval, Document Retrieval | Quality of what the retriever returned |
| Coherence, Fluency | Logical flow; language quality |
| Similarity, F1, BLEU, GLEU, ROUGE, METEOR | Similarity or overlap with a ground truth answer |
| Indirect Attack (XPIA) | Whether the response obeyed instructions injected through retrieved content |
| Task Adherence, Intent Resolution, Tool Call Accuracy | Agent behavior and tool use |

### Generative AI and agents

**Agent tools** ([function calling](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/function-calling), [file search](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/file-search), [code interpreter](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/code-interpreter), [OpenAPI](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/openapi), [MCP](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/model-context-protocol))

| Tool | Use it when |
| --- | --- |
| File search | The agent must answer from files you upload into a vector store |
| Azure AI Search | The agent must answer from an index you already run, with citations |
| Code interpreter | The agent must run Python in a sandbox: math, data files, charts |
| Function calling | Your app runs the code: the model returns a function name and arguments, your app executes it and sends the output back |
| OpenAPI | The agent calls an HTTP API described by an OpenAPI 3.0 or 3.1 spec |
| MCP | The agent uses tools from an MCP server; limit them with `allowed_tools` and gate calls with `require_approval` |

**Orchestration patterns in Microsoft Agent Framework** ([source](https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/))

| Pattern | How the agents run |
| --- | --- |
| Sequential | One after another in a fixed order |
| Concurrent | In parallel |
| Handoff | One agent transfers control to another based on context |
| Group chat | Agents collaborate in a shared conversation |
| Magentic | A manager agent coordinates specialist agents dynamically |

**Prompts and parameters** ([prompt engineering](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering), [structured outputs](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/structured-outputs), [reasoning models](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/reasoning))

- The system message sets role, boundaries, tone, and output format.
- Examples in the prompt (few-shot learning) prime the format and behavior you want.
- Chain of thought prompting asks for the steps before the answer; the docs say it applies only to models without reasoning.
- `temperature` runs from 0 to 2, and lower values give more focused output. Change `temperature` or `top_p`, not both.
- Most reasoning models don't accept `temperature` or `top_p`; you tune them with reasoning effort instead.
- Structured outputs make the model follow your JSON schema. JSON mode only guarantees valid JSON.
- Asking for inline citations makes fabricated statements less likely.

**Observability** ([tracing](https://learn.microsoft.com/en-us/azure/foundry/observability/concepts/trace-agent-concept))

- A trace is a tree of spans, one per operation, each with start and end times and attributes.
- Foundry follows OpenTelemetry semantic conventions and stores traces in the Application Insights resource connected to the project.

### Computer vision

| Task | Approach | Source |
| --- | --- | --- |
| Describe an image or answer questions about it | Send the image (URL or base64) with your text to a vision model | [Images in chat prompts](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/gpt-with-vision) |
| Spend fewer tokens on simple images | Set image `detail` to `low`, which processes a 512 x 512 version | [Images in chat prompts](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/gpt-with-vision) |
| Edit one area of an image | Send the image, a prompt, and a PNG mask of the same size; fully transparent pixels mark the area to change | [Image generation](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/dall-e) |
| Generate a video | Submit an asynchronous job, poll its status, then download the result | [Video generation](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/video-generation) |
| Structured fields from images or video | A Content Understanding analyzer with a field schema | [Content Understanding](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/overview) |
| Moderate uploaded images | Azure AI Content Safety image analysis for hate, sexual, violence, and self-harm | [Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview) |

### Text analysis and speech

| Need | Use | Source |
| --- | --- | --- |
| Entities, summaries, or labels as JSON that always matches a schema | A language model with structured outputs | [Structured outputs](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/structured-outputs) |
| Find and redact personal data | Azure Language PII detection | [PII detection](https://learn.microsoft.com/en-us/azure/ai-services/language-service/personally-identifiable-information/overview) |
| People, places, and organizations in text | Azure Language named entity recognition | [NER](https://learn.microsoft.com/en-us/azure/ai-services/language-service/named-entity-recognition/overview) |
| Translate many files and keep their formatting | Translator document translation, asynchronous batch, with source and target Blob Storage containers | [Document translation](https://learn.microsoft.com/en-us/azure/ai-services/translator/document-translation/overview) |
| Domain terminology in translations | Custom Translator | [Translator overview](https://learn.microsoft.com/en-us/azure/ai-services/translator/overview) |
| Transcribe a microphone or audio stream as it arrives | Real-time transcription (speech to text) | [Speech to text](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-to-text) |
| Transcribe a recorded file as fast as possible | Fast transcription, which returns results synchronously | [Speech to text](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-to-text) |
| Transcribe a large volume of stored audio | Batch transcription, asynchronous | [Batch transcription](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/batch-transcription) |
| Recognize a few uncommon terms without training | A phrase list | [Speech to text](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-to-text) |
| Domain vocabulary plus difficult audio conditions | A custom speech model trained on text and on audio with human transcripts | [Custom speech](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/custom-speech-overview) |
| Control pitch, rate, volume, and pronunciation of synthesized speech | SSML | [SSML](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-synthesis-markup) |
| A voice agent without building the speech pipeline yourself | Voice Live API | [Voice Live](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/voice-live) |

### Information extraction

**Azure AI Search query types** ([hybrid search](https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview), [semantic ranker](https://learn.microsoft.com/en-us/azure/search/semantic-search-overview))

| Query | Ranking | Strength |
| --- | --- | --- |
| Full text | BM25 | Exact terms, product codes, names, dates |
| Vector | HNSW or exhaustive KNN similarity | Matches on meaning without shared keywords |
| Hybrid | Full text and vector in parallel, merged with Reciprocal Rank Fusion (RRF) | Strong default for grounding data |
| Semantic ranker | Reranks the top BM25 or RRF results with language models, and can return captions and answers | Better relevance on top of the queries above |

**Enrichment pipeline** ([AI enrichment](https://learn.microsoft.com/en-us/azure/search/cognitive-search-concept-intro), [integrated vectorization](https://learn.microsoft.com/en-us/azure/search/vector-search-integrated-vectorization))

- Data source, then an indexer that cracks documents, then a skillset (OCR, Text Split, an embedding skill, the Content Understanding skill, or custom skills), then field mappings into the index.
- Integrated vectorization creates embeddings during indexing and at query time. Chunk large documents so each piece fits the embedding model's input limit.
- Enriched content is temporary unless you map it to the index or cache it.

**Content Understanding** ([overview](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/overview), [prebuilt analyzers](https://learn.microsoft.com/en-us/azure/ai-services/content-understanding/concepts/prebuilt-analyzers))

- An analyzer bundles content extraction settings, a field schema, and the model deployments it uses.
- Fields use one of three methods: extract (documents only), classify, or generate.
- Output is markdown for search and RAG, or JSON fields for automation. Document analyzers can return a confidence score (0–1) and the source location for each field.
- `prebuilt-read` does OCR without layout, `prebuilt-layout` adds tables, sections, and figures, and the base analyzers (`prebuilt-document`, `prebuilt-image`, `prebuilt-audio`, `prebuilt-video`) are the parents for custom analyzers.
- API version `2025-11-01` is the generally available version for production.

## Free official resources

- [AI-103 certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-ai-apps-and-agents-developer-associate/): scheduling, price by country, and languages.
- [AI-103 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103): the skills outline this guide follows.
- [Course AI-103T00: Develop AI apps and agents on Azure](https://learn.microsoft.com/en-us/training/courses/ai-103t00) and its four free learning paths: [Develop generative AI apps on Microsoft Foundry](https://learn.microsoft.com/en-us/training/paths/develop-generative-ai-apps/), [Develop AI agents on Azure](https://learn.microsoft.com/en-us/training/paths/develop-ai-agents-azure/), [Develop natural language solutions in Azure](https://learn.microsoft.com/en-us/training/paths/develop-language-solutions-azure-ai/), and [Extract insights from visual data on Azure](https://learn.microsoft.com/en-us/training/paths/insight-visual-data/).
- [Free practice assessment on AI Skills Navigator](https://aiskillsnavigator.microsoft.com/credentials/cert-3fb198f57997226a824aa5f52a1a22af9a4597941b2288ed39371c7a9e6bd7c9): sign in to start it.
- [Exam sandbox](https://aka.ms/examdemo): try the question formats and the exam interface.
- [AI-103 exam prep video](https://aka.ms/AI103-ExamPrep) from Microsoft.
- [Microsoft Foundry portal](https://ai.azure.com) and the [Microsoft Foundry documentation](https://learn.microsoft.com/en-us/azure/foundry/what-is-foundry).
- [Azure free account](https://azure.microsoft.com/pricing/purchase-options/azure-account) for the labs.
- [Microsoft Q&A](https://learn.microsoft.com/en-us/answers/) for questions about the services.

## Practice questions

[practice-questions.md](practice-questions.md) has 15 original scenario questions spread across the five domains by weight, each with an explanation and a link to the docs. For more, the [Examice AI-103 practice bank](https://examice.com/exams/microsoft/ai-103?utm_source=github&utm_medium=social&utm_campaign=ai-103-study-guide-and-practice-questions&utm_content=link_2) has 160+ questions with a written explanation and a discussion under each one, and the first 5 questions are free, explanations included.

## Exam day tips

- You get 120 minutes. On associate exams you can open Microsoft Learn in a split screen, but the clock keeps running, so use it to confirm one detail rather than to learn a topic ([source](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience)).
- Answer and review every question you've seen before you take a break: after a break you can't return to them.
- You can't take a break in the middle of a lab or a problem and solution set.
- Guessing costs nothing, and a question with several parts gives a point for each correct part, so answer everything. Some questions are unscored, and you won't know which ([source](https://learn.microsoft.com/en-us/credentials/certifications/exam-scoring-reports)).
- If the exam isn't offered in your language, you can request 30 extra minutes.
- Register with a personal Microsoft account, not a work account, so your records stay with you if you change jobs.
- Expect current product names: Microsoft Foundry (formerly Azure AI Studio and Azure AI Foundry), Foundry Tools (formerly Azure AI Services), and Azure Content Understanding in Foundry Tools ([source](https://learn.microsoft.com/en-us/azure/foundry/what-is-foundry)).

## FAQ

### How hard is AI-103?

Microsoft rates it Intermediate and expects you to have built apps in Python and to know generative AI and Azure services. Planning, securing, and building generative apps and agents carry 55–65% of the weight, so practical time with Foundry deployments, agents, and RAG matters most. You need a scaled score of 700 to pass ([source](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103)).

### How long should I study for AI-103?

The course AI-103T00 runs 4 days with an instructor, and its four learning paths take about 30 hours by Microsoft's estimates ([source](https://learn.microsoft.com/en-us/training/courses/ai-103t00)). If you already build on Azure, the six week plan above at 8–10 hours a week is a reasonable target. Add a week or two if Foundry is new to you.

### Does the Azure AI Apps and Agents Developer Associate certification expire?

Yes, after one year. Renewal is free: pass an online, unproctored, open book assessment on Microsoft Learn during the six month window before it expires, and the certification extends one year from its expiration date ([source](https://learn.microsoft.com/en-us/credentials/certifications/renew-your-microsoft-certification)).

### What is the AI-103 retake policy?

After a first failed attempt you wait 24 hours. After that you wait 14 days between attempts, with at most 5 attempts in the 12 months from your first try. Each retake is paid, and you can't retake an exam you passed unless the certification has expired ([source](https://learn.microsoft.com/en-us/credentials/support/retake-policy)).

### Does AI-103 replace AI-102?

Yes. Microsoft retired AI-102 and the Azure AI Engineer Associate certification on June 30, 2026, and named AI-103 and the Azure AI Apps and Agents Developer Associate as the replacement. An Azure AI Engineer Associate certification you already earned stays valid until it expires, but its renewal assessment is retired ([announcement](https://techcommunity.microsoft.com/blog/skills-hub-blog/the-ai-job-boom-is-here-are-you-ready-to-showcase-your-skills/4494128), [AI-102 certification page](https://learn.microsoft.com/en-us/credentials/certifications/azure-ai-engineer/)).

### Which programming language does AI-103 use?

Python. The audience profile asks for experience developing apps by using Python ([source](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103)).

## Contributing

Found a fact that changed or an answer you disagree with? Open an issue or a pull request and include a link to the Microsoft source. Exam facts in this guide were last checked on October 28, 2026.

## License

Text and questions © Examice, licensed under [CC BY 4.0](LICENSE).

Microsoft, Azure, and Microsoft Foundry are trademarks of the Microsoft group of companies. This guide is not affiliated with or endorsed by Microsoft.
