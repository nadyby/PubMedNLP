# Exploration des Thématiques Médicales dans PubMed

Ce projet explore les thématiques médicales dans un corpus de **949 articles PubMed** (2024-2025) via un pipeline de NLP : **scraping** avec BeautifulSoup à partir du site PubMed : https://pubmed.ncbi.nlm.nih.gov/ , annotation avec **BioBERT** (DISEASE, CELL_TYPE), et apprentissage non supervisé **(K-means, LDA)**. Il identifie **5 thématiques principales** : **troubles variés, maladies systémiques, cancers localisés, carcinomas, et diabète**.

## Structure du projet 📂

Voici une vue d'ensemble des fichiers et dossiers principaux du projet :

```plaintext
Projet PubMedNLP/
├── annotation/
├── ├── annotated_articles.json   # Articles annotés
├── ├── phase_annotation.ipynb    # Notebook de la phase d'annotation
├── apprentissage/
├── ├── phase_apprentissage.ipynb # Notebook de la phase d'apprentissage
├── scraping/
├── ├── articles.json             # Articles sous format json extraits du site PubMed
├── ├── articles.txt              # Articles sous format json extraits du site PubMed
├── ├── phase_scraping.ipynb      # Notebook de la phase de scraping
│── README.md                     # Documentation du projet
│── Rapport                       # Rapport détaillé du projet
├── requirements.txt              # Liste des dépendances Python
```


## Structure du Rapport
- **Chapitre 1**: Scraping des articles (`articles.json`).
- **Chapitre 2**: Annotation avec le modèle BioBERT (`annotated_articles.json`).
- **Chapitre 3**: Clustering (k=5) et Topic Modeling (LDA).

## Utilisation
1. Clonez le dépôt : `git clone https://github.com/nadyby/PubMedNLP`
2. Installez les dépendances : `pip install -r requirements.txt`


## Résultats
Le clustering et LDA révèlent une prédominance des cancers et du diabète dans les recherches récentes.


- **Clusters K-means (k=5)** :
  - **Cluster 0 (268 articles)** : Regroupe des troubles variés, incluant des maladies neurologiques et des conditions diverses (ex. "multiple sclerosis", "glioblastoma").
  - **Cluster 1 (86 articles)** : Thématique des maladies systémiques affectant les organes (ex. "cardiovascular disease").
  - **Cluster 2 (161 articles)** : Regroupe les cancers localisés par organe (ex. "breast cancer", "lung cancer").
  - **Cluster 3 (35 articles)** : Focalisé sur les carcinomas (ex. "hepatocellular carcinoma").
  - **Cluster 4 (36 articles)** : Spécifique au diabète et ses variantes (ex. "diabetes").

- **Topics LDA (5 topics)** :
  - **Topic 0 (varié)** : Mélange de cancers et maladies systémiques (ex. "colorectal cancer").
  - **Topic 1 (carcinomas et cancers)** : Focalisé sur les carcinomes et certains cancers (ex. "hepatocellular carcinoma").
  - **Topic 2 (cancers pulmonaires)** : Dominé par les cancers pulmonaires (ex. "lung cancer").
  - **Topic 3 (diabète)** : Centré sur le diabète et conditions associées (ex. "diabetes").
  - **Topic 4 (cancers digestifs)** : Mélange de cancers digestifs et maladies systémiques (ex. "gastric cancer").

### Conclusion

Cette analyse a permis de classer **586 articles PubMed** en **5 thématiques médicales** via **K-means** sur les annotations **`Disease`**. 

Les **5 clusters** identifiés (cancers localisés, carcinomas, maladies d’organes, diabète, troubles variés) reflètent des groupes pertinents. 

La **visualisation t-SNE** et le **score de silhouette (0.159)** confirment une séparation raisonnable. 

**L’analyse LDA** (**5 topics**) complète ces résultats en affinant certains thèmes (ex. Topic 1 pour carcinomas, Topic 3 pour diabète). 

-> Ces deux approches confirment la présence de groupes médicaux distincts dans le corpus, avec une prédominance de cancers et maladies métaboliques.

## Auteur
Nadia BEN YOUSSEF - 2024/2025

## Licence 📜
Ce projet est sous licence **MIT**.