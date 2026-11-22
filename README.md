# LLM Sentiment Analysis — TP

**Master 2 Vision et Machine Intelligente (VMI)** — Université Paris Cité

Dans ce TP, j'ai utilisé **RoBERTa** pour classer des critiques de films du dataset **Rotten Tomatoes** en deux classes : positif et négatif. J'ai comparé plusieurs méthodes avec le même jeu de test.

## Notebooks

- [tp-llm.ipynb](tp-llm.ipynb) : inférence sans entraînement, linear probing, fine-tuning complet et partiel, métriques et figures.
- [tp-llm-5-epochs.ipynb](tp-llm-5-epochs.ipynb) : expérience supplémentaire avec les 8 dernières couches pendant 5 époques maximum.

## Résultats

| Méthode | Accuracy | F1 macro |
|---|---:|---:|
| Sans entraînement | 80,02 % | 79,89 % |
| Linear probing strict | 83,11 % | 83,07 % |
| Fine-tuning complet | **86,87 %** | **86,87 %** |
| Fine-tuning des 4 dernières couches | 86,30 % | 86,29 % |
| Tête de classification seule | 83,02 % | 83,02 % |
| Fine-tuning des 8 dernières couches | 86,68 % | 86,60 % |

Dans le test supplémentaire à 5 époques, le meilleur F1 sur validation est à l'époque 3. Continuer l'entraînement n'a pas amélioré le résultat sur le test.

## Modèle et outils

- [Dataset Rotten Tomatoes](https://huggingface.co/datasets/cornell-movie-review-data/rotten_tomatoes)
- [Modèle RoBERTa](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest)
- Python, PyTorch, Transformers, Datasets, scikit-learn
- Environnement : Kaggle avec GPU Tesla T4

## Exécution

Ouvrir le notebook sur Kaggle, activer le GPU et Internet, puis exécuter les cellules dans l'ordre. Les notebooks enregistrés contiennent les sorties, métriques et figures des expériences.
