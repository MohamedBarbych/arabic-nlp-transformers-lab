
# 🧠 Arabic NLP – Deep Learning Lab (Atelier 3)

## 🎓 Université Abdelmalek Essaadi – Master MBD  
**Instructor**: Pr. Elaachak Lotfi  
**Author**: Mohamed BARBYCH

---

## 📚 Description

This project is a complete deep learning lab for **Arabic Natural Language Processing (NLP)** using both:
- **Sequence Models** (RNN, Bi-RNN, GRU, LSTM)
- **Transformer-based GPT-2 fine-tuning** for text generation.

It is divided into two main parts:
- **Part 1**: Classification of Arabic news headlines with semantic scoring.
- **Part 2**: Fine-tuning an Arabic GPT-2 model (`aragpt2-base`) to generate realistic Arabic text.

---

## 📁 Folder Structure

```
.
├── Atelier3_Part1_1.ipynb            # Scraping, scoring, preprocessing
├── Atelier3_Part1_2.ipynb            # RNN, GRU, LSTM classification + metrics
├── Atelier3_Part2_ArabicGPT2.ipynb   # GPT-2 fine-tuning and generation
├── arabic_data.txt                   # Custom Arabic sentences for generation
├── custom.txt                        # Short demo sentences for quick tuning
├── data_scraped.csv                 # Scraped headlines from Hespress
├── data_semantically_scored.csv     # Labeled headlines with relevance scores
```

---

## 🧪 Part 1 – Classification with Sequence Models

### ✅ Objective
Build a semantic classifier that evaluates the **relevance of Arabic news** headlines.

### 🔧 Models Used:
- RNN
- Bidirectional RNN
- GRU
- LSTM

### 📊 Preprocessing Techniques:
- Arabic tokenization using `ToktokTokenizer`
- Stemming using `ISRIStemmer`
- Stopword removal with NLTK
- Discretization of semantic scores into 5 bins

### 🧠 Results (Summary):

| Model   | Accuracy | Observations |
|---------|----------|--------------|
| RNN     | ~45%     | Bias toward dominant class (1) |
| Bi-RNN  | ~48%     | Slight improvement due to bidirectionality |
| GRU     | ~43%     | Requires longer training & more data |
| LSTM    | ~43%     | Struggled with short TF-IDF input vectors |

➡️ **Conclusion**: While the models are functional, performance is limited by:
- Small dataset size
- Label imbalance
- TF-IDF input limitations for sequential architectures

---

## 🤖 Part 2 – Arabic GPT-2 Fine-Tuning

### ✅ Objective
Use the pre-trained **Arabic GPT-2 (aragpt2-base)** model to generate new political/news content.

### 📁 Dataset
Used `arabic_data.txt` with short political-style statements:
```
الملك يترأس اجتماعًا وزاريًا مهمًا
المملكة تطور شراكات استراتيجية جديدة
...
```

### 🔁 Training Loop
- Model: `aubmindlab/aragpt2-base`
- Epochs: 3
- Loss: Decreased steadily
- Tokenizer padding set to EOS to prevent errors

### ✨ Example Generation

**Input**: `المغرب`  
**Output**: *(after fine-tuning)*  
```
المغرب يواصل توسيع شراكاته الاقتصادية في المنطقة الإفريقية مع تعزيز دوره الدبلوماسي على المستوى الدولي.
```

➡️ GPT-2 trained on Arabic text produced **semantically and syntactically correct** completions.

---

## ✅ What I Learned

- How to collect and clean Arabic text data
- How to build RNN-based classifiers using PyTorch
- How tokenization, stopwords, and class imbalance affect performance
- How to fine-tune pretrained transformer models for Arabic text generation
- How to control text creativity using sampling methods (`top_k`, `top_p`, `temperature`)

---

## 🚀 How to Run

### 🔗 On Google Colab:
```python
!pip install transformers
```
Then open `.ipynb` files and run the cells as instructed.

---

## 📤 Deployment

You can later:
- Host this as a demo app using Gradio or Streamlit
- Connect it to an Arabic headline auto-generator

---

## 📎 References

- [Huggingface Transformers](https://huggingface.co)
- [AUB Mind Lab – aragpt2-base](https://huggingface.co/aubmindlab/aragpt2-base)
- [Gist inspiration for GPT-2 fine-tuning](https://gist.github.com/mf1024/3df214d2f17f3dcc56450ddf0d5a4cd7)

---

## ✅ Final Note

This lab was a great opportunity to dive deep into **Arabic NLP**, mixing classic sequence modeling with modern transformers.

**Thank you!**
