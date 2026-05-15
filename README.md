# TS-Capstone
# 🤖 Joana — AI Chatbot

An intent-based conversational chatbot built with TensorFlow/Keras, designed to run entirely in **Google Colab** — no local setup required.

---

## 🚀 Quick Start (Google Colab)

1. Open [Google Colab](https://colab.research.google.com)
2. Click **File → Upload notebook** and upload `Joana_Chatbot.ipynb`
3. Run each cell top to bottom using **Shift + Enter** or **Runtime → Run all**

That's it — no file uploads needed. The notebook creates all required files automatically.

---

## 📁 Project Structure

```
├── Joana_Chatbot.ipynb   # Main notebook (install → train → chat)
├── requirements.txt      # Python dependencies
└── README.md
```

> **Generated at runtime** (not committed to the repo):
> `intents.json` · `chat_model/` · `tokenizer.json` · `label_encoder.json`

---

## 📓 Notebook Cells

| Cell | What it does |
|------|-------------|
| 1 | Installs `colorama` |
| 2 | Creates `intents.json` with all training data |
| 3 | Trains the Keras model (≈ 1 min, 500 epochs) |
| 4 | Saves model, tokenizer, and label encoder |
| 5 | Launches the interactive chat loop |

---

## 🧠 Model Architecture

```
Embedding (1000 vocab, 16 dims)
     ↓
GlobalAveragePooling1D
     ↓
Dense(16, relu)
     ↓
Dense(16, relu)
     ↓
Dense(num_classes, softmax)
```

- **Loss:** Sparse Categorical Crossentropy  
- **Optimizer:** Adam  
- **Epochs:** 500  

---

## 💬 Supported Intents

| Tag | Example Patterns |
|-----|-----------------|
| `greeting` | Hi, Hello, Hey |
| `goodbye` | Bye, See you later |
| `thanks` | Thank you, Thanks |
| `about` | Who are you? |
| `name` | What is your name? |
| `help` | Can you help me? |
| `createaccount` | I want to create an account |
| `complaint` | I want to raise a complaint |

---

## ➕ Adding New Intents

In **Cell 2** of the notebook, add a new object to the `intents` list:

```python
{
  "tag": "your_tag",
  "patterns": ["example question 1", "example question 2"],
  "responses": ["Response A", "Response B"]
}
```

Then re-run all cells to retrain with the updated data.

---

## 🛠 Dependencies

See `requirements.txt`. Key libraries:

- `tensorflow >= 2.10.0`
- `scikit-learn >= 1.0.0`
- `numpy >= 1.21.0`
- `colorama >= 0.4.6`

> These are pre-installed in Google Colab except `colorama`, which Cell 1 installs automatically.

---

## 👤 Author

**Pravallika Gangadevi**  
Performance Solutions — Marketing & Partnerships Team  
Large Customer Sales, Google India
