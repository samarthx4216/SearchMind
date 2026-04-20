# 🔎 LangChain - Chat with Search

A conversational AI chatbot built with **LangChain** and **Streamlit** that can search the web, query Wikipedia, and look up academic papers on ArXiv — all in real time.

---

## ✨ Features

- 🌐 **Web Search** via DuckDuckGo
- 📚 **Wikipedia** lookups
- 🧪 **ArXiv** academic paper search
- 🤖 Powered by **Groq LLMs** (LLaMA 3, Qwen)
- 💬 Persistent chat history within a session
- 🧠 Live agent thought visualization using `StreamlitCallbackHandler`

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| UI | Streamlit |
| LLM Provider | Groq (`langchain-groq`) |
| Agent Framework | LangChain |
| Search Tools | DuckDuckGo, Wikipedia, ArXiv |
| Environment Config | python-dotenv |

---

## 📦 Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 📄 Requirements

Create a `requirements.txt` with the following:

```
streamlit
langchain
langchain-groq
langchain-community
duckduckgo-search
wikipedia
arxiv
python-dotenv
```

---

## 🔑 Configuration

### Option A — `.env` file (recommended)

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

### Option B — Sidebar input

Enter your Groq API key directly in the app's sidebar at runtime. No `.env` file needed.

> Get your free Groq API key at [console.groq.com](https://console.groq.com)

---

## 🚀 Running the App

```bash
streamlit run app.py
```

Then open [http://localhost:8501](http://localhost:8501) in your browser.

---

## 🧩 How It Works

1. The user types a question in the chat input.
2. A **ZERO_SHOT_REACT** LangChain agent decides which tool(s) to use:
   - **DuckDuckGo** for general web queries
   - **Wikipedia** for encyclopedic information
   - **ArXiv** for scientific/research papers
3. The agent's reasoning steps are displayed live via `StreamlitCallbackHandler`.
4. The final answer is shown in the chat and saved to session history.

---

## 🎛️ Sidebar Options

| Option | Description |
|---|---|
| **Groq API Key** | Your secret key for accessing Groq-hosted LLMs |
| **Model** | Choose between `llama-3.3-70b-versatile`, `llama-3.1-8b-instant`, or `qwen/qwen3-32b` |

---

## 📁 Project Structure

```
your-repo-name/
├── app.py              # Main Streamlit application
├── .env                # Environment variables (do not commit)
├── .gitignore
├── requirements.txt
└── README.md
```

---

## ⚠️ Known Limitations

- DuckDuckGo search may occasionally be rate-limited.
- ArXiv and Wikipedia results are capped at 200 characters per result for brevity.
- Chat history is session-scoped and resets on page refresh.

---

## 🙌 Acknowledgements

- [LangChain](https://www.langchain.com/)
- [Streamlit](https://streamlit.io/)
- [Groq](https://groq.com/)
- [LangChain Streamlit Agent Examples](https://github.com/langchain-ai/streamlit-agent)
