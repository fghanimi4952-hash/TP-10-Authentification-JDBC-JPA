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


## Fonctionnement global de l’authentification

L’utilisateur accède à /login.

Il saisit username + password.

Spring Security utilise CustomUserDetailsService pour :

vérifier si l’utilisateur existe

récupérer son mot de passe hashé

récupérer ses rôles

BCrypt compare les mots de passe.

Si OK → redirection vers /home.

Si KO → redirection vers /login?error=true.

Les pages “admin” et “users” sont filtrées en fonction des rôles.

##  Base de données (MySQL)
Tables générées automatiquement :

user

role

user_roles (ManyToMany)

## Utilisateurs initialisés
username	password	roles
admin	1234	ADMIN + USER
user	1111	USER

(Pass hashés avec BCrypt)

##  Tests fonctionnels
##  Test 1 — Page de login

URL : http://localhost:8085/login

Résultat : formulaire s’affiche

## Test 2 — Login correct (admin)

username : admin

password : 1234

Résultat : accès autorisé à /home

##  Test 3 — Login incorrect

username : admin

password : 0000

Résultat : /login?error=true

##  Test 4 — Accès non authentifié

Aller à /home sans login

Résultat : redirection automatique → /login

##  Test 5 — Rôles (si routes Admin/User existent)

USER ne peut pas entrer dans ADMIN

ADMIN peut accéder à tout


https://github.com/user-attachments/assets/a40a84ec-aa60-4f9f-b16c-c48c41fc8cce




