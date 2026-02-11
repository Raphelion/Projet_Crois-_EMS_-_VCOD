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
