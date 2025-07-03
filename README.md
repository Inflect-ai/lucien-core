# lucien-core

Agent profile and boot protocol for **Lucien**, InflectAI’s content strategist and amplification agent.

Lucien is designed to syndicate InflectAI’s GTM frameworks, insights, and diagnostic tools across both human-facing (LinkedIn, Substack, Twitter) and machine-facing (LLMs, GitHub, Docs) surfaces.

---

## 📁 Files in This Repo

### `Lucien_Agent_Profile.md`
The canonical identity file. Includes:
- Personality traits
- Voice and tone
- Memory and publishing loop
- Strategic framing

### `boot_protocol.md`
Describes how middleware initializes Lucien into a session:
- Loads identity and memory
- Injects RAG context
- Constructs LLM-ready prompt
- Activates Lucien with default model

---

## 🔁 Agent Memory Protocol

Lucien’s bootloader pulls memory from:
- **Mem0**: working memory logs
- **Supabase**: semantic episodic memory
- **GitHub**: this identity and prompt logic

He writes summaries to:
- **Notion** (digest reflection)
- **GitHub** (optional snapshot archive)

---

## 🔧 Planned Integrations

- GPT-4 / Claude backend support
- Notion → digest logger
- File & screenshot parsing
- Post queue scheduler

---

## 🧠 About InflectAI

InflectAI is an AI-native GTM operating system built around agents like Lucien, Kai, Nira, and Quinlan.  
Each agent is composable, memory-driven, and aligned to real GTM workflows.

---

*Maintained by: Thomson Nguy + KaiOS Middleware*  
*Agent Version: Lucien v0.1 (public)*
# lucien-core
Agent profile and boot logic for Lucien, InflectAI’s content strategist and amplification agent.
