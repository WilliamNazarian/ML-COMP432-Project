# Amazon Reviews Pipeline

Four quick moves:

| Step | Action | Output you must download |
|------|--------|--------------------------|
| 1 | **Run `Part_1_baseline_kaggle.ipynb`** up to the “CLS embeddings for baseline models” header. | —
| 2 | Zip & download the `amazon_reviews_data/` folder which contains the arrow_clean folder which has the (`train`, `validation`, `test`) folders and the dtaset_dict.json file, and each of those folders contain `dataset.arrow`, `dataset.info.json`, `state.json` | `amazon_reviews_data.zip` 
| 3 | **Run `Part_2_DistilBert.ipynb`** end‑to‑end. | `cls_embeddings.zip` this is what you see you have to download in the notebook, but only the winning models cls information should be donwloaded
| 4 | Back in **Part 1**, upload winning models cls files inside `cls_embeddings/`, then run the rest of the notebook. | Final baseline scores



GPU recommended (Colab: *Runtime → Change runtime type → GPU*).


