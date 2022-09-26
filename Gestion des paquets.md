# TP 4 - Gestion des paquets

## Exercice 1 - Commandes de base

### 1. La commande qui permet de mettre à jour son système est :
```
apt-get update && apt-get upgrade
```


### 2. Pour obtenir l'alias "maj", il faut l'enregistrer dans le fichier ` .bashrc ` :

![image](https://user-images.githubusercontent.com/80455771/192150407-c687dc82-2ba2-4c56-9a8a-fcd3523d32fb.png)


### 3. La commande qui permet d'obtenir les 5 derniers paquets installés sur la machine est : 
```
grep installed /var/log/dpkg.log | tail -n 5 
```

![image](https://user-images.githubusercontent.com/80455771/192151385-0fa63cb0-a094-472d-8c22-ba7426cb24b0.png)


### 4. La commande qui permet d'obtenir les derniers paquets qui ont été installés explicitement est :
```
grep "apt install" /var/log/Apt/history.log
```

![image](https://user-images.githubusercontent.com/80455771/192151558-bf48e700-199f-4d45-a433-a24ef0f0be32.png)


### 5. Les commandes `dkpg` et `apt` qui permettent de compter le nombre total de paquets installés sur la machine sont :
```
dkpg -l | grep "ii" |wc -l
```

et

```
apt list -i | wc -l 
```
![image](https://user-images.githubusercontent.com/80455771/192154497-f784257f-fd7b-43ff-a62c-640593c8571d.png)

Cette petite différence s'explique par le fait que apt utilise en arrière plan dpkg quand il fait une installation à la juste différence que apt gère les dépendances contrairement à dpkg et donc compte un paquet installé en plus.


### 6. 68953 sont disponibles en téléchargement sur les dépôts Ubuntu, connues grâce à la commande :
```
apt list | wc -l
```


### 7. - Le paquet glances sert à afficher le maximum d'informations dans un minimum de places ainsi que des informations supplémentaires :
   - Le tldr permet d'avoir des pages du manuel simplifié et géré par la communauté
   - Le paquet hollywood permet de simuler une fenêtre de hacking comme au cinéma 


### 8. Le paquet qui permet de jouer au sudoku est le paquet : `ksudoku`


## Exercice 2 

La commande ls est installé à partir des paquets coreutils et klibc-utils, on peut savoir ça grâce à la commande :
```
dpkg -S ls | grep "/ls$"
```
Le script :
```console
#!/bin/bash

echo $(dpkg -S $1 |grep "/$1$"
```

## Exercice 3 

Commande qui affiche “INSTALLÉ” ou “NON INSTALLÉ” selon le nom et le statut du package
spécifié dans cette commande :
```
dpkg -l "nom_du_package" 2>/dev/null | grep "ii" && echo "Installé || echo "Non installé"
```
Exemple avec un paquet aléatoire et le paquet Hollywood :


![image](https://user-images.githubusercontent.com/80455771/192210392-83789ca4-f8a7-4e6c-9c48-e348d853b87a.png)

## Exercice 4 
On peut voir les programmes livrés avec la commande coreutils grâce à la commande :
```
dpkg -L coreutils
```
Le programme "[" est l'équivalent de la commande 'test'. C'est ce qu'on utilise dans les scripts pour les conditions. 

## Exercice 5 

- Emacs est un éditeur de texte 
- Lynx est un navigateur web en mode texte 

## Exercice 6

Un nouveau fichier a été installé et il s'appelle :
```
linuxuprising-ubuntu-java-jammy.list
```

![image](https://user-images.githubusercontent.com/80455771/192216733-a38af22a-c9cc-418a-a6a3-84ed7ad9a87e.png)

## Exercice 7 

- Installation pour clôner le dépôt dit :

![image](https://user-images.githubusercontent.com/80455771/192221042-dcdd7e1c-b6a1-46a2-8f2a-482513517101.png)

- Les différentes installation grâce au fichier 'README.md' : 

![image](https://user-images.githubusercontent.com/80455771/192221465-60241203-2ff4-47ed-b9cb-390a791cbf01.png)

![image](https://user-images.githubusercontent.com/80455771/192221990-7aa2fd97-f05d-49cc-aecc-f8d69cf5d659.png)


![image](https://user-images.githubusercontent.com/80455771/192221532-821a4273-ddca-4eac-ab7f-9792eb1c7527.png)

![image](https://user-images.githubusercontent.com/80455771/192221719-2aa733ef-f8d7-4edb-8ea7-8b2b621c0a67.png)

![image](https://user-images.githubusercontent.com/80455771/192221799-f04c0be5-9d87-4cd2-b81a-92d76ca5f526.png)

Et on lance le programme `cbonsai`

![image](https://user-images.githubusercontent.com/80455771/192222055-2a87e5a9-de87-4317-88f6-4d802c5bc411.png)

## Exercice 8 
Les différentes arbrorescence :
 - Pour le chemin `origine-commande/debian/control` :
 
![image](https://user-images.githubusercontent.com/80455771/192236881-2cb25c09-272b-4eaf-9c57-5ffb6f0b22a0.png)

 - Pour le chemin `origine-commande/usr/local/bin` :
 
 ![image](https://user-images.githubusercontent.com/80455771/192237452-819dfe7b-2b64-49e6-ae41-6042c49b4f59.png)

Voici le contenu du fichier `control` :

![image](https://user-images.githubusercontent.com/80455771/192236597-353babda-e3c7-4e4a-a176-3bcef12fd95b.png)









