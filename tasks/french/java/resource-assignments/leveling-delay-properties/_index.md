---
title: Gérer les propriétés du délai de mise à niveau dans Aspose.Tasks
linktitle: Gérer les propriétés de délai de mise à niveau pour les affectations de ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment gérer les propriétés de délai de mise à niveau pour les affectations de ressources dans Aspose.Tasks for Java avec ce didacticiel complet.
weight: 17
url: /fr/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les propriétés du délai de mise à niveau dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous passerons en revue le processus de gestion des propriétés de délai de mise à niveau pour les affectations de ressources dans Aspose.Tasks for Java. Aspose.Tasks est une puissante bibliothèque Java qui vous permet de travailler avec des fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project sur votre système.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que Java JDK est installé sur votre système. Vous pouvez le télécharger et l'installer à partir du[site web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez la bibliothèque Aspose.Tasks pour Java à partir du[page de téléchargement](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre projet Java pour utiliser les fonctionnalités d'Aspose.Tasks :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Étape 1 : Créer un objet de projet
 Instancier un`Project` objet:
```java
Project prj = new Project();
```
## Étape 2 : Créer une tâche
Ajoutez une tâche au projet :
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Étape 3 : Définir la date de début et la durée de la tâche
Définissez la date de début et la durée de la tâche :
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Étape 4 : ajouter une ressource
Ajoutez une ressource au projet :
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Étape 5 : Créer une affectation de ressources
Créez une affectation de ressource pour la tâche et la ressource :
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Étape 6 : Définir le délai de mise à niveau
Définissez le délai de mise à niveau pour l'affectation :
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Étape 7 : Afficher les résultats
Imprimez le délai de mise à niveau et d'autres informations pertinentes :
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Conclusion
Dans ce didacticiel, nous avons appris à gérer les propriétés de délai de mise à niveau pour les affectations de ressources dans Aspose.Tasks for Java. En suivant ces étapes, vous pouvez gérer efficacement les affectations de ressources dans vos projets Java.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres bibliothèques Java ?

R : Oui, Aspose.Tasks peut être intégré à d'autres bibliothèques Java pour améliorer les capacités de gestion de projet.

### Q : Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?

: Oui, Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.

### Q : Où puis-je trouver une assistance supplémentaire pour Aspose.Tasks ?

 R : Vous pouvez trouver de l'aide et des ressources sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q : Puis-je essayer Aspose.Tasks avant d'acheter ?

 R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks auprès du[page des versions](https://releases.aspose.com/).

### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks ?

 R : Vous pouvez demander une licence temporaire auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
