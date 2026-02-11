-- Ici, on va mettre les données qui ont été modifiées, et qui sont réutilisables par à peu près n'importe qui ou n'importe quoi --
On va décrire les étapes que l'on a fait, pour réussir à rendre ces données lisibles.

Nous avons un problème : les données brutes sont des données temporelles, et l'intervalle entre chaque fichier texte est de 3 mois. Si on supprime les doublons et/ou les fichiers vides, cela va casser la structure des fichiers, et ainsi la temporalité. Nous pensons qu'il est préférable de gader les fichiers vides, pour avoir une bien meilleure visualisation.
Ceci dit, les noms peuvent être utilisés afin de savoir quel fichier est dans quelle année, et est dans quel semestre...

