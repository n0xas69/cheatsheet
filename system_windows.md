# contrôle des dossiers / fichiers

```python
import os
import shutil # permet de copier / supprimer des fichiers (voir doc python)

path = "C:\\dev\\test\\test"
file = "test.py"

os.listdir(path) # Liste les dossiers et les fichier du path
os.path.join(path, file) # join le path et le nom du fichier pour faire un chemin complet
