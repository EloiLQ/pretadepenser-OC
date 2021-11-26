# Application de Scoring Client pour l'entreprise Prêt à Dépenser


**Context** 
L’entreprise Prêt à Dépenser souhaite mettre en œuvre un outil de “scoring crédit” pour calculer la probabilité qu’un client rembourse ou non son crédit, puis classifie la demande en crédit accordé ou refusé. Elle souhaite donc développer un algorithme de classification en s’appuyant sur des sources de données variées (données comportementales, données provenant d'autres institutions financières, etc.).


Dans ce projet, on réalise :
- un [modèle statistique](https://nbviewer.org/github/EloiLQ/pretadepenser-OC/blob/main/Modelisation.ipynb) pour prédire les clients susceptible de ne pas rembourser un crédit (Modelisation.ipynb). La modélisation est effectué à l'aide de l'algorithme LightGBM.
- une [application web](https://share.streamlit.io/eloilq/webapp-banking/main/app.py) pour utiliser le modèle et pour interpréter ses résultats (app.py). L'application est déployée à l'aide de Streamlit.


La note méthodogique résume les points clé de la modélisation.

Les données utilisées pour la modélisation ne sont pas disponibles sur ce dépôt. Pour les télécharger sur Kaggle, taper la commande suivante :

`kaggle kernels output ekrembayar/homecredit-default-risk-step-by-step-1st-notebook -p kernel`

Ces données ont été pré-processées à partir des données brutes disponible sur le site de [Kaggle](https://www.kaggle.com/c/home-credit-default-risk). Le code de cette étape de pré-traitement est disponible [ici](https://www.kaggle.com/ekrembayar/homecredit-default-risk-step-by-step-1st-notebook/notebook).

L'algorithme LightGBM est utilisé pour réaliser le modèle statistique. Le modèle entraîné est ensuite utilisé par l'application web pour prédire le score pour chaque nouveau client. La même application permet d'interpréter les réultats d'un score pour un client donné, à partir des coefficient de Shapley. Par exemple, on peut savoir les caractéristiques clients qui ont le plus influencé la décision (score) du modèle.
