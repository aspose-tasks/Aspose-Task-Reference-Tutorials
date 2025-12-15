---
date: 2025-12-15
description: Apprenez à lire les données MS Project Online en utilisant Aspose.Tasks
  Java. Ce guide montre comment récupérer la liste des projets, lister les projets
  SharePoint et obtenir le nombre de ressources.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java : Lecture sans effort des données MS Project Online'
url: /fr/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java : Lecture sans effort des données MS Project Online

## Introduction
Dans le domaine de la gestion de projet, manipuler les données Microsoft Project Online de manière efficace est essentiel pour des opérations rationalisées. **aspose tasks java** fournit une API robuste et facile à utiliser qui vous permet de lire les données Project Online sans vous battre avec des appels HTTP de bas niveau. Dans ce tutoriel, nous allons parcourir comment récupérer une liste de projets, lister les projets SharePoint et obtenir le nombre de ressources de chaque projet — le tout avec seulement quelques lignes de code Java.

## Réponses rapides
- **Que fait aspose tasks java ?** Il lit et manipule les fichiers Microsoft Project et les données Project Online de manière programmatique.  
- **Ai-je besoin d'une licence pour l'essayer ?** Un essai gratuit est disponible ; une licence est requise pour une utilisation en production.  
- **Quelles informations d'identification sont requises ?** Domaine SharePoint, nom d'utilisateur et mot de passe (ou jeton Azure AD).  
- **Puis-je lister les projets SharePoint ?** Oui – utilisez `ProjectServerManager.getProjectList()` pour les récupérer.  
- **Comment obtenir le nombre de ressources ?** Chargez chaque objet `Project` et appelez `project.getResources().size()`.

## Qu'est-ce que aspose tasks java ?
**aspose tasks java** est une bibliothèque orientée développeur qui abstrait les complexités des formats de fichiers Microsoft Project et des API REST de Project Server. Elle vous permet de lire, créer et modifier les données de projet directement depuis des applications Java, facilitant ainsi l'intégration avec les systèmes d'entreprise existants.

## Pourquoi utiliser aspose tasks java pour lire MS Project Online ?
- **Pas de gestion manuelle du HTTP** – la bibliothèque se charge de l'authentification et des appels REST.  
- **Sécurité de typage forte** – travaillez avec `Project`, `ProjectInfo` et d'autres POJOs au lieu de JSON brut.  
- **Cross‑platform** – fonctionne sur tout environnement compatible JVM.  
- **Ensemble de fonctionnalités riche** – au-delà de la lecture, vous pouvez également mettre à jour les tâches, les ressources et les chronologies.

## Prérequis
1. **Java Development Kit (JDK)** – JDK 8 ou supérieur installé.  
2. **Aspose.Tasks for Java library** – téléchargez-le depuis [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – avec les permissions de lire les projets.  
4. **SharePoint domain address** – où votre instance Project Online réside.  
5. **Username and password** – ou les informations d'identification Azure AD appropriées pour l'authentification.

## Importer les packages
Tout d'abord, importez les classes essentielles d'Aspose.Tasks que nous utiliserons tout au long du tutoriel :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Étape 1 : Définir le domaine SharePoint, le nom d'utilisateur et le mot de passe
Définissez les détails de connexion pour votre environnement Project Online. Remplacez les valeurs placeholders par vos propres informations d'identification.
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Étape 2 : Authentifier avec les informations d'identification du serveur de projet
Créez un objet `ProjectServerCredentials` et initialisez un `ProjectServerManager`. Ce gestionnaire prendra en charge tous les appels ultérieurs à Project Online.
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Étape 3 : Récupérer la liste des projets et afficher les informations
Utilisez le gestionnaire pour **récupérer la liste des projets** (lister les projets SharePoint) et afficher les informations de base telles que le nom, la date de création et la date de dernière sauvegarde.
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Étape 4 : Charger les projets individuels et afficher le nombre de ressources
Pour chaque projet retourné à l'étape précédente, chargez l'objet complet `Project` et affichez le **nombre de ressources**.
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Échec de l'authentification** | Domaine, nom d'utilisateur ou mot de passe incorrect. | Vérifiez les informations d'identification et assurez-vous que le compte possède les permissions de lecture sur Project Online. |
| **SSLHandshakeException** | L'environnement Java ne dispose pas de la version TLS requise. | Mettez à jour le JDK vers la dernière version ou activez TLS 1.2+. |
| **`reader.getProjectList()` renvoie vide** | Le compte n'a accès à aucun projet. | Vérifiez les permissions sur Project Online ou utilisez un compte administrateur. |
| **Les grands projets provoquent OutOfMemoryError** | Le chargement de nombreux projets simultanément consomme de la mémoire. | Chargez les projets un à la fois et libérez les références après utilisation. |

## Questions fréquemment posées
### Q : Puis-je utiliser aspose tasks java pour modifier les données MS Project Online ?
R : Oui, Aspose.Tasks offre des capacités étendues pour lire **et** modifier les données Project Online de manière programmatique.

### Q : Aspose.Tasks prend‑il en charge d'autres formats de fichiers de gestion de projet ?
R : Absolument. Il prend en charge MPP, XML, Primavera et bien d’autres, assurant la compatibilité à travers divers écosystèmes de projet.

### Q : Existe‑t‑il un essai gratuit pour Aspose.Tasks for Java ?
R : Oui, vous pouvez obtenir un essai gratuit depuis [here](https://releases.aspose.com/) pour explorer les fonctionnalités d'Aspose.Tasks.

### Q : Où puis‑je trouver une documentation complète pour Aspose.Tasks for Java ?
R : Vous pouvez consulter la documentation détaillée [here](https://reference.aspose.com/tasks/java/) pour obtenir des instructions complètes sur l'utilisation d'Aspose.Tasks dans vos projets Java.

### Q : Quelles options de support sont disponibles pour Aspose.Tasks for Java ?
R : Si vous rencontrez des problèmes ou avez des questions, vous pouvez obtenir de l'aide sur le forum communautaire Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2025-12-15  
**Testé avec :** Aspose.Tasks for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}