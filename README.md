# TP fine-tuning de LLM avec LoRA

Dans ce TP, vous allez adapter un LLM open-weight ([Qwen3-1.7B](https://huggingface.co/Qwen/Qwen3-1.7B)) à une tâche précise, le résumé de dialogues ([DialogSum](https://huggingface.co/datasets/knkarthick/dialogsum)), par *fine-tuning* supervisé avec la méthode LoRA, sur le GPU gratuit de Google Colab.

En sortie de ce module, vous serez capable de :
- Choisir entre prompt engineering, RAG et fine-tuning, et estimer la mémoire nécessaire à un entraînement
- Préparer un jeu de données au format *prompt / completion* avec le *chat template* du modèle
- Expliquer le masquage de la perte : sur quels tokens le modèle apprend-il ?
- Configurer LoRA (rang, alpha, modules ciblés) et calculer le nombre de paramètres entraînés
- Entraîner avec la bibliothèque TRL (`SFTTrainer`) et lire une courbe de perte
- Évaluer le modèle fine-tuné face au modèle de base (ROUGE, exemples, oubli catastrophique)
- Sauvegarder, recharger et fusionner un adaptateur LoRA
- (Mini-projet) Appliquer QLoRA à un modèle plus gros, ou étudier l'effet de la quantité de données

Prérequis : le TP d'initiation aux LLM (tokenizer, *chat template*, génération, ROUGE).

## Exercices

Répondre aux questions dans le notebook [tp-fine-tuning.ipynb](./tp-fine-tuning.ipynb), en l'ouvrant dans Colab avec le bouton *Open in Colab* en haut du notebook.

La notation prendra également en compte la qualité de votre code et son optimisation.

## Environnement : 100 % gratuit

Aucune dépense n'est nécessaire pour ce TP.

| Besoin | Solution gratuite |
|---|---|
| GPU (principal) | [Google Colab](https://colab.research.google.com) : `Exécution -> Modifier le type d'exécution -> T4 GPU` |
| GPU (si Colab n'a plus de GPU disponible) | [Kaggle Notebooks](https://www.kaggle.com/code) : environ 30 h de GPU par semaine, `Settings -> Accelerator -> GPU T4 x2` |

Une session Colab gratuite est limitée dans le temps : sauvegardez votre adaptateur LoRA (quelques dizaines de Mo) sur Google Drive si vous voulez le réutiliser.
