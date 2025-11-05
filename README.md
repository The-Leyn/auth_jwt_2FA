# 🎭 Mini-application PHP de gestion de spectacles

Projet académique d’application web en **PHP orienté objet**, intégrant un système complet d’**authentification sécurisée via JWT**, **sans dépendance externe** (comme Firebase).  
L’application simule un **site de réservation de spectacles** avec gestion des utilisateurs, rôles, réservations et sécurité avancée.

Ce projet illustre les **fondamentaux d’une architecture MVC moderne et simplifiée** :  
Routeur, contrôleurs, entités, vues, sécurité via **JWT + Refresh Tokens**, et désormais une **authentification à deux facteurs (2FA)** configurable.

---

## ✨ Fonctionnalités principales

### 🔓 Pages publiques

- Accueil, liste et fiche des spectacles

### 🔐 Pages utilisateurs

- Réservation de places
- Profil et historique des réservations
- Activation et gestion de la **double authentification (2FA)** :
  - 🔢 **Application d’authentification (OTP)** (Google Authenticator, Authy, etc.)
  - ✉️ **Code de vérification par e-mail**
  - 📱 **Code de vérification par SMS** (via **Twilio**)

### 🛠️ Pages administrateurs

- Ajout, modification et suppression des spectacles

### ⚙️ Sécurité et architecture

- Gestion des droits via middleware `#[IsGranted]` et `#[Authenticated]`
- Authentification **JWT** + **Refresh Tokens** (sans librairie externe)
- Mise à jour automatique du token lors des changements de méthode 2FA
- Séparation stricte **MVC** : routeur, contrôleurs, vues, entités, repositories

### 💾 Base de données

- **MySQL / phpMyAdmin**
- Tables : `user`, `spectacle`, `reservation`, etc.

---

## ⚙️ Installation & Prérequis

### 🧰 Prérequis techniques

Avant d’installer le projet, assurez-vous d’avoir :

- Un **serveur local PHP** (MAMP, XAMPP, WAMP, Laragon, etc.)
- **PHP 8.0+**
- **Composer**
- Une base **MySQL**
- Un compte **Twilio** (pour l’envoi de SMS)
- Une clé **SendGrid** (pour l’envoi d’e-mails)

---

## 📦 Étapes d’installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/Woodiss/auth_jwt_P1.git
cd auth_jwt_P1
```

### 2. Installer les dépendances PHP

```bash

composer install
```

### 3. Configurer les variables d'environnement

Copier le fichier `.env.example` et renseignez vos informations

```env

# Base de données
DB_DRIVER=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_NAME=auth_jwt_p1
DB_USER=root
DB_PASS=
DB_CHARSET=utf8mb4

# Envoi d'e-mails (2FA par email)
SENGRID_API_KEY=your_sendgrid_api_key
SENGRID_SENDER=your_verified_sender_email@example.com

# Envoi de SMS (2FA par SMS)
TWILIO_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE=+1234567890
```

```

```

```

```

### 4. Importer la base de données

1. Ouvrez phpMyAdmin

2. Créez une base nommée auth_jwt_p1

3. Importez le fichier SQL fourni à la racine du projet :

`auth_jwt_p1.sql`

### 5. Lancer le serveur php

```bash
php -S localhost:8000 -t public
```

## Compte de démonstration

**Utilisateur**

- Email : compte.user@gmail.fr
- Mot de passe : azertyui

**Admin**

- Email : compte.admin@gmail.fr
- Mot de passe : azertyui

