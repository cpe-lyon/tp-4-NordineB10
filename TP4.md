##Exercice 1 :

1. Sudo apt update : mise a jour .
sudo apt ugrade : relancer les services
sudo apt full-upgrade : met à jour la distribution

2. on va rajouter un alias dans le fichier caché .bashrc  alias =’sudo apt full-upgrade’
on utilise la commande source ~/.bashrc pour redemarer le serveur bash.

3. tail -5 varlog/dpkg.log : afficher les 5 derniers paquets installé sur la machine

4. sudo apt list –installed | ls -lart : dernier paquets par apt install

5. apt list –installed | wc -l : le nombre de paquets installés par apt install
dpkg –list | wc -l : le nombre de paquets installés
Apt fait appel a dpkg donc on devrait trouver le même nombre

6. sudo apt list | wc -l : paquets disponibles sur les dépots ubuntu

7.  Glances est une application en ligne de commande qui permet d'afficher l'état des principales ressources d'un système, de sa charge et du fonctionnement des applications.
Tldr est une alternative à la commande man, permettant d’en résumer les informations . 
Hollywood simule un genre de centre de contrôle affichant des logs qui défilent, des lignes de commandes et du binaire façon Matrix.
Sudo apt update
sudo apt install glances
sudo apt install tldr
sudo apt install hollywood

8. apt search sudoku : pour jouer au sudoku.

##Exercice 2 :

dpkg -S /bin/ls : paquet ou la commande ls a été installé, c’est à dire coreutils.

Fonction
#!/bin/bash

origine-commande(){

        dpkg -S /bin/$1
}

origine-commande $1








3.

#!/bin/bash

origine-commande(){
         which -a $1 | tail -n 1 | xargs dpkg -S 2>/dev/null | cut -f1 -d:

}

origine-commande $1


##Exercice 3 :

#!/bin/bash

dpkg -l $1 2>/dev/null | grep "^ii" > /dev/null 2>&1 && echo "INSTALLE" || echo "NON INSTALLE"


##Exercice 4 :





