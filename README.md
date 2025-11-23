#  Spring Security JPA — Authentication avec Base de Données

Ce TP met en place un système de login avec Spring Security et MySQL.
Les utilisateurs et leurs rôles sont stockés en base.
Spring vérifie le mot de passe, redirige après connexion et bloque l'accès aux pages selon le rôle (ADMIN/USER).

##  Objectifs du projet
- Mettre en place un système d’authentification sécurisé.
- Stocker les utilisateurs et rôles dans MySQL.
- Configurer Spring Security avec JPA.
- Créer un formulaire de connexion personnalisé via Thymeleaf.
- Restreindre l’accès aux pages selon les rôles :  
  - `ADMIN` → accès aux pages admin  
  - `USER` → accès aux pages user  
  - Tous les utilisateurs → accès à /login  
- Initialiser la base avec des utilisateurs par défaut.
- Effectuer des tests fonctionnels de l’authentification.

---


---


---

##  Structure du projet (arborescence)
<img width="650" height="804" alt="image" src="https://github.com/user-attachments/assets/d402ea3b-0bb8-41cd-8708-43b1579ddfaa" />



##  Resultat :

USER ne peut pas entrer dans ADMIN

ADMIN peut accéder à tout


https://github.com/user-attachments/assets/a40a84ec-aa60-4f9f-b16c-c48c41fc8cce




