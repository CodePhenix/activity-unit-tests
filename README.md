# Software Testing MooC Activity

Ce dépôt contient une activité pour illustrer le travail quotidien d'un ingénieur logiciel.

## Instructions

### Pré-requis

- Python 3.x installé
- `pip` installé

### Étapes

#### 0. Forkez ce dépôt et créez une branche

Rendez vous sur https://github.com/CodePhenix/activity-unit-tests et cliquez sur
`Fork` pour créer un fork du repo c'est à dire une version à vous de ce code.

Ensuite clonez votre fork sur votre ordinateur et creez une branche

```bash
git clone <repo_url>
cd activity-unit-tests
git checkout -b activity_test
```

Activez l'environnement virtuel Python et installez les dépendances qui vous permettront de suivre la suite de
l'activité.

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

#### 1. Evaluer la couverture de tests existante

Dans `main.py` la fonction `add` a déjà été codée et dans `tests/test_main.py` des tests unitaires permettent
de la tester. Nous allons maintenant évaluer ce qu'on appelle la converture de tests c'est à dire quel pourcentage
de notre code est testé.

Ces tests permettent de tester de façon indépendante une seule fonction, ce genre de tests sont ceux qu'on nomment unitaires: ils testent un comportement simple, unitaire de notre code

```bash
pytest --cov=main
```

Vous pouvez constater que notre couverture est de 100%, c'est top !

#### 2. Ajoutez une nouvelle fonction avec des tests

Nous allons maintenant ajouter du code et voir comment ca impacte la couverture. Puis nous ajouterons des tests pour
la rétablir à 100%. Il s'agit là du quotidien de la plupart des développeurs

- Implémentez une nouvelle fonction `subtract` dans `main.py` qui permet de soustraire deux nombres
- Recalculez votre couverture de tests: à combien est-elle déscendue ? (cf remarque plus bas)
- Ajoutez des tests correspondants dans `tests/test_main.py` jusqu'à obtenir à nouveau une couverture de 100%.

Rq: vous constaterez que bien qu'on ait deux fonctions dont seulement une seule est testée, la couverture
ne descend pas à 50%. C'est normal, c'est parce que le calcul de couvertures ne compte pas en fonctions couvertes mais plutôt en ligne de code appelées pendant le lancement de tests (ce qu'il appellent des statements) ce qui change la donne.

#### 3. Commitez, poussez et créez une Pull Request

Nous allons maintenant pusher notre code et voir comment ces tests s'intégrent dans un processus
continue de qualité

```bash
git add .
git commit -m "Add tests for add and subtract functions"
git push origin feature/add-tests
```

Rendez-vous sur votre repository et allez dans l'onglet Pull request pour créer une pull request.
Une fois crée vous constaterez que les tests ont été lancés automatiquement.
