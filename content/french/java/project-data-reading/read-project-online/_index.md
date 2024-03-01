---
title: Lecture de données en ligne MS Project sans effort avec Aspose.Tasks
linktitle: Lecture des données en ligne du projet dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment lire sans effort les données Microsoft Project Online à l'aide d'Aspose.Tasks pour Java. Améliorez vos capacités de gestion de projet.
type: docs
weight: 13
url: /fr/java/project-data-reading/read-project-online/
---
## Introduction
Dans le domaine de la gestion de projet, la gestion efficace des données Microsoft Project Online est cruciale pour rationaliser les opérations. Aspose.Tasks for Java fournit une solution robuste pour lire ces données sans effort. Ce didacticiel explique comment exploiter Aspose.Tasks pour accéder et manipuler les données MS Project Online de manière transparente.
## Conditions préalables
Avant de plonger dans ce didacticiel, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : installez le JDK pour compiler et exécuter des programmes Java.
2.  Aspose.Tasks pour la bibliothèque Java : téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet Java. Vous pouvez l'acquérir auprès de[ici](https://releases.aspose.com/tasks/java/).
3. Compte Microsoft Project Online : obtenez des informations d'identification valides pour accéder aux données MS Project Online.
4. Adresse de domaine SharePoint : adresse de domaine SharePoint où résident vos données MS Project Online.
5. Nom d'utilisateur et mot de passe : informations d'identification pour authentifier l'accès à MS Project Online.
## Importer des packages
Dans votre projet Java, importez les packages Aspose.Tasks nécessaires pour une intégration transparente :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Étape 1 : Définir l'adresse de domaine SharePoint, le nom d'utilisateur et le mot de passe
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com" ;
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Remplacer`"https://contoso.sharepoint.com"` avec votre adresse de domaine SharePoint,`"admin@contoso.onmicrosoft.com"` avec votre nom d'utilisateur, et`"MyPassword"` avec votre mot de passe.
## Étape 2 : Authentification avec les informations d'identification de Project Server
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Créer`ProjectServerCredentials` objet avec l’adresse du domaine SharePoint, le nom d’utilisateur et le mot de passe. Puis initialisez`ProjectServerManager` avec ces informations d'identification.
## Étape 3 : Récupérer la liste des projets et afficher les informations
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Parcourez la liste de projets obtenue à partir de`reader.getProjectList()` et affichez les détails du projet tels que le nom, la date de création et la date du dernier enregistrement.
## Étape 4 : Charger des projets individuels et compter les ressources de sortie
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Pour chaque projet, chargez-le en utilisant`reader.getProject(p.getId())` et affichez le nom du projet ainsi que le nombre de ressources associées.

## Conclusion
Aspose.Tasks for Java simplifie le processus de lecture des données MS Project Online, offrant aux développeurs un ensemble d'outils puissants pour rationaliser les tâches de gestion de projet. En suivant ce didacticiel, vous pouvez intégrer efficacement Aspose.Tasks dans vos applications Java pour accéder et manipuler facilement les données du projet.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour Java pour modifier les données MS Project Online ?
R : Oui, Aspose.Tasks offre des fonctionnalités étendues non seulement pour lire mais également pour modifier les données MS Project Online par programme.
### Q : Aspose.Tasks prend-il en charge d'autres formats de fichiers de gestion de projet ?
R : Absolument, Aspose.Tasks prend en charge divers formats de fichiers, notamment MPP, XML, etc., garantissant ainsi la compatibilité avec divers systèmes de gestion de projet.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/) pour explorer les caractéristiques et fonctionnalités d’Aspose.Tasks.
### Q : Où puis-je trouver une documentation complète sur Aspose.Tasks pour Java ?
 R : Vous pouvez vous référer à la documentation détaillée[ici](https://reference.aspose.com/tasks/java/)pour des conseils complets sur l’utilisation d’Aspose.Tasks dans vos projets Java.
### Q : Quelles options de support sont disponibles pour Aspose.Tasks pour Java ?
 R : Si vous rencontrez des problèmes ou avez des questions, vous pouvez demander de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).