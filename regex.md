Construire et vérifier regex : https://pythex.org/

**\d** = un chiffre  
**\D** = pas de chiffre  
**\w** = un caractère alpanumérique [0-9a-zA-Z_]  
**\W** = pas de caractère alphanumérique  
**\s** = un espace blanc (espace, tab ...)  
**\S** = pas d'espace  
**()** = Créer un groupe  
**|** = OU  
**^** = Commence par  
**$** = Termine par  
**^\d** = Commence par un chiffre  
**\d$** = Termine par un chiffre

**\d+** = au moins un chiffre ou plus  
**\w+** = au moins une lettre au plus (le + signifie "au moins un")

**\d{2}** = 2 chiffres  
**\d{2,8}** = entre 2 et 8 chiffres  

.* = tout ce qui viens après  
**Prénom:(.*)** = tout ce qui viens après prénom:  
**'(.*)'** = Permet de récupérer ce qui a entre les '  
**<(.*)>** = Récupère ce qui a entre les chevrons, le met dans un groupe

![](https://github.com/n0xas69/cheatsheet/blob/master/regex.PNG)


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


reg = re.compile(r"(Je m'appelle)?Romain dupont") # Le ()? permet de dire que le groupe est optionnel
gr = reg.search("Je m'appelle Romain dupont")
print(gr.group())

gr2 = reg.search("Romain dupont")
print(gr2.group())

rege = re.compile(r"romain|cindy") # le | veux dire "ou", dans l'exemple, cindy ou romain
gr = rege.findall("bonjour romain et cindy") # le findall renvoi une liste de tout ce qui match
print(gr)
```


# Exemples
```python
regex = re.compile(r"\d+\s\w+")
print(regex.findall("bonjour, voici 11 pommes et 1200 poires. Ainsi que 8 carottes"))
```
**\d+** = trouve un chiffres ou plus  
**\s** = suivit d'un espace,  
**\w+** = suivit d'un mot (le \w cherche une lettre, le + permet de dire "au moins une lettre")

résultat du print : ```['11 pommes', '1200 poires', '8 carottes']```

```python
text = "client : s100, id : '454a5-dsd45-d7s8d-jdkls-fd457'"

regex = re.compile(r"(s\d{3})|(\w{5}-\w{5}-\w{5}-\w{5}-\w{5})") # cherche le client et l'id
gr = regex.findall(text) # retourne une liste de tuples
client = gr[0][0] # accède au tuple d'indice 0, et le premier indice du tuple
id_client = gr[1][1]

if client == "s100":
        print(f"Voici votre ID : {id_client}")
else:
        print("Vous n'êtes pas le bon client")
```

décryptons la regex :  
**s\d{3}** = un s suivit de 3 chiffres  
**|** = OU  
**\w{5}-** = chaine de 5 caractère suivit d'un -

Le résultat du findall est : ```[('s100', ''), ('', '454a5-dsd45-d7s8d-jdkls-fd457')]```

autre moyen plus simple de trouver l'id :

```python
import re

reg = re.search(r"'(.*)'", "ceci est un test, id : '454a5-dsd45-d7s8d-jdkls-fd457'")
print(reg.group(1))
```

**'(.*)'** = Permet de récupérer ce qui a entre les ' dans un groupe.

Remplacer un élément par un autre :
```python
import re

text = "salut romain"

reg = re.compile(r"r\w+")
text2 = reg.sub("cindy", text)

print(text2)
```
```salut cindy```
