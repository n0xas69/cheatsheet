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
```

## recherche de fichier par extension
```python
import os
import shutil as sh

def search_ext(src, ext):
        files = os.listdir(src)
        for f in files:
                path = os.path.join(src, f)
                file_ext = path.split(".")
                try:
                        if os.path.isfile(path) is True:
                                if file_ext[1] == ext:
                                        print(path)
                        
                        else:
                                search_ext(path, ext)
                except IndexError:
                        pass
                except PermissionError:
                        print(f"Accès refusé {src}")


search_ext(r"C:\Program Files", "txt")
```
