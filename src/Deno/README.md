-- Scripts Deno --
On va détailler comment le code a été créé. 
Le code Deno est un code d'automatisation. Pour chaque pays, pour chaque période (Q1, Q2, Q3, Q4) de chaque année, on récupère les données du serveur correspondantes, en faisant une requête.

 -- SCRIPT de création du code d'automatisation dans le terminal Linux --
Il a fallu déjà installer deno avec la commande : "curl -fsSL https://deno.land/install.sh | sh", et la commande : "npm install -g deno", puis "deno init my_project".

Puis, dans le terminal : 
>> mkdir projet_croise_deno
>> cd projet_croise_deno
>> nano fetch_data.ts

On écrit le code dans l'éditeur nano.

>> deno run --allow-net --allow-write fetch_data.ts
On autorise la lecture des fichiers, puis on lance l'automatisation.
Nous avons lancé l'automatisation sur deux oridnateurs en même temps, avec deux catégories chacun, afin d'aller deux fois plus vite.

-- Explication du code --
On commence par définir une variable BASE_URL qui contient "http://172.22.215.130:8080/archived", puis une variable DATASETS qui contient la liste ["sequences", "cancer", "biomedical", "social"].
On a aussi COUNTRIES qui contient ["PT", "CH", "DE", "GB", ...], START_YEAR et END_YEAR qui contiennent 1980 et 2025, ce sont les pays et périodes à couvrir.
Enfin, on a une variable "DELAY_MS" qui est égal à 500, une valeur fixée arbitrairement, et qui va fixer la durée entre chaque requête.

On définit ensuite les utilitaires. sleep() -> attends un certain nombre de millisecondes. Le script fait une pause entre chaque téléchargement.
generateTrimstre() -> La fonction généère tous les trimestres (Q1, Q2, Q3, Q4) qui sont les trimestres des années.
Ainsi, la variable TRIMESTERS = generateTrimesters(START_YEAR, END_YEAR) génère tous les noms des fichiers que nous allons récupérer.

Pour chaque Dataset : 

Pour chaque Pays : 
On créé le dossier dans le dossier courant. 

Pour chaque Trimestre : 
On télécharge le fichier voulu via une requête : on additionne l'URL de base et les noms des boucles en cours : datasets, pays, trimestre.
Si le fichier existe déjà, on saute au suivant, et on ne le télécharge pas.
Si le fichier n'existe pas encore, alors si la requête ne renvoie pas une erreur, on récupère les données, on les inscrit dans un fichier texte, et on les place dans le dossier en cours.
On attend le délai indiqué, pour éviter toute erreur lié à la rapidité entre deux requêtes.
On affiche "Téléchargement terminé".









