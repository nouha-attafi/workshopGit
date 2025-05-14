"""# 🌐 CodeFam – Plateforme Éducative de Codage (Desktop)

<p align="center">
  <a href="https://github.com/CodeFam">
    <img src="https://img.shields.io/badge/Join%20us%20on-GitHub-blue" alt="CodeFam GitHub"/>
  </a>
  <a href="https://twitter.com/CodeFamApp">
    <img src="https://img.shields.io/badge/Follow%20us%20on-Twitter-1DA1F2" alt="CodeFam Twitter"/>
  </a>
</p>

## 📖 Description du Projet

**CodeFam (Coding Family)** est une application desktop développée avec **JavaFX**, conçue comme une plateforme d'e-learning dédiée à l'apprentissage du codage, inspirée de plateformes comme Coursera ou Udemy. Elle propose une interface intuitive permettant aux utilisateurs d'accéder à une bibliothèque de cours structurés, organisés en packs thématiques, accompagnés de vidéos pédagogiques, quiz interactifs, et un forum intégré pour favoriser les échanges entre apprenants et tuteurs. L'application intègre un système de paiement sécurisé via **Stripe** pour les contenus premium et offre des tableaux de bord statistiques pour suivre les progrès et les activités des utilisateurs.

### 🎯 Fonctionnalités Principales
- **Cours et Contenus** : Accès à des cours organisés par catégories, avec vidéos, PDF téléchargeables, et quiz personnalisables (facile, moyen, difficile).
- **Gestion des Utilisateurs** : Authentification flexible (email/mot de passe ou Google), vérification par email, réinitialisation de mot de passe, et rôles (Admin, Tuteur, Utilisateur) avec permissions spécifiques.
- **Forum Interactif** : Système de posts et commentaires avec support d'images, filtrage de contenu via **API Ninjas**, et structure hiérarchique pour les réponses.
- **Quiz Dynamiques** : Création, modification, et génération aléatoire de quiz avec visualisation des résultats via graphiques (PieChart).
- **Paiement et Facturation** : Intégration de **Stripe** pour des paiements sécurisés et exportation de factures détaillées au format Excel.
- **Statistiques** : Tableaux de bord pour visualiser les données des utilisateurs, revenus, achats, et performances des quiz/offres.
- **Sécurité** : Protection contre les captures d’écran, filtrage de contenu (profanité), et contrôle d’accès par rôle.
- **Recherche Dynamique** : Filtrage en temps réel des catégories, cours, vidéos, quiz, et posts.

## 🗂 Table des Matières

- [Pré-requis](#pré-requis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Structure du Projet](#structure-du-projet)
- [Contribuer](#contribuer)
- [Démo](#démo)
- [Contact](#contact)

## ✅ Pré-requis

Avant de lancer l'application, assurez-vous d'avoir installé :

- **[JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)** : Nécessaire pour exécuter l'application JavaFX.
- **[JavaFX SDK](https://openjfx.io/)** : Framework pour l'interface graphique.
- **[Maven](https://maven.apache.org/)** : Gestion des dépendances.
- **[MySQL](https://www.mysql.com/)** : Base de données pour stocker les données.
- **[Git](https://git-scm.com/)** : Pour cloner le repository.
- **Clé API [Stripe](https://stripe.com/)** : Pour les paiements (mode test recommandé).
- **Clé API [API Ninjas](https://api-ninjas.com/)** : Pour la modération de contenu.

## ⚙ Installation

Suivez ces étapes pour configurer le projet localement :

1. **Cloner le repository** :
   ```bash
   git clone https://github.com/CodeFam/codefamJavaFx.git
   ```

2. **Naviguer dans le dossier du projet** :
   ```bash
   cd codefamJavaFx
   ```

3. **Configurer la base de données** :
   - Créez une base de données MySQL nommée `codefam_db` :
     ```sql
     CREATE DATABASE codefam_db;
     ```
   - Importez le schéma SQL depuis `src/main/resources/database/schema.sql` :
     ```bash
     mysql -u votre_utilisateur -p codefam_db < src/main/resources/database/schema.sql
     ```
   - Mettez à jour les informations de connexion dans `src/main/resources/config.properties` :
     ```properties
     db.url=jdbc:mysql://localhost:3306/codefam_db
     db.user=votre_utilisateur
     db.password=votre_mot_de_passe
     stripe.api.key=sk_test_votre_cle_stripe
     apininjas.api.key=votre_cle_api_ninjas
     ```

4. **Installer les dépendances** :
   ```bash
   mvn clean install
   ```

## 🚀 Utilisation

Pour exécuter l’application :

1. **Ouvrir le projet dans un IDE** (IntelliJ IDEA, Eclipse, etc.).
2. **Exécuter la classe principale** : `src/main/java/main/CodeFamMain.java`.
3. **Ou via la ligne de commande** :
   ```bash
   mvn javafx:run
   ```

### Tester les fonctionnalités :
- **Admin/Tuteur** : Connectez-vous avec un compte admin (ex. `admin@codefam.com`, mot de passe : `admin123`) pour gérer les cours, quiz, utilisateurs, et visualiser les statistiques.
- **Utilisateur** : Créez un compte, vérifiez-le via email, abonnez-vous à des catégories, et accédez aux cours/quiz.
- **Paiements** : Utilisez une carte de test Stripe (ex. `4242 4242 4242 4242`) pour simuler un achat.
- **Forum** : Créez des posts, commentez, et interagissez avec la communauté.
- **Statistiques** : Consultez les tableaux de bord pour voir les graphiques des performances.

### Commandes Maven utiles :
- Compiler : `mvn compile`
- Tester : `mvn test`
- Packager : `mvn package`

## 🗄 Structure du Projet

```
codefamJavaFx/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── main/CodeFamMain.java       # Point d'entrée de l'application
│   │   │   ├── controllers/                # Contrôleurs MVC
│   │   │   ├── models/                    # Entités (Post, Comment, User, etc.)
│   │   │   ├── services/                  # Logique métier
│   │   │   ├── utils/                     # Utilitaires (DB, API, etc.)
│   │   ├── resources/
│   │   │   ├── fxml/                      # Interfaces FXML
│   │   │   ├── css/                       # Styles CSS
│   │   │   ├── config.properties          # Configuration (DB, API)
│   │   │   ├── database/schema.sql        # Schéma SQL
│   ├── test/                              # Tests unitaires
├── pom.xml                                # Dépendances Maven
├── README.md                              # Documentation
```

## 🤝 Contribuer

Nous accueillons les contributions ! Suivez ces étapes :

1. **Forkez le projet**.
2. Créez une branche pour vos modifications :
   ```bash
   git checkout -b feature/nouvelle-fonctionnalite
   ```
3. Commitez vos changements :
   ```bash
   git commit -m "Ajout de nouvelle fonctionnalité"
   ```
4. Poussez votre branche :
   ```bash
   git push origin feature/nouvelle-fonctionnalite
   ```
5. Ouvrez une **Pull Request** sur GitHub.

### Bonnes pratiques :
- Suivez le pattern **MVC**.
- Utilisez des **requêtes préparées** pour les interactions avec la base de données.
- Testez vos modifications avec `mvn test`.
- Documentez votre code et respectez les conventions Java.

## 🎥 Démo

👉 [Regardez la démo de CodeFam sur YouTube](https://www.youtube.com/watch?v=exemple) *(Lien à mettre à jour après publication)*

## 📬 Contact

- **GitHub** : [@CodeFam](https://github.com/CodeFam)
- **Email** : support@codefam.com
- **Twitter** : [@CodeFamApp](https://twitter.com/CodeFamApp)

---

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-JavaFX-orange" alt="Made with JavaFX"/>
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License MIT"/>
</p>
"""
