# 🤖 LangChain & Ollama Agent Frameworks

A collection of **LangChain** workflow implementations powered locally by **Ollama (`qwen2.5:3b`)**. This repository demonstrates practical patterns for local LLMs, including custom tool integration, agent execution, structured parsing, memory handling, and streaming LCEL chains.

---

## ✨ Features & Components

### 1. 🛠️ Intelligent Tool-Calling & ReAct Agents
* **College Assistant Agent:** Uses LangChain's tool calling to automate student attendance verification, mark calculation, hostel/library fee computation, and database record lookup (`S101`, `S102`, `S103`).
* **ReAct Agent & Custom Tools:** Built-in dynamic tools for safe expression evaluation via custom math solvers and student risk evaluation lookups.

### 2. 🧠 Conversational Agent with Memory
* Implements **`ConversationBufferWindowMemory`** ($k=5$) to maintain multi-turn context across queries.
* Export tool outputs and session logs directly into formatted JSON reports (`session_report.json`).

### 3. 🎯 Structured Output Parsing (Pydantic)
* Extracts unstructured text inputs into strictly validated JSON objects matching custom models (e.g., `StudentProfile` schema with CGPA and risk levels).

### 4. ⚡ LCEL Chains & Execution Modes
* Modern **LangChain Expression Language (LCEL)** integration (`prompt | llm | parser`).
* Supports multiple execution patterns: standard **invoke**, continuous **streaming**, and asynchronous/parallel **batch** processing.

---

## 🛠️ Tech Stack & Requirements

* **Framework:** LangChain (`langchain-core`, `langchain-community`)
* **Local LLM Integration:** `langchain-ollama`
* **Model:** `qwen2.5:3b` via Ollama
* **Data Validation:** Pydantic v2
* **Language:** Python 3.10+

---

## ⚙️ Quick Start Guide

### 1. Install & Start Ollama
Ensure [Ollama](https://ollama.ai/) is installed and running locally, then pull the target model:
```bash
ollama pull qwen2.5:3b
