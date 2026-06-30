# post_genarator
AI-powered LinkedIn Post Generation Agent built with LangGraph conditional workflows.
# 🚀 AI LinkedIn Post Generation Agent using LangGraph

An AI-powered LinkedIn Post Generation Agent built with **LangGraph**, **LangChain**, and an LLM. This project uses a **Writer–Reviewer multi-agent workflow** with **conditional edges** to iteratively improve the quality of generated posts instead of relying on a single LLM response.

---

## 📌 Overview

Most AI content generators rely on a single prompt to produce an output. While this works for simple tasks, the quality often suffers due to weak hooks, repetitive content, or poor structure.

This project demonstrates how **LangGraph** can orchestrate multiple AI agents that collaborate to produce better content.

The workflow consists of:

- ✍️ Writer Agent – Generates the LinkedIn post
- 🔍 Reviewer Agent – Reviews and improves the post
- 🔄 Conditional Routing – Determines whether another iteration is needed
- ✅ Final Output – Returns a polished LinkedIn post

---

## 🏗️ Workflow

```text
                User Topic
                     │
                     ▼
              HumanMessage
                     │
                     ▼
              Writer Agent
                     │
                     ▼
          Generate First Draft
                     │
                     ▼
            Condition Check
             │             │
      Continue           Stop
             │             │
             ▼             ▼
       Reviewer Agent      END
             │
             ▼
     Improve the Draft
             │
             ▼
        Writer Agent
```

The Writer and Reviewer collaborate until the stopping condition is satisfied.

---

# ✨ Features

- Multi-Agent architecture using LangGraph
- Writer and Reviewer workflow
- Conditional edges for iterative refinement
- AI-generated LinkedIn posts
- Modular prompt templates
- Easy to customize
- Beginner-friendly implementation

---

# 🛠️ Tech Stack

- Python
- LangGraph
- LangChain
- OpenAI / Gemini / Groq LLM
- Google Colab

---

# 📂 Project Structure

```text
langgraph-post-generation-agent/
│
├── post_generator.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── images/
```

---

# ⚙️ Installation

## Clone the repository

```bash
git clone https://github.com/your-username/langgraph-post-generation-agent.git
```

```bash
cd langgraph-post-generation-agent
```

---

## Install dependencies

```bash
pip install -r requirements.txt
```

---

## Configure API Key

Create a `.env` file.

```text
OPENAI_API_KEY=your_api_key
```

or

```text
GOOGLE_API_KEY=your_api_key
```

depending on the LLM you're using.

---

# ▶️ Usage

Open the notebook:

```text
post_generator.ipynb
```

Run all cells.

Provide any topic:

```text
Write a LinkedIn post about GraphRAG
```

The LangGraph workflow will:

1. Generate a draft
2. Review the draft
3. Improve it
4. Repeat until the stopping condition is met
5. Return the final LinkedIn post

---

# 🧠 How It Works

## Step 1

User provides a topic.

Example:

```text
Write a LinkedIn post about AI Agents
```

↓

## Step 2

Writer Agent generates the first draft.

↓

## Step 3

The workflow evaluates a condition.

```python
if len(state["messages"]) >= 5:
    return END
else:
    return "Reviewer"
```

↓

## Step 4

Reviewer Agent critiques and improves the draft.

↓

## Step 5

The improved version is sent back to the Writer.

↓

## Step 6

The Writer creates an even better version.

↓

## Step 7

The cycle repeats until the stopping condition is reached.

↓

## Final Output

A polished LinkedIn post.

---

# 📸 Example

### Input

```text
Write a LinkedIn post about GraphRAG
```

### Output

- Strong hook
- Problem statement
- Insightful explanation
- Clear structure
- Call-to-action
- Relevant hashtags

---

# 💡 Why LangGraph?

Instead of asking an LLM to generate content once, LangGraph enables:

- Agent collaboration
- Iterative refinement
- Better reasoning workflows
- Modular AI systems
- Conditional execution
- Scalable AI pipelines

---

# 🚀 Future Improvements

- Multiple reviewer agents
- SEO optimization
- Blog generation
- Twitter/X post generation
- Tone selection
- Automatic image generation
- Human feedback loop
- Streamlit interface

---

# 📦 Requirements

```text
langgraph
langchain
langchain-openai
python-dotenv
ipykernel
```

---

# 🤝 Contributing

Contributions are welcome!

Feel free to fork the repository, open issues, or submit pull requests to improve the project.

---

# 📄 License

This project is licensed under the MIT License.

---

## ⭐ If you found this project useful

Please consider giving it a ⭐ on GitHub. It helps others discover the project and motivates future improvements.
