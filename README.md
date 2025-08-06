# 🔍 Pipeline RAG sur les Accords d'Entreprise – Heures Supplémentaires

Ce projet met en place une pipeline **Retrieval-Augmented Generation (RAG)** appliquée à un échantillon de 1000 accords d'entreprise portant sur les **heures supplémentaires**.

## 📁 Structure du Notebook

### 1. `create_vectorstore_textsplitter`

Génère une base vectorielle nommée **`chroma_db_v0`** à partir des textes des accords, avec découpage des documents selon :

* `CharacterTextSplitter` ou
* `RecursiveCharacterTextSplitter`

> 💡 À adapter selon le niveau de granularité souhaité pour les passages indexés.

---

### 2. `create_vectorstore_article`

Génère une base vectorielle nommée **`chroma_db_article`**, cette fois en découpant les documents selon leur **structure en articles** (basée sur le sommaire).

---

### 3. `results_article`

Lance la pipeline **RAG** sur un ensemble de **100 accords annotés**.

* Évalue la pertinence des réponses générées.
* Possibilité de spécifier le chemin vers une base vectorielle différente (ex : `chroma_db_v0`).

> ✅ Permet de comparer les performances selon le mode de découpage choisi (texte brut vs articles).

---

### 4. `comparaison_k`

Compare les performances de la pipeline RAG en faisant varier le nombre de documents récupérés `k` (de 1 à 10).

* Analyse l'impact du paramètre `k` sur la qualité des réponses.
* Permet de trouver un bon compromis entre **rappel** et **précision**.

---

## 🚀 Objectif

Explorer différentes stratégies de découpage des documents pour :

* Optimiser la pertinence de la récupération dans le cadre de RAG.
* Adapter le découpage aux spécificités des **accords**.
* Quantifier l'impact de ces choix sur les performances finales.

---

