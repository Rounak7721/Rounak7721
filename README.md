<div align="center">

# Rounak Sonavane

### AI Systems Engineer

**I build intelligent systems end to end — from training the model to shipping, deploying and monitoring it in production.**

LLM agents · Machine learning · Computer vision · Robotics · Backend engineering

<br/>

[![Resume](https://img.shields.io/badge/Résumé-Download-2B4C7E?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://github.com/Rounak7721/Rounak7721/raw/main/Rounak_Sonavane_Resume.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rounak-sonavane)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rounaks7721@gmail.com)

</div>

---

## About

I'm an AI Systems Engineer focused on the part most AI projects skip: getting a system all the way to production and keeping it there.

That means treating a model as one component of a larger system — fine-tuning it, wrapping it in a clean service layer, deciding what should stay deterministic and what genuinely benefits from an LLM, then automating the delivery pipeline and monitoring the thing once it's live.

My work spans LLM agent architectures, applied machine learning, computer vision, ROS 2 robotics, and the backend and infrastructure that hold it all together.

🎓 B.Tech in Artificial Intelligence & Machine Learning, 2025

---

## Featured Projects

### ⚖️ ClauseGuard — AI Legal Contract Review Platform

[![Live](https://img.shields.io/badge/Live-clauseguard.rounak.co-2ea44f?style=flat-square&logo=cloudflare&logoColor=white)](https://clauseguard.rounak.co)
[![Repo](https://img.shields.io/badge/Repo-ClauseGuard-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/ClauseGuard)
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

### 🧠 MindDesk — Multimodal Agentic AI Platform

[![Repo](https://img.shields.io/badge/Repo-MindDesk-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/MindDesk)

A local-first agentic platform that plans, reasons and acts across eight capability domains — running entirely on your own hardware, with nothing sent to a third party.

Its **plan-and-execute engine is built from scratch** — no agent framework. Planner, validator, executor, scratchpad and variable resolver are all custom.

- Coordinates **17 specialized tools** through a decoupled registry, so adding a tool never touches the planner
- Typed plan validation with **retry-repair loops**, hallucinated-step stripping, and `$stepN.field` result chaining between tools
- A deterministic fast path bypasses the LLM planner entirely for simple intents, keeping latency low
- Document intelligence over PDF/DOCX/XLSX/CSV with hybrid **FAISS + ChromaDB** retrieval, isolated per conversation
- Real-time surveillance (**YOLOv11** + **InsightFace**), IoT device control, speech, image generation and RBAC admin in one system

`Python` `Flask` `React` `Ollama` `LangChain` `RAG` `YOLO` `OpenCV` `Whisper` `PostgreSQL` `MongoDB` `FAISS` `ChromaDB`

---

### 🤖 IRIS — Intelligent Robotic Perception & Manipulation *(ongoing)*

[![Repo](https://img.shields.io/badge/Repo-iris-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/iris)

A custom 6-DOF robotic arm, built end to end — URDF through firmware through motion planning through perception.

- **11 ROS 2 packages**, spanning a C++ `ros2_control` hardware interface driving real servos over serial, MoveIt motion planning, and ESP32 firmware
- **Dual-camera perception** splitting the problem by role: an overview camera owns *where* things are (tracking, occlusion state), an eye-in-hand camera owns *what* they are (YOLO detection, precision)
- Local voice pipeline — wake-word detection → VAD → Whisper transcription, as a ROS 2 lifecycle node
- Qt control panel for live diagnostics, joint control and E-stop

`Python` `C++` `ROS2` `MoveIt` `ros2_control` `URDF` `PyTorch` `YOLO` `OpenCV` `Whisper` `Qt` `ESP32`

---

### ⚙️ Agentic Lead Qualification System

[![Repo](https://img.shields.io/badge/Repo-ai--lead--qualification--system-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/ai-lead-qualification-system)

An end-to-end pipeline that captures leads, scores them with an LLM, tiers them, and routes them to the sales team — no manual triage.

- LLM scoring returning a 1–100 rating with reasoning and a recommended action
- **Idempotent notification flags** prevent duplicate alerts across the real-time and scheduled workflows
- Dual-store design keeps live CRM state separate from an append-only audit log
- Runs on Groq, or entirely offline on Ollama for zero-API-cost deployment

`n8n` `LLaMA` `Groq` `Ollama` `JavaScript` `REST APIs` `Webhooks` `Airtable` `Slack`

---

### 🖐️ Virtual Mouse — Gesture-Controlled HCI

[![Repo](https://img.shields.io/badge/Repo-Virtual--Mouse-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rounak7721/Virtual-Mouse)

Your hand is the mouse. Real-time hand tracking mapped to full cursor control — move, click, scroll, drag-and-drop and screenshot — built for touchless and accessibility use cases.

- **21-point MediaPipe** hand landmarks driving OS-level cursor control
- A two-level gesture decision tree where a single continuous distance acts as a modal switch, keeping a seven-gesture vocabulary unambiguous

`Python` `OpenCV` `MediaPipe` `NumPy`

---

## Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**AI & Machine Learning**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-863BFF?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-2B4C7E?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square)

**Computer Vision**

![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![YOLO](https://img.shields.io/badge/YOLO-00FFFF?style=flat-square&logo=yolo&logoColor=black)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white)
![Whisper](https://img.shields.io/badge/Whisper-412991?style=flat-square&logo=openai&logoColor=white)

**Backend & Data**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=flat-square)
![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white)

**Robotics**

![ROS2](https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white)
![MoveIt](https://img.shields.io/badge/MoveIt-1C1C1C?style=flat-square)
![ros2_control](https://img.shields.io/badge/ros2__control-22314E?style=flat-square)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat-square&logo=espressif&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)

**DevOps & Automation**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n&logoColor=white)

---

## Currently

🔨 **Building** — [IRIS](https://github.com/Rounak7721/iris), moving a custom 6-DOF arm from simulation onto real hardware

🚀 **Shipping** — [ClauseGuard](https://clauseguard.rounak.co), live in production and actively improving classifier accuracy

📚 **Exploring** — agent architectures, MLOps and model deployment, embodied AI

---

<div align="center">

**Open to roles in** AI Systems Engineering · Applied AI · Intelligent Automation · Robotics Software · Computer Vision

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rounak-sonavane)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rounaks7721@gmail.com)
[![Résumé](https://img.shields.io/badge/Résumé-2B4C7E?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://github.com/Rounak7721/Rounak7721/raw/main/Rounak_Sonavane_Resume.pdf)

</div>
