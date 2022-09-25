# TP 4 - Gestion des paquets

## Exercice 1 - Commandes de base

1. La commande qui permet de mettre à jour son système est :
```
apt-get update
```


2. Pour obtenir l'alias "maj", il faut l'enregistrer dans le fichier ` .bashrc ` :

![image](https://user-images.githubusercontent.com/80455771/192150407-c687dc82-2ba2-4c56-9a8a-fcd3523d32fb.png)


3. La commande qui permet d'obtenir les 5 derniers paquets installés sur la machine est : 
```
grep installed /var/log/dpkg.log | tail -n 5 
```

![image](https://user-images.githubusercontent.com/80455771/192151385-0fa63cb0-a094-472d-8c22-ba7426cb24b0.png)


4. La commande qui permet d'obtenir les derniers paquets qui ont été installés explicitement est :
```
grep "apt install" /var/log/Apt/history.log
```

![image](https://user-images.githubusercontent.com/80455771/192151558-bf48e700-199f-4d45-a433-a24ef0f0be32.png)


5. Les commandes `dkpg` et `apt` qui permettent de compter le nombre total de paquets installés sur la machine sont :
```
dkpg -l | grep "ii" |wc -l
```

et

```
apt list -i | wc -l 
```
![image](https://user-images.githubusercontent.com/80455771/192154497-f784257f-fd7b-43ff-a62c-640593c8571d.png)

Cette petite différence s'explique par le fait que apt utilise en arrière plan dpkg quand il fait une installation à la juste différence que apt gère les dépendances contrairement à dpkg et donc compte un paquet installé en plus.


6. 68953 sont disponibles en téléchargement sur les dépôts Ubuntu, connues grâce à la commande :
```
apt list | wc -l
```


7. - Le paquet glances sert à afficher le maximum d'informations dans un minimum de places ainsi que des informations supplémentaires 
   - Le tldr permet d'avoir des pages du manuel simplifié et géré par la communauté
   - Le paquet hollywood permet de simuler une fenêtre de hacking comme au cinéma 


8. Le paquet qui permet de jouer au sudoku est le paquet `ksudoku`

