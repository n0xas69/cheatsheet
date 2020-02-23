```python
import re

regphone = re.compile(r"\d{2} \d{2} \d{2} \d{2} \d{2}")

text = "Bonjour, mon numéro est le 06 68 41 46 88"
regphone.search(text) # Cherche la regex dans la string en paramètre
print(regphone.search(text).group()) # la méthode group() affiche la chaine trouvé

#################################################################

regphone = re.compile(r"(\d{2} \d{2}) \d{2} \d{2} \d{2}") # la parenthèse permet de séparer en groupe
print(regphone.search(text).groups()) # la méthode groups affiche tous les groupe
print(regphone.search(text).group(1)) # On passe le numéro du group en paramètre pour afficher celui qu'on veux


reg = re.compile(r"(Je m'appelle)?Romain dusson") # Le ()? permet de dire que le groupe est optionnel
gr = reg.search("Je m'appelle Romain dusson")
print(gr.group())

gr2 = reg.search("Romain dusson")
print(gr2.group())

rege = re.compile(r"romain|cindy") # le | veux dire "ou", dans l'exemple, cindy ou romain
gr = rege.findall("bonjour romain et cindy") # le findall renvoi une liste de tout ce qui match
print(gr)
```

Vérifier regex : https://pythex.org/

# Exemples
```python
regex = re.compile(r"\d+\s\w+")
print(regex.findall("bonjour, voici 11 pommes et 1200 poires. Ainsi que 8 carottes"))
```
\d+ = trouve un chiffres ou plus  
\s = suivit d'un espace,  
\w+ = suivit d'un mot (le \w cherche une lettre, le + permet de dire "au moins une lettre")

résultat du print : ['11 pommes', '1200 poires', '8 carottes']

