# ⚡ MindForge AgentFlow — Browser-Based LLM Agent POC

This project is a **lightweight proof-of-concept** for experimenting with **LLM agents directly in the browser**. It demonstrates how an AI model can combine **reasoning with external tools** like search engines, API workflows, and even live JavaScript execution — all inside a simple front‑end.

Unlike static chatbots, MindForge aims to show how an LLM can **think, plan, and act** in a loop until a task is solved.

---

## ✨ Key Highlights

🔹 **Switch Between Models**
Pick your preferred provider: AI Pipe API (default), OpenAI GPT, Gemini, Claude, or others.
The dropdown lets you switch models on the fly.

🔹 **Agent Loop Logic**

* Takes your query, reasons using an LLM, and decides if a tool is needed.
* Calls tools like search/AI workflows/JS executor.
* Continues until a final response is ready.

🔹 **Built-in Tools**

* 🔍 Google Search snippet fetcher.
* 🔗 AI Pipe workflow integration.
* ⚙️ JavaScript sandbox for running code safely in‑browser.

🔹 **Polished Browser UI**

* Clean Bootstrap-based design.
* Real-time chat interface with error alerts.
* Logs tool actions + response times for debugging.

---

## 🧩 How It Works

### High-Level Flow

```python
def run_agent(user_message):
    history = [user_message]
    while True:
        reply, tool_calls = LLM(history, tools)
        print("Agent:", reply)
        if tool_calls:
            history += [use_tool(tc) for tc in tool_calls]
        else:
            break
```

The JavaScript version mirrors this loop, wired to provider APIs.

---

## 🚀 Getting Started

### Requirements

* A modern browser (Chrome/Edge/Firefox).
* (Optional) API keys if you want live connections:

  * [AI Pipe](https://aipipe.org/) proxy API key
  * Or OpenAI / Gemini / Anthropic keys

### Run Locally

1. Clone the repo:

   ```bash
   git clone https://github.com/<your-username>/mindforge-agentflow.git
   cd mindforge-agentflow
   ```
2. Open `index.html` directly in your browser, or serve with:

   ```bash
   python -m http.server 8000
   ```

   Visit [http://localhost:8000](http://localhost:8000).
3. Add your API key in the in‑app Settings panel.

---

## 🖥️ Example Use

**User:** "Write me a blog outline on IBM."

**Agent:** "Searching IBM..." → *(runs Google search tool)*

**Agent:** "IBM is a global company founded in 1911... Would you like me to draft an outline?"

**User:** "Yes."

**Agent:** *Creates blog outline step by step.*

---

## 🎯 Evaluation Metrics

| Aspect                   | Marks |
| ------------------------ | ----- |
| Working functionality    | 1.0   |
| Code clarity & structure | 0.5   |
| UI polish & extras       | 0.5   |
| **Total**                | 2.0   |

---

## 📂 Repo Layout

```
├── index.html   # Main UI
├── agent.js     # Core agent + providers + tools
├── styles.css   # Custom styling
└── README.md    # Docs
```

---

## 🙏 Credits

* AI Pipe for workflow API
* OpenAI / Anthropic / Google for LLM APIs
* Bootstrap for quick styling

---

🔮 **Future Directions**

* Save conversation history in browser storage.
* Support streaming responses.
* Add more tools (charts, file parsing, SQL queries).

---
