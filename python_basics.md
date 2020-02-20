# String


```python
maVariable1 = "kek"
maVariable2 = "loule"

print(f"je peux mettre ma variable1 {maVariable1} et une autre {maVariable2}")
print(r"je peux faire des caractère bizarre genre \n pour qu'il ne le considère pas comme une retour chariot.")
print("Je peux également utiliser le format pour afficher ma variable {} et {}".format(maVariable1, maVariable2))
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


dico = {"prénom" : "romain", "nom" : "dupont", "age" : 24}
print(dico.keys()) # affiche les clés
print(dico.values()) # affiche les valeurs
print(dico.items()) # affiche les pairs

```
