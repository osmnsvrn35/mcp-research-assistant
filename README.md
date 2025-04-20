# 🧠 MCP Research Assistant

A multi-agent, context-aware AI system built using the **Model Context Protocol (MCP)**. This project is designed to explore and demonstrate **agent orchestration**, **context tracking**, and **multi-step LLM workflows** — all driven by modular and composable MCP definitions.

---

## 🚀 Project Goals

- Build an **intelligent research assistant** that can:
  - Interpret natural language queries
  - Find relevant academic papers (via arXiv/Semantic Scholar API)
  - Summarize each paper using an LLM
  - Combine results into a clear and final report

- Learn the architecture and hands-on implementation of:
  - `ModelContext`, `ModelProtocol`, `ModelDefinition`
  - Multi-agent workflows
  - Context propagation across agents
  - Modular AI system design using MCP

---

## 📦 Tech Stack

| Component | Tool |
|----------|------|
| LLM Backend | OpenAI / Claude / Local LLM |
| Agent Framework | [LangChain](https://github.com/langchain-ai/langchain), [LangGraph (optional)](https://github.com/langchain-ai/langgraph) |
| Protocol Design | Model Context Protocol (MCP) |
| Paper Search | Semantic Scholar API / arXiv API |
| Context Store | In-memory (or upgrade to Redis later) |
| Frontend (optional) | FastAPI / CLI |

---

## 🧱 Architecture Overview

```txt
┌────────────────────────────┐
│        User Input          │
└────────────┬───────────────┘
             ▼
    ┌───────────────────┐
    │ Controller Agent  │ ◀── Creates context, splits tasks
    └────────┬──────────┘
             ▼
 ┌──────────────────────┐
 │   Research Agent     │ ◀── Calls paper search APIs
 └────────┬─────────────┘
          ▼
 ┌──────────────────────┐
 │   Summarizer Agent   │ ◀── Summarizes each paper
 └────────┬─────────────┘
          ▼
 ┌──────────────────────┐
 │  Synthesizer Agent   │ ◀── Aggregates & formats response
 └──────────────────────┘
