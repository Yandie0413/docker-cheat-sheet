##PASSOT Armelle Yandie 157/L1A/24-25
# Docker –

---
##  Qu’est-ce que Docker ?

Docker est une plateforme qui permet de créer, déployer et exécuter des applications dans des conteneurs.  
Un conteneur est une sorte de mini-ordinateur isolé, léger et portable.

##  Concepts clés

- **Image** : Modèle figé d’une application  
- **Conteneur** : Instance en cours d’exécution d’une image  
- **Dockerfile** : Script pour construire une image  
- **Volume** : Stockage persistant des données  
- **Docker Hub** : Registre d’images  

---

## Commandes de base

'''bash
docker --version               # Vérifie l'installation
docker pull nginx              # Télécharge une image
docker run -d -p 8080:80 nginx # Lance un conteneur
docker ps                     # Liste les conteneurs actifs
docker stop <nom/id>          # Stoppe un conteneur
docker rm <nom/id>            # Supprime un conteneur
docker rmi <image>            # Supprime une image



--
## Créer un conteneur personnalisé avec un Dockerfile

Étapes :

1. Crée un fichier Dockerfile  
2. Écris ton environnement  
3. Construis l’image avec : docker build -t mon_app .  
4. Lance avec : docker run mon_app
-----
## Images et conteneurs
```bash
docker images                 # Liste les images  
docker ps -a                  # Liste tous les conteneurs  
docker container prune        # Supprime les conteneurs arrêtés  

````
---
## Volumes
```bash
docker volume create mon_volume  
docker run -v mon_volume:/data image  
docker volume ls  
docker volume rm mon_volume  
```
----

## Dockerfile minimal
````bash
FROM python:3.10  
WORKDIR /app  
COPY . .  
RUN pip install -r requirements.txt  
CMD ["python", "app.py"]  

````
-----

## Docker Compose de base
```bash
version: "3.8"  
services:  
  web:  
    image: nginx  
    ports:  
      - "8080:80"  
  app:  
    build: .  
    volumes:  
      - .:/app
````
---
## Bonnes pratiques

- Utiliser des images légères (ex: alpine)  
- Ajouter un fichier `.dockerignore`  
- Ne pas stocker les secrets dans le Dockerfile  
- Nettoyer les ressources inutilisées avec :  
  docker system prune

---
##  Résumé rapide

- Docker = plateforme de conteneurisation  
- Image = recette  
- Conteneur = plat prêt à servir  
- Dockerfile = instructions pour créer une image  
- Compose = orchestre plusieurs conteneurs  
- Volume = stockage persistant
