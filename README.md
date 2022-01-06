# Python_2A

Ce projet a été réalisé par Benjamin Amsellem, Martin Bordes et Matthieu Bricaire dans le cadre du cours _Python pour le Data scientist_ en 2ème année d'ENSAE.
Son but est de comparer les réactions engendrées par deux films sortis au cinéma en 2021 : _Space Jam: A New Legacy_ (ou _Space Jam 2_) et _Dune_.
Cette comparaison sera réalisée au moyen d'une analyse de sentiments sur une base de données constituée par webscraping sur Twitter.

## Table des matières
* [A. Webscraping de Twitter](#A-Webscraping-de-Twitter)
* [B. Préprocessing](#b-Préprocessing)
* [C. Modélisation](#c-Modélisation)
* [D. Conslusion](#d-Conclusion)


## A. Webscraping de Twitter

Le notebook [Scraping.ipynb](Scraping.ipynb) permet de scraper des tweets en Anglais concernant les deux films sur des périodes pertinentes, choisies par les auteurs, et de les passer sous forme de dataframe pandas pour qu'ils soient aisément manipulables par la suite. 


## B. Préprocessing et visualisation

Les modèles que nous utiliserons dans la partie modélisation relèvent des méthodes supervisées. Nous aurons donc besoin d'une base de données déjà labellisées pour les entraîner. À cette fin nous aurons recours à la base [Sentiment140](http://help.sentiment140.com/) qui contient 1.6 million de Tweets en langue anglaise, portant sur des sujets divers, et déjà labellisés (`Positive` ou `Negative`).

:warning: N.B. : Nous aurions souhaité enregistrer tous les dataframes préprocessés au format csv. Cela nous a été possible pour la base des données scrapées sur Twitter et ses huit versions préprocessées de manières différentes. Malheureusement, les huit versions préprocessées de la base d'entraînement Sentiment140 n'ont pas pu être enregistrées en csv car elles excédaient la capacité maximale uploadable sur Github (200MB contre une limite maximale de 100MB). Les huit versions préprocessées de la basee Sentiment140 seront donc enregistrés en pickle avec l'extension bz2.

Le notebook [Preprocessing.ipynb](Preprocessing.ipynb) effectue le preprocessing sur cette base Sentiment140 et sur les tweets webscrapés. Il effectue également un travail de visualisation et permet, au moyen de wordclouds, de constater visuellement l'efficacité des différentes méthodes de préprocessing utilisées.

:warning: N.B. : Nous avons décidé d'effectuer un travail de visualisation en deux parties séparées : la première intervient avant le traitement par modèles de machine learning et sert à constater "visuellement" l'efficacité du préprocessing; la deuxième intervient à la fin du projet et permet de visualiser au mieux les données obtenues après traitement.


## C. Modélisation

Nous entraînons trois modèles d'apprentissage supervisé différents dans trois notebooks différents:
1) Gaussian/Multinomial Naive Bayes : [GaussianNB_model.ipynb](GaussianNB_model.ipynb)
2) Multinomial Naive Bayes Semi-Supervised : [MultinomialNB_model.ipynb](MultinomialNB_model.ipynb)
3) Logistic Regression : [LogisticRegression_model.ipynb](LogisticRegression_model.ipynb)

Méthodes de feature extraction utilisées : 
* Count Vectorizer
* TF-IDF
* N-grams


## D. Conclusion

Le modèle le plus efficace parmi les trois testés est le modèle de régression logistique, utilisé avec la méthode de feature extraction "TfidfVecotrizer" avec Ngram.
Le notebook [Conclusion.ipynb](Conclusion.ipynb) applique ce modèle entraîné sur la base Sentiment140 à la base de tweets webscrapés en première partie. 
Puis il propose une visualisation montrant l'évolution des sentiments sur les deux films dans le temps.

Merci de votre attention et bonne lecture !
