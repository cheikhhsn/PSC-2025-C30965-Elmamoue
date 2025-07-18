
# Résumé des chapitres 4 et 5 – *Scientific Computing with Python*

## Chapitre 4 – Algèbre linéaire : les tableaux (arrays)

Ce chapitre introduit l’utilisation des **tableaux (ou "arrays")**, qui sont des structures fondamentales pour le calcul scientifique avec Python. L’accent est mis sur la bibliothèque **NumPy**, indispensable pour manipuler des vecteurs et des matrices de manière efficace.

On commence par la création d’un tableau simple à une dimension :

```python
import numpy as np
a = np.array([1, 2, 3])
```

On peut aussi créer des **matrices (tableaux à deux dimensions)** en utilisant des listes imbriquées :

```python
M = np.array([[1, 2], [3, 4]])
```

L’accès aux éléments se fait par indexation :

```python
M[0, 1]  # renvoie 2
M[1, :]  # renvoie la deuxième ligne : [3, 4]
```

Le chapitre couvre ensuite les **opérations d’algèbre linéaire** :
- Les **opérations élémentaires** (`+`, `-`, `*`, `/`) s’appliquent élément par élément.
- Le **produit scalaire** se fait avec `np.dot()` ou l’opérateur `@`.
- On apprend à **transposer** (`.T`), **redimensionner** (`reshape`), ou **concaténer** des tableaux.

Une notion importante introduite est le **broadcasting** : une méthode automatique permettant de faire des opérations entre tableaux de tailles différentes, sans boucle explicite.

Ensuite, le module `scipy.linalg` est présenté pour effectuer des opérations plus avancées comme :
- Résolution de systèmes linéaires
- Inversion de matrices
- Calcul de déterminants
- Décompositions LU et SVD

Exemple :
```python
from scipy.linalg import lu, svd
```

Le chapitre se termine par des cas pratiques : résolution d’équations linéaires, ajustement de données par moindres carrés, etc.

## Chapitre 5 – Concepts avancés sur les tableaux

Ce chapitre approfondit l’utilisation des tableaux NumPy avec des concepts plus avancés liés aux **performances** et à l’**efficacité mémoire**.

La première notion importante est la distinction entre **copie** et **vue (view)** :
- Une **copie** crée un nouveau tableau indépendant.
- Une **vue** permet d’accéder aux mêmes données sans en faire une duplication.

Ensuite, les **tableaux booléens** permettent de **filtrer des éléments** selon une condition :

```python
a = np.array([1, 2, 3, 4])
mask = a > 2
a[mask]  # renvoie [3, 4]
```

D’autres méthodes d’indexation avancée sont abordées :
- `np.where()` pour récupérer les indices ou appliquer des remplacements conditionnels
- L’indexation par tableaux d’indices

Le chapitre insiste sur la **vectorisation**, qui remplace les boucles explicites :

```python
# Mauvaise pratique
for i in range(len(a)):
    b[i] = a[i] * 2

# Bonne pratique
b = a * 2
```

Le **broadcasting** est détaillé :

```python
a = np.array([1, 2, 3])
b = 10
a + b  # [11, 12, 13]
```

Enfin, le chapitre aborde les **matrices creuses (sparse matrices)**, utiles pour les grands jeux de données peu denses :

```python
from scipy.sparse import csr_matrix
```

Formats (CSR, CSC, LIL) sont présentés selon les besoins (performance, modification, accès).

