# Création de dossier projet

## TODO

créer un dossier module ou du nom que vous voulez
dans ce dossier créer un fichier `.py` et écrire une ou des fonctions à l'intérieur

à la racine du projet créer un fichier `.py` (`main`, `app`, `run` ou autre) et importer/executer une fonction ou des fonctions du fichiers se situant dans votre dossier module

> trouver l'intérêt d'un fichier `__init__.py`

## EXPLICATION

**Structure du projet**
```arduino
mon_projet/
│
├── module/
│   ├── __init__.py
│   └── fonctions.py
│
└── main.py
```

**Etape 1**
Créer un dossier `module` et un fichier `.py` (ici, fonctions.py)
Le fichier `fonctions.py` contiendra les fonctions à exécuter;

```pyhton
# module/fonctions.py

def saluer(nom):
    return f"Bonjour, {nom} !"

def additionner(a, b):
    return a + b

```

**Etape 2**
Créer le fichier principal à la racine du projet
Nommer, ici, `main.py`

```python
# main.py

from module.fonctions import saluer, additionner

# Exécution des fonctions importées
print(saluer("Alice"))
print(f"La somme de 5 et 3 est : {additionner(5, 3)}")

```

Pour exécuter le projet, lancer en ligne de commande terminal :
```bash
python main.py #main.py étant le nom du fichier principal
```
Résultat :
```yaml
Bonjour, Keyla !
La somme de 5 et 3 est : 8
```

**Etape 3**
L'utilité de `__init__.py` : ce dernier sert à indiquer à Python que le dossier dans lequel il se trouve (ici `module`) est un ***package***.
> Sans `__init__.py`, l'importation du module ou des fonctions contenus dans le dossier est impossible.
NB : Dans notre cas, le fichier `__init__.py` peut être vide.
```bash
touch module/__init__.py
``` 

## Avantages du fichier `__init__.py` :
- Il transforme un dossier **package** Python
- Peut contenir des **importations relatives** (plusieurs fichiers Python dans le package)
- Peut être utilisé pour **initialiser** certains composants du package lorqu'il est importé

## Conclusion :
Vous avez maintenant un dossier `module` avec des fonctions que tu peux importer et utiliser dans ton fichier principal.
Le fichier `__init__.py` permet à Python de considérer ton dossier comme un **package** et facilite le simportaitons entre fichiers dans votre projet.

****