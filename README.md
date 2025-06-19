# cancerdetection
CNN model to classify blood cell images into 5 types (basophil, erythroblast, monocyte, myeloblast, seg_neutrophil) to assist in early detection of hematologic cancers.

Le but de ce travail est de développer un modèle d’apprentissage profond (deep learning) capable de classifier des images microscopiques de cellules sanguines, afin d’identifier des types cellulaires spécifiques – notamment ceux associés à des cancers hématologiques comme les leucémies.

# 1. Données utilisées
Le dataset provient de Kaggle : "Blood Cell Images for Cancer Detection".
Il contient des images de cellules sanguines classées manuellement en plusieurs types (ex. : monocytes, neutrophiles, lymphocytes, etc.).
Ces types incluent potentiellement des cellules cancéreuses (comme des blastes).

# 2. Prétraitement
Images redimensionnées et normalisées.
Encodage des étiquettes en catégories (one-hot encoding).
Séparation en ensembles d’entraînement, validation et test.

# 3. Modèle
Un réseau de neurones convolutif (CNN) a été construit avec Keras.
Architecture classique : Conv2D + MaxPooling + Dropout + Dense + Softmax.
Fonction de perte : categorical_crossentropy, ce qui indique une classification multi-classes.

# 4. Entraînement
Le modèle est entraîné sur un ensemble d’images de cellules connues, avec validation croisée.

Il apprend à identifier visuellement les caractéristiques morphologiques associées à chaque classe.

# 5. Prédiction et évaluation
Une fois entraîné, le modèle peut classer une nouvelle image de cellule sanguine.

On évalue les performances avec des matrices de confusion et des scores comme la précision, rappel et F1-score.

# Résultat attendu :
Le modèle permet d’identifier automatiquement des cellules anormales qui pourraient indiquer un potentiel cancer du sang. Il peut ainsi :
Accélérer le triage initial d’échantillons.
Soutenir les professionnels dans des environnements à faible ressource médicale.
Servir de base pour des outils de diagnostic assisté par IA.

# Liste des classes dans le dataset :
<li>basophil</li>
Type rare de globule blanc.
Impliqué dans les réactions allergiques et inflammatoires.

<li>erythroblast</li>
Précurseur des globules rouges.
Normalement présent dans la moelle osseuse, pas dans le sang circulant — sa présence peut être liée à des pathologies.

<li>monocyte</li>
Globule blanc qui se transforme en macrophage dans les tissus.
Participe à l’immunité innée.

<li>myeloblast</li>
Cellule souche immature de la lignée myéloïde.
Sa présence dans le sang est anormale et typique de certaines leucémies (ex : LAM).

<li>seg_neutrophil (segmented neutrophil)</li>
Neutrophile mature.
Très courant et premier défenseur contre les infections bactériennes.
