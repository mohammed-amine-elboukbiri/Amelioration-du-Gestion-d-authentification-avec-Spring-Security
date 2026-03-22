# 🔐 Spring Boot - Système d'Authentification Sécurisé (v2)

Une application web Spring Boot offrant un système d'authentification complet avec gestion des rôles, gestion des sessions et une interface Thymeleaf enrichie. Ce projet est une évolution directe du [mini-projet d'authentification par rôles](#-lien-avec-le-projet-précédent).

---

## 🔗 Lien avec le projet précédent

Ce projet fait suite au mini-projet d'authentification basé sur les rôles. Il en reprend les fondations et les enrichit avec des fonctionnalités plus complètes et une approche plus proche d'une application réelle.

| Fonctionnalité                        | Projet v1 | Projet v2 (ce projet) |
|---------------------------------------|-----------|-----------------------|
| Authentification en mémoire           | ✅        | ✅                    |
| Rôles ADMIN / USER                    | ✅        | ✅                    |
| Page de login personnalisée           | ✅        | ✅ (améliorée)        |
| Dashboards par rôle                   | ✅        | ✅ (enrichis)         |
| Gestion des autorisations d'accès     | Basique   | ✅ Complète           |
| Gestion des sessions                  | ❌        | ✅                    |
| Redirection intelligente après login  | ❌        | ✅                    |
| Sécurité renforcée (CSRF, headers...) | ❌        | ✅                    |

---

## 📋 Description

Cette version apporte une approche plus structurée et plus robuste de la sécurité Spring, avec notamment :

- La gestion des utilisateurs en mémoire via `InMemoryUserDetailsManager`
- Un contrôle d'accès aux pages selon le rôle (`ADMIN`, `USER`)
- Une page de connexion personnalisée et améliorée
- Une redirection intelligente après login selon le rôle de l'utilisateur
- La gestion des sessions et de la déconnexion sécurisée
- Des dashboards dédiés et enrichis pour chaque rôle

---

## 🛠️ Technologies utilisées

| Technologie            | Version |
|------------------------|---------|
| Java                   | 21      |
| Spring Boot            | 4.0.4   |
| Spring Security        | 6.x     |
| Thymeleaf              | 3.x     |
| Thymeleaf Extras Security | 3.x  |
| Maven                  | 3.x     |

---

## 🏗️ Structure du projet

![structure](https://github.com/user-attachments/assets/ff187cfc-2e2c-4054-9502-845c15959bad)

---


## 🔒 Protection des routes

| Route                  | Accès autorisé    |
|------------------------|-------------------|
| `/login`               | Tout le monde     |
| `/admin/**`            | `ADMIN` seulement |
| `/user/**`             | `USER` seulement  |
| `/access-denied`       | Authentifié       |
| `/`                    | Authentifié       |

---

## Video d'affichage


https://github.com/user-attachments/assets/d1053974-c7cc-432c-8af7-3f5080ff76a0


---

## 🖥️ Pages de l'application

- **`/login`** — Page de connexion personnalisée
- **`/admin/dashboard`** — Espace dédié à l'administrateur
- **`/user/dashboard`** — Espace dédié à l'utilisateur
- **`/access-denied`** — Page affichée en cas d'accès non autorisé
- **`/logout`** — Déconnexion et invalidation de session

---


## 📚 Concepts illustrés

- **Authentication** — Vérification de l'identité via formulaire personnalisé
- **Authorization** — Contrôle d'accès granulaire selon les rôles
- **InMemoryUserDetailsManager** — Gestion des utilisateurs sans base de données
- **SecurityFilterChain** — Chaîne de filtres Spring Security
- **AuthenticationSuccessHandler** — Redirection personnalisée après login
- **Gestion des sessions** — Contrôle du nombre de sessions et invalidation à la déconnexion
- **Thymeleaf Security** — Affichage conditionnel selon le rôle dans les templates

---

## 🔮 Pistes d'évolution (v3)

- Persistance des utilisateurs en base de données (Spring Data JPA + MySQL/PostgreSQL)
- Encodage des mots de passe avec `BCryptPasswordEncoder`
- Mise en place de JWT pour une authentification stateless
- Ajout d'une interface d'administration pour gérer les utilisateurs
- Journalisation des connexions et des accès

---
