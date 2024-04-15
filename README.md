# Projet Bibliometrics avec MongoDB, Scrapy et Dash

Ce projet contient une configuration Docker-compose pour exécuter une stack comprenant MongoDB, un script de scraping avec Scrapy et un tableau de bord interactif avec Dash.

L'objectif de ce projet est d'extraire des données à partir d'un site web et de les afficher de manière interactive sur un tableau de bord.

# Blocs de données affichées sur le tableau de bord
- Nombre de livres dans chaque catégorie
Affiche le nombre total de livres dans chaque catégorie.

- Note moyenne pour chaque catégorie
Affiche la note moyenne attribuée aux livres dans chaque catégorie.

- Liste des livres avec plus de 10 exemplaires disponibles
Affiche une liste des livres pour lesquels plus de 10 exemplaires sont disponibles, avec leur titre, leur catégorie, leur prix et leur note.

- Liste des livres avec une note de 5 étoiles
Affiche une liste des livres qui ont reçu une note de 5 étoiles, avec leur titre, leur catégorie et leur note.

Ces blocs de données fournissent des informations clés sur les livres disponibles et leurs évaluations, facilitant ainsi leur analyse.

## Configuration des services

### MongoDB

Le service MongoDB est utilisé comme base de données pour stocker les données extraites par le script de scraping.

- Port exposé : `27017`
- Volume : `mongodb_data:/data/db`

### Scrapping

Le service de scraping utilise Scrapy pour extraire des données à partir du site web "https://books.toscrape.com/" et les stocker dans MongoDB.

### Dash

Le service Dash héberge un tableau de bord interactif permettant de visualiser et d'analyser les données extraites.

- Port exposé : `8050`

## Utilisation

1. Assurez-vous que Docker et Docker-compose sont installés sur votre système.
2. Clonez ce dépôt sur votre machine locale.
3. Naviguez jusqu'au répertoire du projet.
4. Exécutez la commande suivante pour démarrer les services à la racine du projet:

   ```bash
   docker compose up --build
