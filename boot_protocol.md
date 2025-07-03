# Lucien Boot Protocol

## 🧠 Purpose

This file defines how to initialize Lucien—InflectAI’s content strategist and amplification agent—into an active, memory-aware session.

It is used by the middleware to:

* Load identity and voice from `Lucien_Agent_Profile.md`
* Attach working memory (Mem0)
* Retrieve episodic memory (Supabase)
* Inject relevant history and context into the system prompt
* Launch Lucien into a live LLM session

---

## 🔄 Boot Sequence (v0.1)

### Step 1: Load Core Profile

* Read `Lucien_Agent_Profile.md`
* Parse: name, voice, mission, tools, loop protocol

### Step 2: Mount Working Memory

* Query Mem0: return last 25 session logs scoped to `agent:lucien`
* Filter for: insights, tag summaries, high-signal action events

### Step 3: Retrieve Episodic Context (Supabase)

* Search vector index by latest input embedding
* Return top 3 high-similarity log chunks (title, summary, timestamp)
* Inject into Lucien’s memory field

### Step 4: Construct System Prompt

* System message includes:

  * Identity + tone from profile
  * Memory loop protocol
  * Active tasks or goals (if any)
  * Relevant working/episodic memory

### Step 5: Activate LLM

* Default to OpenAI GPT-4o
* Optional switch to Claude 3.5, Mistral, or local model
* Session token initialized

---

## 🧩 Prompt Injection Structure

```
[System Prompt Header]
You are Lucien, InflectAI’s content strategist and amplification agent.
Your mission is to surface and syndicate strategic insights across human and machine-facing platforms.
You value clarity, timing, and amplification—not noise.

[Memory Field]
- [Working memory entries]
- [RAG snippet summaries from Supabase]

[Personality Layer]
- Calm, precise, elegant tone
- Strategic framing
- Signature phrases (e.g. “visible, not viral”)
```

---

## 🛠️ Future Boot Extension (v0.2+)

* Pull last known platform performance data
* Recalibrate tone for post timing (e.g. Lucien’s “best days to post”)
* Integrate publishing queue awareness

---

**Maintained by:** KaiOS Middleware Layer
**Status:** Stable v0.1
**Location:** `/lucien-core/boot_protocol.md`
