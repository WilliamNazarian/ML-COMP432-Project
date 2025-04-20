# Amazon Reviews Sentiment Pipeline 🚀

A lightweight two‑notebook workflow that lets you

1. build strong TF‑IDF + classical baselines,  
2. fine‑tune DistilBERT,  
3. compare the two approaches on identical splits.

Everything runs on free Google Colab GPUs.

---

## 📦 What You’ll Need

| Requirement | Why it’s needed | Links |
|-------------|----------------|-------|
| **Google Colab** with a GPU runtime (`Runtime → Change runtime type → GPU`) | Training DistilBERT quickly | —
| **Kaggle account** + `kaggle.json` credentials | Automatic download of the Amazon Reviews dataset | [Docs](https://www.kaggle.com/docs/api) |
| **~5 GB of free Drive / local disk** | Caches datasets, checkpoints, and embeddings | —

---

## ⚡ Quick‑Start (4 Moves)

| # | Do this → | Produces ↓ |
|---|-----------|-----------|
| **1** | Open **`Part_1_baseline_kaggle.ipynb`** and run every cell **up to** the heading **“CLS embeddings for baseline models”**. | — |
| **2** | Zip **`amazon_reviews_data/`** (it now contains `arrow_clean/` with `train / validation / test` splits) and download it. | `amazon_reviews_data.zip` |
| **3** | Run **`Part_2_DistilBert.ipynb`** top‑to‑bottom. | `cls_embeddings.zip` <br>*(only download the embeddings of the **winning** DistilBERT model)* |
| **4** | Go back to **`Part 1`**, upload the contents of `cls_embeddings.zip` into `cls_embeddings/`, then execute the remainder of that notebook. | Final baseline vs DistilBERT scores |

> **Tip:** Steps 2 & 3 each show a *single* zip‑file link in the Colab sidebar; just click to download.

---

## 🗂️ Directory Cheat‑Sheet

```
amazon_reviews_data/
 ├─ arrow_clean/              ← HF DatasetDict (train / val / test)
 └─ artifacts/                ← TF‑IDF vectoriser & best classical model
cls_embeddings/
 ├─ <exp>_train_embeddings.npy
 ├─ <exp>_validation_embeddings.npy
 └─ <exp>_test_embeddings.npy  ← upload these before rerunning Part 1 tail
```

---

## ❓ FAQ / Troubleshooting

* **Notebooks look blank on GitHub.**  
  GitHub often fails to render large Colab notebooks. Click **“Open in Colab”** and they load fine. (GitHub issue #155944)

* **“kaggle: command not found”**  
  Run `!pip install kaggle` in the first cell of *Part 1* and re‑upload `kaggle.json`.

* **CUDA out‑of‑memory during DistilBERT fine‑tune**  
  Switch Colab to a fresh session or reduce `batch_size` in the configuration cell near the top of *Part 2*.

---

## 📄 Project Files

| Notebook / Script | Purpose |
|-------------------|---------|
| **`Part_1_baseline_kaggle.ipynb`** | Download & clean data, create classical baselines, evaluate CLS embeddings |
| **`Part_2_DistilBert.ipynb`** | Comprehensive DistilBERT fine‑tuning, hyper‑parameter search, CLS extraction |
| `Part1-Part3-LogRegSVM-CLS_embeddings.py` | Python export of *Part 1* logic (optional CLI use) |
| `Part2_DistilBert.py` | Python export of *Part 2* (optional CLI use) |

---



