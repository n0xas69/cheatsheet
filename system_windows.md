# contrôle des dossiers / fichiers

```python
import os
import shutil # permet de copier / supprimer des fichiers (voir doc python)

path = "C:\\dev\\test\\test"
file_src = "hello.txt"
file_dst = "world.txt"

os.listdir(path) # Liste les dossiers et les fichier du path
os.path.join(path, file) # join le path et le nom du fichier pour faire un chemin complet
sh.copyfile(os.path.join(path, file_src), os.path.join(path, file_dst)) # copie le contenu du fichier src dans un fichier dst
