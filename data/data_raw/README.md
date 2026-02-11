-- On va ici mettre toutes les données brutes. On récupère les données, on les mets ici, dans ce dossier --
Maintenant, voici les étapes qui ont été nécessaires pour importer toutes les données.

Les données nous ont été fournies sur Moodle. Il s'agit de 6 fichiers, au format .fasta, que nous allons devoir importer sur R.
Le package utilisé sera seqinr, avec une fonction "read.alignement()". On aura également besoin de l'option "split" de la fonction "strsplit", pour séparer les données selon un caractère.
Le fichier correspondant sera placé dans le dossier R de "src".
