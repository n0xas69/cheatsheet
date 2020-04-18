# String


```python
maVariable1 = "kek"
maVariable2 = "loule"

print(f"je peux mettre ma variable1 {maVariable1} et une autre {maVariable2}")
print(r"je peux faire des caractère bizarre genre \n pour qu'il ne le considère pas comme une retour chariot.")
print("Je peux également utiliser le format pour afficher ma variable {} et {}".format(maVariable1, maVariable2))
print(f"si je veux mettre des {{salut}} et des variable {maVariable1} je peux")
```

    je peux mettre ma variable1 kek et une autre loule
    je peux faire des caractère bizarre genre \n pour qu'il ne le considère pas comme une retour chariot.
    Je peux également utiliser le format pour afficher ma variable kek et loule
    

# Boucle


```python
texte = "salut les kebab"
for lettre in texte:
    print(lettre)

i = 1
while i < 10:
    print("kek")
    i = i+1
```

    s
    a
    l
    u
    t
     
    l
    e
    s
     
    k
    e
    b
    a
    b
    kek
    kek
    kek
    kek
    kek
    kek
    kek
    kek
    kek
    

# Liste / tuple / dictionnaire
```python
liste = []
tuple = ()
dico = {}

# liste de dictionnaire
liste = [
        {"prénom" : "romain", "nom" : "dupont"},
        {"prénom" : "cindy", "nom" : "binase"},
        {"prénom" : "chaton", "nom" : "miaou"}
        ]
        
liste.append("test") # ajoute un élément à la fin de la liste
liste.pop(1) # supprime un élément de la liste par son index
liste.insert(1, "saluut") # insert un élément à l'index spécifié en paramètre
print(liste.count("saluut")) # compte le nombre d'éléments spécifié en paramètre        
liste.sort(key= lambda x: x["nom"]) # Trier une liste par la valeur d'un dictionnaire
value_dico = liste[0].values() # accède au valeurs du dictionnaire situé à l'index 0 de la liste, renvoi un type dict_values
maListe = [1, 2, 3, 4, 5]
len(maListe) # longueur de la liste
liste.remove(2) # Supprime un élément par sa valeur
```
### Compréhension de liste
[action à faire | pour ces élément | si tel condition]  
[    n * 2      | for n in maListe |     if n > 3    ]
```python
maListe2 = [n * 2 for n in maListe] # multiplie chaque élément de la liste par deux
maListe3 = [n * 2 for n in maListe if n > 3] # multiplie les éléments supérieur à 3
```
### Dictionnaires
```python
dico = {"prénom" : "romain", "nom" : "dupont", "age" : 24}
print(dico.keys()) # affiche les clés
print(dico.values()) # affiche les valeurs
print(dico.items()) # affiche les pairs
dico.get(key) # récupère la valeur de la clé spécifié

listDico = [{"classe" : "mage", "lvl" : "45"}, {"classe" : "guerrier", "lvl" : "42"}, {"classe" : "guerrier", "lvl" : "50"}]

for dico in listDico:
    if dico.get("classe") == "guerrier":
        print("il y a un guerrier niveau " + dico.get("lvl"))

```
### Générateur / expression
```python
maListe = [{"key1": "value1", "key2": "value2"}, {"key1": "value3", "key2": "value4"}, {"key1": "value5", "key2": "value2"}]

# On fait la somme des dico qui on la value2 en clé2 pour chaque dico dans la liste
test = sum(dic.get("key2") == "value2" for dic in maListe)
print(test)
```


# map() / filter() / zip() / reduce()
```python
from functools import reduce

#1 Capitalize all of the pet names and print the list
my_pets = ['sisi', 'bibi', 'titi', 'carla']

def capitalize(item):
    return item.upper()

print(list(map(capitalize, my_pets)))




#2 Zip the 2 lists into a list of tuples, but sort the numbers from lowest to highest.
my_strings = ['a', 'b', 'c', 'd', 'e']
my_numbers = [5,4,3,2,1]


new_numbers = sorted(my_numbers)
print(list(zip(my_strings, new_numbers)))



#3 Filter the scores that pass over 50%

scores = [73, 20, 65, 19, 76, 100, 88]

def filtre(item):
  return item > 50

print(list(filter(filtre, scores)))

#4 Combine all of the numbers that are in a list on this file using reduce (my_numbers and scores). What is the total?
```
