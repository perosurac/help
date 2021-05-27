# Connaitre les versions
```
$ pip --version
$ python --version
```
# Installer / désinstaller un package
```
$ pip install <package>
$ pip install requests==2.1.0
$ pip install requests~=2.2
$ pip install requests~=2.1.0
$ pip install requests>2.5.0
$ pip install "requests>2.4.0,<2.6.0"

$ pip uninstall <package>
```

Renseignements sur les packages
```
$ pip list
$ pip freeze
$ pip show <package>
$ pip show <package> <package> ...
```

# Importation d’un module en entier
La bonne façon d’importer :
```
1 import os
2 print(os.getcwd())
```
On utilise moins de code après (utile dans le shell python) ; correct mais pas une bonne pratique.
`1 from os import *`

# Importation d’une fonctionnalité d’un module
```
1 from os import getcwd
2 print(getcwd()) // on n’utilise plus le préfixe
```

# Importation d’un paquet avec alias
Utile pour la lisibilité du code
```
1 import numpy as np
2 print(np.ceil(1.234))
```

# Création d’un environnement + activation + désactivation
Lors de la création d’un environnement, il n’y a aucun paquet d’installer !!
Nommer tous les environnement “env” est une bonne pratique (cfr .gitignore, ...).
```
$ python -m venv env

$ source env/bin/activate // linux
$ env\Scripts\activate.bat // windows

(env) $ deactivate
```

# Création + utilisation de requirements.txt
Le nom “requirements.txt” est un standard dans le dev Python.
Dans l’environnement de base activé, faire :
`$ pip freeze > requirements.txt`

Dans le nouvel environnement activé, faire :
`$ pip install -r requirements.txt`

# Suppression d’un environnement 
Il suffit de supprimer le répertoire !

# Problème d’encodage pour le français
Mettre la ligne suivante en haut du script :
`1 # -*- coding: utf8 -*-`
