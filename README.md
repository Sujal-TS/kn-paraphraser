# 📝 KnParaphraser: Kannada Paraphrasing using Novel Data Augmentation Framework

A Kannada paraphrasing model designed for low-resource NLP, using a novel data augmentation framework powered by Round-Trip Translation (RTT) and Transformer-based models. This project includes a custom fine-tuned **KnT5 model** and a publicly available **100k+ sentence paraphrase corpus**.

---

## 📌 Highlights

- ⚡ Fine-tuned `mT5` reduced to Kannada-specific `KnT5`
- 🔁 Round Trip Translation with NLLB-200 using **5 decoding strategies**
- 🧠 Evaluation using BLEU and semantic similarity (IndicSBERT)
- 📂 Dataset + Model released publicly for Kannada NLP tasks

---

## 📚 Abstract

Paraphrase generation in low-resource languages like Kannada is challenging due to the lack of large, high-quality corpora. We propose a data augmentation framework using Round Trip Translation (RTT) with diverse decoding strategies (Greedy, Beam, Top-K, Top-P, Combined) to generate a rich and lexically varied Kannada paraphrase corpus. A reduced mT5 model (`KnT5`) is fine-tuned on this dataset, resulting in the `KnParaphraser` model.

---

## 📊 Dataset

- **Source**: [Samanantar Kn-En Dataset](https://arxiv.org/abs/2104.05596)
- **Augmented using**: NLLB-200 (Meta AI)
- **Total Pairs**: ~87,000 high-quality sentence pairs
- **Corpus**: [KanPara Dataset](https://huggingface.co/datasets/shraajan/KanPara)

---

## 🤖 Model

- **Base**: [google/mt5-base](https://huggingface.co/google/mt5-base)
- **Reduced to**: Kannada-specific `KnT5` using token frequency filtering
- **Fine-tuned Model**: [shraajan/t5-knparaphraser](https://huggingface.co/shraajan/t5-knparaphraser)
- **Training Config**:
  - Epochs: 5
  - Batch Size: 4
  - Optimizer: Adam
  - Learning Rate: 3e-5
  - Steps: 27,195

---

## 📈 Evaluation

| Method            | BLEU Score | Semantic Similarity |
|-------------------|------------|----------------------|
| Greedy            | 0.2978     | 0.8977               |
| Beam              | 0.3062     | 0.9133               |
| Top-K Sampling    | 0.2754     | 0.8881               |
| Top-P Sampling    | 0.2807     | 0.8919               |
| Combined Sampling | 0.1793     | 0.7696               |

- Final Model Evaluation: BLEU: **0.1967**, Similarity: **0.8133** (on 1000 unseen sentences)

---

## 💡 Example

**Input Kannada Sentence:**
