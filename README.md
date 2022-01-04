# Python_2A

Ce projet a été réalisé par Benjamin Amsellem, Martin Bordes et Matthieu Bricaire dans le cadre du cours _Python pour le Data scientist_ en 2ème année d'ENSAE.
Son but est de comparer les réactions engendrées par deux films sortis au cinéma en 2021 : _Space Jam: A New Legacy_ (ou _Space Jam 2_) et _Dune_.
Cette comparaison sera réalisée au moyen d'une analyse de sentiments sur une base de données constituée par webscraping sur Twitter.

## Table des matières
* [A. Webscraping de Twitter](#A-Webscraping-de-Twitter)
* [B. Préprocessing](#b-Préprocessing)
* [C. Modélisation](#c-Modélisation)
* [D. Conslusion](#d-Conclusion)
* [E. Installation](#e-Installation)


## A. Webscraping de Twitter

Le notebook [Scraping.ipynb](Scraping.ipynb) permet de scraper des tweets en Anglais concernant les deux films sur des périodes pertinentes, choisies par les auteurs, et de les passer sous forme de dataframe pandas pour qu'ils soient aisément manipulables par la suite. 


## B. Préprocessing et visualisation
Les modèles que nous utiliserons dans la partie modélisation relèvent des méthodes supervisées. Nous aurons donc besoin d'une base de données déjà labellisées pour les entraîner. À cette fin nous aurons recours à la base [Sentiment140](http://help.sentiment140.com/) qui contient 1.6 million de Tweets en langue anglaise, portant sur des sujets divers, et déjà labellisés (`Positive` ou `Negative`).

Le notebook [preprocessing.ipynb](preprocessing.ipynb) effectue le preprocessing sur cette base Sentiment140 et sur les tweets webscrapés. Il effectue également un travail de visualisation et permet, au moyen de wordclouds, de constater visuellement l'efficacité des différentes méthodes de préprocessing utilisées.

:warning: N.B. : Nous avons décidé d'effectuer un travail de visualisation en deux parties séparées : la première intervient avant le traitement par modèles de machine learning et sert à constater "visuellement" l'efficacité du préprocessing; la deuxième intervient à la fin du projet et permet de visualiser au mieux les données obtenues après traitement.

Méthodes utilisées : 
* Count Vectorizer
* TF-IDF
* N-grams


## C. Modélisation
Nous entraînons trois modèles d'apprentissage supervisé différents dans trois notebooks différents:
* Logistic Regression : [LogisticRegression_model.ipynb](LogisticRegression_model.ipynb)
* Gaussian/Multinomial Naive Bayes : [GaussianNB_model.ipynb](GaussianNB_model.ipynb)
* Multinomial Naive Bayes Semi-Supervised : [MultinomialNB_model.ipynb](MultinomialNB_model.ipynb)

## D. Conclusion

Le notebook [Conclusion.ipynb](Conclusion.ipynb) présente nos conclusions quant à l'efficacité des trois modèles considérés dans la partie précédente. 
Puis il applique le modèle retenu comme le plus pertinent à la base de tweets webscrapés en première partie. 
Enfin il propose une visualisation des données obtenues.


## E. Installation

* Installation de l'environnement d'exécution avec Anaconda

Cloner le répertoire puis exécuter à l'intérieur du répertoire : 
```bash
conda env create
```

* Lancement de JupyterLab ou Jupyter Notebook

Exécuter à l'intérieur du répertoire : 
```bash
conda activate data-2A
jupyter lab
```
ou : 
```bash
conda activate data-2A
jupyter notebook
```
