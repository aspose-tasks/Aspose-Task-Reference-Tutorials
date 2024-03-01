---
title: Lire MS Project depuis Primavera avec Aspose.Tasks pour Java
linktitle: Lire le projet de Primavera dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à lire des fichiers MS Project à partir de Primavera XML de manière transparente à l'aide d'Aspose.Tasks pour Java. Améliorez l’efficacité de votre gestion de projet.
type: docs
weight: 20
url: /fr/java/project-management/read-primavera/
---
## Introduction
Dans la gestion de projet, l'interopérabilité entre les différentes plates-formes logicielles est cruciale pour un flux de travail fluide. Aspose.Tasks for Java fournit des fonctionnalités robustes pour lire les fichiers Microsoft Project à partir de Primavera XML. Ce didacticiel vous guidera tout au long du processus de lecture des fichiers MS Project à partir de Primavera à l'aide d'Aspose.Tasks pour Java, vous permettant d'examiner efficacement les propriétés spécifiques à Primavera des tâches.
## Conditions préalables
Avant de continuer, assurez-vous que les prérequis suivants sont installés et configurés :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Tasks pour Java : téléchargez et installez Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Étape 1 : Configurer le répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Assurez-vous de remplacer`"Your Data Directory"` avec le chemin réel vers votre répertoire de données.
## Étape 2 : Lire le projet à partir de Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Assurez-vous de remplacer`"PrimaveraProject.xml"` avec le nom réel de votre fichier XML Primavera.
## Étape 3 : Parcourir les tâches et récupérer les propriétés spécifiques à Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Ce code parcourt chaque tâche du projet, imprimant les propriétés spécifiques à Primavera pertinentes.

## Conclusion
Dans ce didacticiel, vous avez appris à lire des fichiers MS Project à partir de Primavera XML à l'aide d'Aspose.Tasks pour Java. Cette fonctionnalité permet une intégration et une analyse transparentes des données de projet sur différentes plates-formes, améliorant ainsi l'efficacité globale de la gestion de projet.
## FAQ
### Q : Puis-je modifier les propriétés spécifiques à Primavera des tâches à l'aide d'Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks for Java fournit des API pour modifier les propriétés des tâches spécifiques à Primavera selon les besoins.
### Q : Aspose.Tasks pour Java prend-il en charge la lecture d'autres formats de fichiers de projet ?
R : Oui, Aspose.Tasks for Java prend en charge la lecture de divers formats de fichiers de projet, notamment MPP, XML et Primavera XML.
### Q : Aspose.Tasks for Java est-il adapté aux applications de gestion de projet au niveau de l'entreprise ?
R : Absolument, Aspose.Tasks pour Java offre des fonctionnalités robustes et une évolutivité, ce qui le rend adapté aux applications de gestion de projet au niveau de l'entreprise.
### Q : Puis-je extraire des informations sur les ressources des projets Primavera à l'aide d'Aspose.Tasks pour Java ?
: Oui, Aspose.Tasks pour Java vous permet d'extraire des informations sur les ressources ainsi que les détails des tâches des projets Primavera.
### Q : Où puis-je trouver une assistance ou une documentation supplémentaire pour Aspose.Tasks pour Java ?
 R : Vous pouvez trouver une documentation complète et accéder à des forums d'assistance sur le[Documentation Aspose.Tasks pour Java](https://reference.aspose.com/tasks/java/) page.