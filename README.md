# Pipeline CI/CD avec Jenkins, GitHub, Docker et ngrok

## Aperçu du TP
Ce TP met en place un pipeline CI/CD pour un projet Spring Boot :
* Récupération du code depuis GitHub
* Build Maven et tests
* Création d’une image Docker
* Lancement du conteneur
* Déclenchement automatique du pipeline à chaque push via GitHub Webhook et ngrok

## Objectifs pédagogiques
* Comprendre la différence entre CI (Intégration Continue) et CD (Livraison/Déploiement Continu).
* Installer et configurer Jenkins sur une machine locale.
* Configurer Maven dans Jenkins.
* Créer un Pipeline Jenkins pour un projet Spring Boot + Docker.
* Exposer Jenkins local à Internet avec ngrok.
* Mettre en place un webhook GitHub déclenchant automatiquement le pipeline.

## Prérequis
* Windows 10/11
* Java JDK (17 ou 21) installé
* Git installé
* Docker Desktop installé et démarré
* Compte GitHub
* Accès Internet

## PARTIE A – Installation et première connexion à Jenkins
### Tâche 1 : Installation de Jenkins
<img width="382" height="298" alt="Capture d&#39;écran 2025-12-14 194432" src="https://github.com/user-attachments/assets/fd58ed60-d144-4cc7-8b05-4b95aed9370c" />
<img width="383" height="301" alt="Capture d&#39;écran 2025-12-14 194505" src="https://github.com/user-attachments/assets/e1b381c0-26cd-40f6-86ff-e21990f28540" />
<img width="960" height="502" alt="Capture d&#39;écran 2025-12-14 195013" src="https://github.com/user-attachments/assets/daee4fc5-58f3-4f13-bd48-b88062b71e9e" />
<img width="960" height="474" alt="Capture d&#39;écran 2025-12-14 195100" src="https://github.com/user-attachments/assets/16df7de7-6926-4d74-a5db-264994723eeb" />
<img width="600" height="420" alt="Capture d&#39;écran 2025-12-14 195743" src="https://github.com/user-attachments/assets/0ea61a8c-837a-4b32-83bf-c4bb4ca72a01" />
<img width="960" height="502" alt="Capture d&#39;écran 2025-12-14 202413" src="https://github.com/user-attachments/assets/e3bfd1be-9a0c-41be-a296-9cfdde461c37" />
<img width="960" height="507" alt="Capture d&#39;écran 2025-12-14 204318" src="https://github.com/user-attachments/assets/977917fb-8ce0-4ad9-85fe-d43e829d6d64" />

### Tâche 2 : Accès au Dashboard Jenkins
<img width="960" height="496" alt="Capture d&#39;écran 2025-12-14 204357" src="https://github.com/user-attachments/assets/aeab6b82-147b-4199-b631-f2edd1378636" />

## PARTIE B – Configuration de Maven dans Jenkins
### Tâche 3 : Ouvrir la configuration des outils
<img width="960" height="504" alt="Capture d&#39;écran 2025-12-14 204526" src="https://github.com/user-attachments/assets/55768b4d-b36b-4edd-8bbf-fd53cd3a8e87" />

### Tâche 4 : Ajouter Maven
<img width="960" height="476" alt="Capture d&#39;écran 2025-12-14 204900" src="https://github.com/user-attachments/assets/ee160624-07f5-4e5b-b04d-b9a65b50bf4f" />

## PARTIE C – Préparation du projet Spring Boot
### Tâche 5 : Récupérer et tester le projet localement
<img width="860" height="460" alt="Capture d&#39;écran 2025-12-14 205241" src="https://github.com/user-attachments/assets/e784e855-e574-4f32-afc5-6636c62b26f1" />
<img width="960" height="504" alt="Capture d&#39;écran 2025-12-14 211123" src="https://github.com/user-attachments/assets/0e4f4105-b768-4046-9148-4a5319f6e95a" />
<img width="960" height="503" alt="Capture d&#39;écran 2025-12-14 211321" src="https://github.com/user-attachments/assets/b3a8a04c-68bc-478d-8418-2daf182f580a" />

### Tâche 6 : Publier le projet dans un dépôt GitHub personnel
<img width="954" height="440" alt="image" src="https://github.com/user-attachments/assets/71bfb1b2-ee8d-455f-9376-b5f53bb92932" />

## PARTIE D – Création d’un Pipeline Jenkins pour CI/CD
### Tâche 7 : Créer un nouveau job Pipeline
<img width="960" height="503" alt="Capture d&#39;écran 2025-12-14 212454" src="https://github.com/user-attachments/assets/450bcbaa-6f65-4947-8c3f-cabd52409cbb" />

### Tâche 8 : Configurer le job Pipeline
<img width="954" height="503" alt="Capture d&#39;écran 2025-12-14 213604" src="https://github.com/user-attachments/assets/4b4b64c5-9fc6-4492-86f0-e1f670f91f0f" />
<img width="693" height="444" alt="Capture d&#39;écran 2025-12-14 213718" src="https://github.com/user-attachments/assets/22c0daa4-fed4-413b-beca-61fd0c1d3ef1" />

## PARTIE E – Lancer le pipeline et lire le résultat
### Tâche 9 : Lancer un build manuel
<img width="960" height="502" alt="Capture d&#39;écran 2025-12-14 220946" src="https://github.com/user-attachments/assets/4dbc02bc-a9ee-408d-845c-5575d4542998" />
<img width="960" height="503" alt="Capture d&#39;écran 2025-12-14 221129" src="https://github.com/user-attachments/assets/f6bace4e-3caf-41fd-9b25-ac53c436252a" />
<img width="960" height="505" alt="Capture d&#39;écran 2025-12-14 221325" src="https://github.com/user-attachments/assets/fb814d41-f977-479a-8a1f-c0e5de5fb2fe" />
<img width="960" height="505" alt="Capture d&#39;écran 2025-12-14 221338" src="https://github.com/user-attachments/assets/c3048542-da3c-4fb4-9169-6dce8bde5df1" />

## PARTIE F – ngrok + Webhook GitHub : déclenchement automatique
### Problème
* Jenkins fonctionne en local (http://localhost:8080).
* GitHub ne peut pas appeler directement cette URL.
--> Solution : ngrok crée un tunnel sécurisé et expose Jenkins via une URL publique.

### Étape 1 – Installation et configuration de ngrok
#### Tâche 10 : Télécharger ngrok
<img width="960" height="503" alt="image" src="https://github.com/user-attachments/assets/443b4b41-72b2-4909-b75c-1821e212ee10" />

#### Tâche 11 : Ajouter ngrok dans le PATH (optionnel mais pratique)
<img width="444" height="486" alt="image" src="https://github.com/user-attachments/assets/0b47db35-52ed-4931-87a3-fafa5f6d6a10" />

#### Tâche 12 : Récupérer et configurer l’authtoken
<img width="960" height="472" alt="image" src="https://github.com/user-attachments/assets/db7368a4-98e2-4aa9-90f1-dc50baeef32b" />

#### Tâche 13 : Créer le tunnel vers Jenkins
<img width="859" height="460" alt="Capture d&#39;écran 2025-12-14 223612" src="https://github.com/user-attachments/assets/69ccb6c0-ee84-40f7-b978-0c5814b76eb7" />
<img width="960" height="476" alt="Capture d&#39;écran 2025-12-14 223709" src="https://github.com/user-attachments/assets/c23d839f-abc2-4434-a9ba-0a808eecb90d" />
<img width="960" height="473" alt="Capture d&#39;écran 2025-12-14 223746" src="https://github.com/user-attachments/assets/17c68f45-8648-49cd-abf5-cea8b181a0af" />

### Étape 2 – Créer un webhook dans GitHub
#### Tâche 14 : Ajouter le webhook côté GitHub
<img width="960" height="468" alt="Capture d&#39;écran 2025-12-14 224109" src="https://github.com/user-attachments/assets/1361ef2d-21c7-40bb-92a5-92540adad3e8" />

### Étape 3 – Configurer Jenkins pour intégrer GitHub
#### Tâche 15 : Installer le plugin GitHub Integration
<img width="957" height="473" alt="Capture d&#39;écran 2025-12-14 224309" src="https://github.com/user-attachments/assets/9a12f7d1-131c-4064-a11b-35ba9523bacc" />
<img width="960" height="476" alt="Capture d&#39;écran 2025-12-14 224324" src="https://github.com/user-attachments/assets/b7378c98-2ca8-407b-8746-97e16fd19c78" />
<img width="959" height="472" alt="Capture d&#39;écran 2025-12-14 224402" src="https://github.com/user-attachments/assets/9bdfb2ba-29d0-4ad5-be5f-83ca0d6e649c" />

#### Tâche 16 : Configurer l’URL Jenkins publiée (si disponible)
<img width="960" height="447" alt="image" src="https://github.com/user-attachments/assets/97f5484a-2490-44d7-8464-d21124ee2b4a" />

### Étape 4 – Test complet du déclenchement automatique
#### Tâche 17 : Modifier le code et pousser sur GitHub
<img width="960" height="502" alt="Capture d&#39;écran 2025-12-14 225820" src="https://github.com/user-attachments/assets/eff5e4a7-048b-4726-b5c5-4ee6e0902339" />
<img width="959" height="501" alt="Capture d&#39;écran 2025-12-14 225829" src="https://github.com/user-attachments/assets/9556e425-832d-40d8-8e1a-2ff40150a71f" />
<img width="959" height="478" alt="Capture d&#39;écran 2025-12-14 230037" src="https://github.com/user-attachments/assets/66e0442d-cb3f-4954-b265-37aa1a7ebef2" />

#### Tâche 18 : Vérifier côté Jenkins
<img width="956" height="475" alt="Capture d&#39;écran 2025-12-14 230201" src="https://github.com/user-attachments/assets/72c0ff6a-b125-471a-93bf-97e41322f7bf" />
<img width="960" height="466" alt="Capture d&#39;écran 2025-12-14 230224" src="https://github.com/user-attachments/assets/8bbd0bc2-0df2-4b39-b7a9-107c9cb0d7a6" />

## Auteur
* Nom : BEN-LAGHFIRI Majeda
* Cours: Architecture Microservices : Conception, Déploiement et Orchestration
* Date : Decembre 2025
* Encadré par : Pr.Mohamed LACHGAR
