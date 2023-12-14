# Intégration d'une Activité Pédagogique Externe à Educentre

## 1. Vue d'ensemble

Ce document fournit des instructions sur la manière de développer et d'intégrer une activité pédagogique externe dans la plateforme Educentre. L'activité est développée comme une page web standard, qui sera ensuite incluse dans Educentre via un `iframe`.

## 2. Étapes de Développement

### 1. Création de la Page Web

Développez votre activité pédagogique sous forme de page web. Cette page doit être conçue pour être intégrée dans un iframe et doit être responsive pour s'adapter à différentes tailles d'écran.

### 2. Réception du Token de Session

Educentre appelera votre page web avec un token de session ajouté en tant que fragment d'URL. Par exemple :

```
http://localhost:8080/index.html#token=cf2a0288-4f7b-46ae-9938-b15559146ec2
```

Votre application doit être capable d'extraire ce token de l'URL pour l'utiliser dans les interactions avec l'API d'Educentre.

### 3. Interactions avec l'API Educentre

Pour remonter des informations aux accompagnateurs via Educentre, votre application doit effectuer une requête POST à l'API Educentre. Voici un exemple d'URL pour l'API de reporting :

```
https://api.educentre.fr/api/v1/training-activities/cf2a0288-4f7b-46ae-9938-b15559146ec2/reporting
```

Assurez-vous que votre requête POST contienne les données nécessaires dans le format attendu par l'API, y compris les informations d'authentification dans le header `Authorization`.

### 4. Considérations de Sécurité

Assurez-vous que toutes les communications avec l'API Educentre sont sécurisées.
Respectez les normes de confidentialité et de protection des données des utilisateurs.

### 5. Test et Déploiement

Testez votre page web en local pour vous assurer qu'elle fonctionne correctement dans un `iframe`.

Testez la réception et l'utilisation du token de session.
Testez la communication avec l'API Educentre.
Une fois les tests réussis, déployez votre page web sur le serveur de production.

# Support

Pour toute assistance technique ou question concernant l'intégration, veuillez contacter l'équipe de support d'Educentre.