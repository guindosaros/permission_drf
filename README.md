# permission_drf
permission de django rest framework


*Ajouter le chemin de django login framework dans l'url du projet

```python
 path('api-auth/',include('rest_framework.urls'))


```

*ensuite importer permissions dans notre apiviews.py

```python 
    from rest_framework import permissions
```

Maintenant Nous allons donner une permission a notre CategoriesViewSet ajouter le code suivant a la fin de la classe Categorieview

```python
  permission_classes = (permissions.IsAuthenticatedOrReadOnly,)
```
*ici on donne la permission de lecture simple la classe de notre api tand que l'ulisateur n'est par connecter il ne pourra par effectuer d'action de crud sur la classe

## Permissions de globale par defaut
*dans le seting.py de du projet declarer 

```python

REST_FRAMEWORK = {
    # ...

    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.DjangoModelPermissionsOrAnonReadOnly'
    ],

```
