---
title: Arrêter et reprendre les affectations de ressources dans Aspose.Tasks
linktitle: Arrêter et reprendre les affectations de ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à gérer efficacement les affectations de ressources dans Aspose.Tasks pour Java avec ce didacticiel étape par étape.
type: docs
weight: 23
url: /fr/java/resource-assignments/stop-resume-assignment/
---
## Introduction
Dans ce didacticiel, nous apprendrons comment arrêter et reprendre les affectations de ressources à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante API Java qui permet aux développeurs de travailler avec des fichiers Microsoft Project sans avoir besoin d'installer Microsoft Project sur leurs systèmes. Nous diviserons le processus en étapes gérables pour le rendre facile à suivre.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Tasks pour la bibliothèque Java téléchargée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
- Compréhension de base de la programmation Java.
## Importer des packages
Tout d'abord, importons les packages nécessaires dans notre projet Java :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Étape 1 : Charger le fichier de projet
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
// Charger le fichier du projet
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Dans cette étape, nous chargeons le fichier du projet dans un`Project` objet en utilisant le chemin du fichier.
## Étape 2 : Parcourir les affectations de ressources
```java
// Définir une date minimale
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Parcourir les affectations de ressources
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Ici, nous définissons une date minimale et commençons à parcourir chaque affectation de ressources du projet.
## Étape 3 : Vérifiez les dates d'arrêt et de reprise
```java
    // Vérifier la date d'arrêt
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Vérifier la date de reprise
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Dans cette étape, nous vérifions si les dates d'arrêt et de reprise de chaque affectation de ressource sont antérieures à la date minimale. Si c'est le cas, nous imprimons "NA", sinon, nous imprimons les dates respectives.
## Conclusion
Dans ce didacticiel, nous avons appris comment arrêter et reprendre les affectations de ressources dans Aspose.Tasks pour Java. En suivant les étapes fournies, vous pouvez facilement implémenter cette fonctionnalité dans vos projets Java.

## FAQ
### Puis-je utiliser Aspose.Tasks sans que Microsoft Project soit installé ?
Oui, Aspose.Tasks vous permet de travailler avec des fichiers Microsoft Project sans avoir besoin d'installer Microsoft Project sur votre système.
### Où puis-je trouver plus de documentation ?
 Vous pouvez trouver une documentation détaillée[ici](https://reference.aspose.com/tasks/java/).
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l'aide si je rencontre des problèmes ?
Vous pouvez obtenir le soutien de la communauté[ici](https://forum.aspose.com/c/tasks/15).
### Puis-je acheter une licence temporaire ?
 Oui, vous pouvez acheter une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).