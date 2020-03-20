# PyQt designer

Générer fichier ressource (pour les images par exemple)
```
pyrcc5 -o resources.py resource/resources.qrc
```

générer fichier .py depuis fichier ui :
```
pyuic5 -x test_qt.ui -o qt.py
```
