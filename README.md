# 🌐 3alamni – Plateforme Éducative (Web)
<p align="center">
  <a href="https://www.facebook.com/profile.php?id=61572284563201">
    <img src="https://img.shields.io/badge/Join%20us%20on-Facebook-blue" alt="3allamni facebook"/>
  </a>
</p>

## 📖 Description du Projet

3alamni est une application web développée dans le cadre du projet intégré Web-Java de 3e année universitaire (2024-2025).  
Il s'agit d'une plateforme éducative qui propose à ses utilisateurs de :

- Suivre des cours  
- Participer à des formations en ligne
- Réserver des événements éducatifs  
- Réaliser des quiz
- Communiquer avec d'autres étudiants grâce à notre communauté
- Réclamer en cas de problème


L’objectif est de faciliter l’apprentissage autonome grâce à une interface intuitive et des fonctionnalités variées.

## 🗂 Table des Matières

- [Pré-requis](#pré-requis)  
- [Installation](#installation)  
- [Utilisation](#utilisation)  

## ✅ Pré-requis

Avant d’installer le projet, assurez-vous d’avoir les éléments suivants installés sur votre machine :

- PHP 8.1.26  
- [Composer](https://getcomposer.org/)  
- [Symfony CLI](https://symfony.com/download)  
- MySQL  
- [Git](https://git-scm.com/)

## ⚙ Installation

1. Cloner le repository :
bash
git clone https://github.com/SlimBizid/3alamni
# Aller au dossier
cd 3alamni

2. Installer symfony :
  bash
scoop install symfony-cli

3. Installer les dépendances :
bash
composer install
npm install

4. Build Tailwind et les dépendances :
bash
npm run build 

5. Créer et configurer la base de données :
bash
symfony console doctrine:database:create
symfony console doctrine:migrations:migrate

6. Lancer le serveur local Symfony :
bash
symfony server:start

7. Accéder à l'application depuis votre navigateur :
👉 [http://127.0.0.1:8000](http://127.0.0.1:8000)

Option: Pour voir d'avantage de fonctionnalités, run cnnmodel/app.py, MessageServer et src/recommender/app.py 
bash 
java org.example.java3alamni/Service.MessageServer
python cnnmodel/app.py
python src/recommender/app.py


## 🚀 Utilisation

Une fois l’application lancée, vous pouvez :

- Explorer les cours disponibles  
- Suivre des formations en ligne  
- Répondre à des quiz pour tester vos connaissances  
- Gérer votre profil utilisateur  
- Participer à des événements
- Reclamer en cas de problème

👉 [Essayer la version Web de 3alamni](https://github.com/MeriemGharbi/Java3alamni)
