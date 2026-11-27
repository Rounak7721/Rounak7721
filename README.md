<div align="center">

# Rounak Sonavane

### AI Engineer

**I take AI products from idea to live deployment — model training, agent design, backend and infrastructure.**

LLM agents · MCP · RAG · Voice agents · Fine-tuning · Evals · Backend systems

<br/>

[![Resume](https://img.shields.io/badge/Résumé-Download-2B4C7E?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://github.com/Rounak7721/Rounak7721/raw/main/Rounak_Sonavane_Resume.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rounak-sonavane)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rounaks7721@gmail.com)

</div>

---

## 👋 About

I build AI systems that are reliable and explainable — not just impressive in a demo.

In practice that means treating a model as one component of a larger system: fine-tuning it where it earns its place, keeping decisions deterministic where they need to be reproducible and auditable, wrapping it in a clean service layer, then automating delivery and monitoring the thing once it's live.

Over the past year and a half I've built an open-source MCP developer tool published on PyPI and the official MCP Registry, a live AI contract review platform, a real-time voice agent, an AI product builder, a multimodal agentic workspace running on a hand-written orchestration engine, and LLM workflow automations, plus a 6-DOF robotic arm on ROS 2 on the side. All of it solo, most of it from scratch.

🎓 B.Tech in Artificial Intelligence & Machine Learning, 2025 · ⚡ Immediate joiner

---

## 🚀 Featured Projects

### ✂️ slimproof — MCP Token Optimizer

[![PyPI](https://img.shields.io/pypi/v/slimproof?style=flat-square&logo=pypi&logoColor=white&label=PyPI&color=3775A9)](https://pypi.org/project/slimproof/)
[![Repo](https://img.shields.io/badge/Repo-slimproof-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/slimproof)
[![Demo](https://img.shields.io/badge/Demo-YouTube-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://youtu.be/w__NH_zfuFQ)
![MCP Registry](https://img.shields.io/badge/MCP_Registry-listed-6E56CF?style=flat-square)

Every MCP tool definition is sent to the model on every request, used or not. slimproof measures what that costs, has Claude rewrite the bloated descriptions, and proves the slim versions still get picked correctly.

The core design idea: **slim the words, never the structure.** A guard rejects any rewrite that changes tool names, parameters, types or schemas, and an eval checks that behaviour holds.

- **Audit** ranks every tool by token cost and flags bloat with 8 rules; **Apply** serves slim descriptions through a local proxy with one-command revert
- Eval on **180 hand-checked requests across 6 popular MCP servers** (Claude Haiku and Sonnet): same **99% tool accuracy** as the originals with **16% fewer prompt tokens** (54% fewer on Desktop Commander)
- In the demo, a 40-tool setup drops from **~24,761 to ~12,595 tokens**
- Shipped three ways: a **PyPI** CLI, an MCP server in the **official MCP Registry**, and a **Claude Code plugin**
- **115 tests**, CI on Ubuntu, macOS and Windows × Python 3.10–3.13, and tag-triggered releases with PyPI trusted publishing (OIDC)

`Python` `MCP Python SDK` `Typer` `httpx` `uv` `pytest` `ruff` `pyright` `GitHub Actions`

---

### ⚖️ ClauseGuard — AI Legal Contract Review Platform

[![Live](https://img.shields.io/badge/Live-clauseguard.rounak.co-2ea44f?style=flat-square&logo=cloudflare&logoColor=white)](https://clauseguard.rounak.co)
[![Docs](https://img.shields.io/badge/Docs-ClauseGuard-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/ClauseGuard)
[![Demo](https://img.shields.io/badge/Demo-YouTube-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/watch?v=t1wdO2IBGTY)

Explains a legal contract clause by clause, in plain language — combining a fine-tuned classifier, a deterministic risk engine, and a RAG-grounded LLM agent.

The core design idea: **deterministic where it must be, generative where it helps.** Clause classification and risk scoring are fully reproducible and auditable; the LLM only writes the explanation.

- Fine-tuned **Legal-BERT** classifying clauses into **41 CUAD categories**, with calibrated confidence scores
- Raised classifier **macro-F1 from 0.63 → 0.78** (accuracy 0.79 → 0.86) by root-causing a training-label conflict rather than adding compute
- Risk levels come from a **static rule table, never an LLM** — same input, same result, every time
- **LangGraph** tool-calling agent producing citation-backed reports, with real interrupt/resume human-in-the-loop gates on expensive operations
- **Fully automated CI/CD**: GitHub Actions → multi-arch images → GHCR → Tailscale-authenticated deploy to a Cloudflare-tunnelled host, with independent n8n uptime monitoring on isolated infrastructure

`FastAPI` `PyTorch` `Transformers` `LangGraph` `LangChain` `Groq` `ChromaDB` `React` `TypeScript` `Docker` `GitHub Actions`

---

### 🎙️ Ask Rounak — Real-Time Voice Interview Agent

[![Live](https://img.shields.io/badge/Live-ask.rounak.co-2ea44f?style=flat-square&logo=vercel&logoColor=white)](https://ask.rounak.co)
[![Repo](https://img.shields.io/badge/Repo-ask--rounak-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/ask-rounak)

Tap the orb and ask an interview question out loud. It answers in my voice persona: my background, projects and how I think.

- **Hands-free voice mode**: Silero VAD runs in the browser (WebAssembly), with barge-in so you can interrupt mid-answer
- Groq **Whisper** speech-to-text that drops low-confidence noise, and streamed **Deepgram Aura-2** speech with custom pronunciations
- **Grounded answers** from my own notes; it says so when something isn't covered instead of guessing
- **Rate-limit-aware fallback chain** (two Groq models, then Gemini), a timeout and fallback on every external call, server-only keys, and Q&A logging with no IPs stored

`Next.js` `React` `TypeScript` `Groq` `Whisper` `Deepgram` `Silero VAD` `Gemini` `Supabase` `Vercel`

---

### 🧠 MindDesk — Multimodal Agentic AI Platform

[![Docs](https://img.shields.io/badge/Docs-MindDesk-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/MindDesk)

A local-first agentic platform that plans, reasons and acts across eight capability domains — running entirely on your own hardware, with nothing sent to a third party.

Its **plan-and-execute engine is built from scratch** — no agent framework. Planner, validator, executor, scratchpad and variable resolver are all custom.

- Coordinates **17 specialized tools** through a decoupled registry, so adding a tool never touches the planner
- Typed plan validation with **retry-repair loops**, hallucinated-step stripping, and `$stepN.field` result chaining between tools
- A deterministic fast path bypasses the LLM planner entirely for simple intents, keeping latency low
- Document intelligence over PDF/DOCX/XLSX/CSV with hybrid **FAISS + ChromaDB** retrieval, isolated per conversation
- Real-time vision (**YOLOv11** detection + **InsightFace** recognition), IoT device control, speech, image generation and RBAC admin in one system

`Python` `Flask` `React` `Ollama` `LangChain` `RAG` `YOLO` `OpenCV` `Whisper` `PostgreSQL` `MongoDB` `FAISS` `ChromaDB`

---

### 📂 More projects

| Project | What it does | Stack |
|---|---|---|
| 🔨 **[ReForge](https://reforge.rounak.co)** · [repo](https://github.com/Rounak7721/ReForge) · [demo](https://www.youtube.com/watch?v=yT_LptZCr4A) | Turns any website into a product concept and starter site. Concept to deployed MVP in 72 hours, with a vendor-neutral LLM layer and $0 running cost | Next.js · Supabase · Gemini · Groq |
| ⚙️ **[Lead Qualification](https://github.com/Rounak7721/ai-lead-qualification-system)** | Captures, scores, tiers and routes leads with an LLM; idempotent alerts and an append-only audit log | n8n · Groq · Ollama |
| 🤖 **[IRIS](https://github.com/Rounak7721/iris)** *(ongoing)* | Custom 6-DOF robotic arm with dual-camera perception and a local voice pipeline | ROS 2 · MoveIt · YOLO · Whisper |
| 🖐️ **[Virtual Mouse](https://github.com/Rounak7721/Virtual-Mouse)** | Full cursor control (move, click, scroll, drag) from webcam hand gestures | OpenCV · MediaPipe |

> ClauseGuard and MindDesk source code is kept private; their repos hold the full architecture and engineering write-ups. Happy to give access to recruiters on request.

---

## 🛠️ Tech Stack

<table>
<tr><td><b>Languages</b></td><td>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white) ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

</td></tr>
<tr><td><b>AI & LLM</b></td><td>

![MCP](https://img.shields.io/badge/MCP-6E56CF?style=flat-square&logo=modelcontextprotocol&logoColor=white) ![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langgraph&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white) ![RAG](https://img.shields.io/badge/RAG-2B4C7E?style=flat-square) ![Evals](https://img.shields.io/badge/Evals-0E7C86?style=flat-square) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=anthropic&logoColor=white)

</td></tr>
<tr><td><b>Models & providers</b></td><td>

![Gemini](https://img.shields.io/badge/Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square) ![OpenAI API](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white) ![Whisper](https://img.shields.io/badge/Whisper-412991?style=flat-square&logo=openai&logoColor=white) ![Deepgram](https://img.shields.io/badge/Deepgram-13EF93?style=flat-square)

</td></tr>
<tr><td><b>Backend & data</b></td><td>

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white) ![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) ![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=flat-square) ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white)

</td></tr>
<tr><td><b>Shipping</b></td><td>

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![PyPI](https://img.shields.io/badge/PyPI-3775A9?style=flat-square&logo=pypi&logoColor=white) ![uv](https://img.shields.io/badge/uv-DE5FE9?style=flat-square&logo=uv&logoColor=white) ![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n&logoColor=white)

</td></tr>
<tr><td><b>Also</b></td><td>

![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) ![YOLO](https://img.shields.io/badge/YOLO-00FFFF?style=flat-square&logo=yolo&logoColor=black) ![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white) ![ROS 2](https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white)

</td></tr>
</table>

---

## 📌 Currently

📦 **Just shipped** — [slimproof](https://github.com/Rounak7721/slimproof) v0.1, on [PyPI](https://pypi.org/project/slimproof/) and the official MCP Registry. Try it: `uvx slimproof audit`

🚀 **Live** — [ClauseGuard](https://clauseguard.rounak.co), [ReForge](https://reforge.rounak.co) and [Ask Rounak](https://ask.rounak.co), all deployed and actively improving

🤖 **On the side** — [IRIS](https://github.com/Rounak7721/iris), a custom 6-DOF robotic arm

---

<div align="center">

**Open to roles in** AI Engineering · Agentic AI · GenAI · LLM Applications · Available immediately

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rounak-sonavane)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rounaks7721@gmail.com)
[![Résumé](https://img.shields.io/badge/Résumé-2B4C7E?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://github.com/Rounak7721/Rounak7721/raw/main/Rounak_Sonavane_Resume.pdf)

</div>
