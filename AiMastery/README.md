# AI Roadmap — From Absolute Scratch to Advanced

A complete, no-fluff path to learning AI: what to know, in what order, and what to build to prove it. Structured so you can drop it straight into a GitHub repo as your learning log / portfolio README.

---

## How to use this roadmap

- Work top to bottom. Don't skip Math/Python — everything after leans on it.
- Every stage has a **"build this"** project. Push each one to GitHub. That's your proof of work.
- Don't try to "finish" AI. Get functional at each stage, ship something, move on.

---

## Stage 0 — Setup (Week 1)

You need these tools before anything else:

- **Python 3.10+** — the language almost all AI work happens in
- **Git + GitHub account** — version control, and where your work lives
- **VS Code** (or PyCharm) — code editor
- **Jupyter Notebook / Google Colab** — for experimenting with code + seeing outputs inline (Colab = free GPU, no install)
- **Anaconda or venv** — managing Python environments so projects don't conflict

**Learn the Git basics you'll actually use:**
```
git init, git add, git commit, git push, git pull, git clone, git branch, git merge
```

**Build this:** Create a GitHub repo called `ai-learning-log`. Every project below becomes a folder in it, with its own README.

---

## Stage 1 — Math you actually need (2–4 weeks)

You don't need a math degree. You need working intuition for these:

| Topic | Why it matters | What to know |
|---|---|---|
| **Linear Algebra** | Data = vectors/matrices; neural nets = matrix multiplication | vectors, matrices, dot product, matrix multiplication |
| **Statistics & Probability** | Models reason under uncertainty | mean, variance, distributions, Bayes' theorem |
| **Calculus** | Training = optimization via gradients | derivatives, gradients, chain rule (just enough to understand backpropagation) |

You don't need to derive proofs — you need to understand *what's happening* when a model "learns."

**Resource:** 3Blue1Brown's "Essence of Linear Algebra" and "Neural Networks" video series (YouTube, free, extremely intuitive).

---

## Stage 2 — Python for AI (2–3 weeks)

Beyond basic syntax, learn the actual data-science stack:

- **NumPy** — arrays, vectorized math
- **Pandas** — loading, cleaning, exploring data
- **Matplotlib / Seaborn** — visualizing data
- **Jupyter workflow** — writing code in cells, plotting inline

**Build this:** Pick any public dataset (Kaggle, or `pandas.read_csv` on a CSV you find). Clean it, explore it, make 3 charts. Push to `ai-learning-log/01-python-eda`.

---

## Stage 3 — Machine Learning fundamentals (4–6 weeks)

This is the core of "AI" as most people mean it. Learn the concepts, not just the library calls.

**Core concepts:**
- Supervised vs. unsupervised vs. reinforcement learning
- Features, labels, training set vs. test set, overfitting vs. underfitting
- Train/validation/test split, cross-validation
- Bias-variance tradeoff
- Evaluation metrics: accuracy, precision, recall, F1, RMSE, ROC-AUC

**Core algorithms (know how each works conceptually, then use them):**
- Linear regression, logistic regression
- Decision trees, random forests
- k-nearest neighbors (KNN)
- k-means clustering
- Support vector machines (SVM) — good to know exists, less critical now
- Gradient boosting (XGBoost / LightGBM) — very widely used in industry

**Tools:** `scikit-learn` (the standard library for all of the above)

**Build this:** A classification project (e.g., predict survival on Titanic dataset, or spam vs. not-spam) end-to-end: load data → clean → train a model → evaluate → write up results in the README. Push to `ai-learning-log/02-ml-classifier`.

---

## Stage 4 — Deep Learning fundamentals (4–8 weeks)

This is where "AI" gets to what most people picture today.

**Concepts:**
- What a neural network actually is: neurons, weights, biases, layers
- Activation functions (ReLU, sigmoid, softmax) — and why nonlinearity matters
- Forward pass vs. backpropagation
- Loss functions and gradient descent (and variants: SGD, Adam)
- Epochs, batch size, learning rate
- Overfitting solutions: dropout, regularization, early stopping

**Architectures to understand (in order of when to learn them):**
1. **Feedforward / Dense networks** — the basic building block
2. **CNNs (Convolutional Neural Networks)** — images
3. **RNNs / LSTMs** — sequences (mostly historical now, but good for intuition)
4. **Transformers** — the architecture behind basically all modern AI (GPT, BERT, etc.) — this is the most important one to actually understand deeply

**Tools:** `PyTorch` (recommended — it's what most research and modern industry code uses) or `TensorFlow/Keras`

**Build this:** Train an image classifier (CNN) on something like MNIST or CIFAR-10. Then, separately, fine-tune a small pretrained model on a text classification task. Push to `ai-learning-log/03-deep-learning`.

---

## Stage 5 — How modern AI (LLMs) actually works (3–5 weeks)

This is the "ChatGPT-era" layer people usually mean when they say "AI" in 2026.

**Concepts to actually understand:**
- Tokens and tokenization
- Embeddings (what they are, why "meaning" becomes a vector)
- The Transformer architecture: attention, self-attention, multi-head attention, positional encoding
- Pretraining vs. fine-tuning vs. instruction-tuning vs. RLHF
- Context windows, and why they're limited
- Prompting: zero-shot, few-shot, chain-of-thought
- Hallucination — why it happens, why it's fundamental to how these models work
- Embeddings + vector databases → **RAG (Retrieval-Augmented Generation)** — how you make an LLM answer using your own data
- Fine-tuning vs. RAG vs. prompt engineering — when to use which

**Practical skills:**
- Using an LLM API (OpenAI, Anthropic, etc.) — sending prompts, handling responses, system prompts
- Building a basic RAG pipeline (embed documents → store in a vector DB like Chroma/FAISS/Pinecone → retrieve → feed to LLM)
- Agent basics: tool use, function calling, letting a model call APIs / run code

**Build this:** A small RAG app — e.g., "chat with your PDF/notes." Push to `ai-learning-log/04-llm-rag-app`.

---

## Stage 6 — Applied AI Engineering (ongoing)

This is where you go from "understands AI" to "ships AI products."

- **APIs & backend:** FastAPI/Flask to wrap models as a service
- **MLOps basics:** experiment tracking (Weights & Biases / MLflow), model versioning, reproducibility
- **Deployment:** Docker, deploying a model behind an API, basic cloud (AWS/GCP/Azure or simpler platforms like Render/Vercel)
- **Data pipelines:** ETL basics, handling real messy data at scale
- **Vector databases** in depth: Pinecone, Weaviate, Chroma, FAISS
- **Agent frameworks:** LangChain, LlamaIndex, or building agents from scratch with raw function calling
- **Evaluation of LLM apps:** how do you know your RAG/agent is actually good? (eval sets, LLM-as-judge, human eval)

**Build this:** Take your RAG app from Stage 5 and make it a real product: add a UI (Streamlit/simple React frontend), deploy it, write proper docs. This becomes your flagship portfolio repo.

---

## Stage 7 — Advanced / Research-adjacent (optional, pick based on interest)

Only go here once Stages 0–6 are solid.

- **Reinforcement Learning:** MDPs, Q-learning, policy gradients, RLHF in depth
- **Generative models:** GANs, diffusion models (how Stable Diffusion/image generators work)
- **Model architecture research:** reading papers (start with "Attention Is All You Need," then follow citations)
- **Fine-tuning at scale:** LoRA/QLoRA, parameter-efficient fine-tuning
- **Multi-agent systems:** multiple LLM agents coordinating
- **Model efficiency:** quantization, distillation, pruning
- **Reading papers regularly:** arXiv, Papers With Code — build the habit of reading one paper a week

---

## Your GitHub portfolio structure (suggested)

```
ai-learning-log/
├── README.md              ← this roadmap + your progress checklist
├── 01-python-eda/
├── 02-ml-classifier/
├── 03-deep-learning/
├── 04-llm-rag-app/
├── 05-deployed-project/
└── notes/                 ← your own written explanations of concepts (writing = best way to prove you understand)
```

**Tip:** Recruiters and collaborators skim READMEs, not code first. Each project folder should have its own short README: what it does, what you learned, how to run it.

---

## Free resources worth using

- **3Blue1Brown** (YouTube) — math and neural network intuition
- **Andrej Karpathy's "Neural Networks: Zero to Hero"** (YouTube) — build a transformer from scratch, line by line
- **fast.ai** — practical deep learning, top-down approach
- **Andrew Ng's Machine Learning Specialization** (Coursera) — classic, rigorous ML foundations
- **Hugging Face NLP Course** (free, on huggingface.co) — practical transformers/LLM course
- **Papers With Code** — papers + implementations side by side

---

## Realistic timeline

- **Casual pace (5–10 hrs/week):** Stage 0–4 in ~4-5 months, Stage 5-6 in another 3-4 months
- **Intense pace (20-30 hrs/week):** Stage 0–6 in ~3-4 months

There's no finish line — Stage 7 and beyond is a career, not a checklist. The goal of this roadmap is to get you from zero to *functional and employable/project-capable*, not to "complete AI."
