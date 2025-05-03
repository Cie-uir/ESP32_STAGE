Ent# Formation ESP32 à Marrakech - Site web et système de gestion

![ESP32 Formation](https://img.shields.io/badge/ESP32-Formation-blue)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?logo=bootstrap&logoColor=white)

Une solution complète et autonome pour présenter, gérer les inscriptions et administrer une formation ESP32 à Marrakech. L'ensemble du système fonctionne dans le navigateur, sans serveur ni base de données externe.

## 🌟 Fonctionnalités

### 📱 Site Web Responsive
- Design professionnel et moderne
- Présentation complète de la formation
- Programme détaillé jour par jour
- Informations sur le tarif et les prestations incluses
- Compatible mobile et tablette

### 📝 Formulaire d'Inscription
- Capture de toutes les informations nécessaires
- Validation des champs obligatoires
- Message de confirmation automatique
- Stockage sécurisé des données

### 💾 Base de Données Locale
- Utilisation de LocalStorage pour stocker les inscriptions
- Fonctionnement 100% côté client, sans serveur
- Données accessibles même hors ligne
- Sécurisation avec authentification

### 🛠️ Panneau d'Administration
- Interface de gestion des inscriptions
- Statistiques en temps réel
- Modification du statut des participants
- Exportation des données au format CSV

### 🔄 Gestion Intelligente des Places
- Attribution automatique des statuts (confirmé, en attente, liste d'attente)
- Promotion automatique depuis la liste d'attente en cas d'annulation
- Limitation du nombre de participants

## 🚀 Installation et Utilisation

### Installation Simple

1. Clonez ce dépôt :
   ```bash
   git clone https://github.com/votre-username/formation-esp32-marrakech.git
   cd formation-esp32-marrakech
   ```

2. Ouvrez le fichier `index.html` dans votre navigateur.

C'est tout ! Aucun serveur ou base de données n'est nécessaire.

### 🌐 Déploiement en Ligne

Pour déployer le site sur internet :

1. Hébergez les fichiers sur n'importe quel service d'hébergement web statique (GitHub Pages, Netlify, Vercel, ou un hébergement partagé classique).

2. Aucune configuration serveur n'est nécessaire.

### 👑 Accès à l'Administration

1. Ajoutez `?admin=true` à la fin de l'URL :
   ```
   index.html?admin=true
   ```
   
2. Utilisez le mot de passe par défaut : `admin123`

> ⚠️ **Sécurité** : Pensez à modifier le mot de passe par défaut dans le code pour une utilisation en production !

## 📋 Personnalisation

### Modifier les Informations de la Formation

Ouvrez `index.html` et modifiez les sections suivantes :

- Informations générales (dates, lieu) : dans les balises avec les classes `date-badge` et `banner`
- Programme : dans la section avec la classe `info-card` contenant le programme détaillé
- Prix et prestations : dans la section avec la classe `price-box`
- Coordonnées : dans le footer

### Modifier les Paramètres de Base

Dans le fichier `index.html`, localisez la classe `LocalDB` et modifiez la méthode `initDatabase()` :

```javascript
initDatabase() {
  if (!localStorage.getItem(this.DB_KEY)) {
    const initialData = {
      participants: [],
      settings: {
        maxParticipants: 12, // Nombre maximum de participants
        formationId: 'ESP32-MRK-2025-06', // Référence de la formation
        formationDates: '6-8 Juin 2025', // Dates
        formationLocation: 'Marrakech, Maroc', // Lieu
        formationPrice: 1740, // Prix en euros
        adminPassword: 'admin123' // Mot de passe administrateur
      }
    };
    
    localStorage.setItem(this.DB_KEY, JSON.stringify(initialData));
  }
}
```

### Personnaliser l'Apparence

Le style du site est défini dans la balise `<style>` en tête du document. Les principales variables de couleur sont :

```css
:root {
  --primary-color: #0e4165;   /* Couleur principale */
  --secondary-color: #f44336; /* Couleur secondaire/boutons */
  --light-color: #f5f7fa;     /* Couleur de fond */
  --dark-color: #2c3e50;      /* Couleur de texte */
  --accent-color: #00b0ff;    /* Couleur d'accentuation */
}
```

## 📊 Gestion des Données

### Format des Données

Les inscriptions sont stockées au format JSON dans le LocalStorage du navigateur :

```javascript
{
  "participants": [
    {
      "id": 1,
      "firstName": "Jean",
      "lastName": "Dupont",
      "email": "jean.dupont@example.com",
      "phone": "+33612345678",
      "company": "Entreprise SAS",
      "experience": "intermédiaire",
      "message": "Je suis impatient de participer !",
      "registrationDate": "2025-05-01T10:30:45.123Z",
      "status": "confirmée"
    },
    // ...autres participants
  ],
  "settings": {
    // Configuration comme définie plus haut
  }
}
```

### Exportation des Données

Les données peuvent être exportées en CSV depuis le panneau d'administration. Le fichier généré contient toutes les informations des participants et peut être ouvert dans n'importe quel tableur (Excel, Google Sheets, etc.).

## 🛡️ Sécurité et Limitations

### Sécurité
- Les données sont stockées localement et ne quittent pas l'ordinateur de l'utilisateur
- L'accès à l'administration est protégé par mot de passe
- Aucune connexion à des services externes

### Limitations
- Le stockage est limité à l'espace disponible dans le LocalStorage (généralement 5-10 MB)
- Les données sont stockées par navigateur et par domaine
- Pour une utilisation multi-utilisateurs, envisagez d'ajouter un backend

## 📱 Compatibilité

- ✅ Chrome (Desktop & Mobile)
- ✅ Firefox (Desktop & Mobile)
- ✅ Safari (Desktop & Mobile)
- ✅ Edge (Desktop & Mobile)
- ✅ Opera (Desktop & Mobile)

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus d'informations.

## 🔗 Crédits

- [Bootstrap](https://getbootstrap.com/) - Framework CSS
- [Font Awesome](https://fontawesome.com/) - Icônes
- [Google Fonts](https://fonts.google.com/) - Polices

---

📧 Contact: [nada.electronics@gmail.com](mailto:nada.electronics@gmail.com)

©️ 2025 Natech Formation - Tous droits réservéser file contents here
