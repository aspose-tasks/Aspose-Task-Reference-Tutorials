---
date: 2026-01-10
description: Apprenez comment modifier le contour et générer des données temporelles
  pour les affectations de ressources en utilisant Aspose.Tasks pour Java, améliorant
  ainsi l’efficacité de la gestion de projet.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment modifier le contour dans Aspose.Tasks pour les données à phases temporelles
url: /fr/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier le contour dans Aspose.Tasks pour les données temporelles

## Introduction
Dans ce tutoriel, vous découvrirez **comment modifier le contour** d’une affectation de ressource et générer des données temporelles à l’aide d’Aspose.Tasks pour Java. Les données temporelles révèlent la répartition du travail sur la chronologie du projet, vous permettant d’ajuster finement les plannings, d’équilibrer les charges de travail et de prendre des décisions basées sur les données.

## Réponses rapides
- **Qu’est‑ce qu’un contour ?** Un contour de travail définit comment l’effort est réparti sur la durée d’une tâche (par ex., Plat, Tortue, Cloche).  
- **Pourquoi modifier un contour ?** Pour refléter des modèles de travail réalistes tels que le chargement anticipé ou différé.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (toute version récente).  
- **Ai‑je besoin d’une licence ?** Oui, une licence valide d’Aspose.Tasks est nécessaire pour une utilisation en production.  
- **Puis‑je voir les résultats dans la console ?** L’exemple affiche les dates de début et les valeurs pour chaque segment temporel.

## Qu’est‑ce que « comment modifier le contour » ?
Modifier un contour signifie mettre à jour la propriété `WORK_CONTOUR` d’une `ResourceAssignment`. Aspose.Tasks prend en charge plusieurs contours prédéfinis (Plat, Tortue, Cloche, etc.) qui influencent la façon dont le travail est alloué dans le temps.

## Pourquoi utiliser Aspose.Tasks pour générer des données temporelles ?
- **Rapports précis :** Exportez une répartition exacte du travail pour les outils de reporting.  
- **Planification de scénarios :** Testez différents contours sans modifier le planning d’origine.  
- **Automatisation :** Intégrez‑le aux pipelines CI pour valider automatiquement la santé du projet.

## Prérequis
Avant de commencer, assurez‑vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) : assurez‑vous que le JDK est installé sur votre système. Vous pouvez le télécharger et l’installer depuis [ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Bibliothèque Aspose.Tasks pour Java : vous devez posséder la bibliothèque Aspose.Tasks pour Java. Vous pouvez la télécharger depuis le [site web](https://releases.aspose.com/tasks/java/).

## Importer les packages
Tout d'abord, importons les packages nécessaires pour travailler avec Aspose.Tasks :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Étape 1 : lire le fichier MPP source
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Étape 2 : obtenir la tâche et l’affectation de ressource
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Comment modifier le contour – Plat (défaut)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Tortue
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Chargement arrière
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Chargement avant
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Cloche
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Pic précoce
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Pic tardif
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Double pic
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problèmes courants et astuces
- **Le contour ne se met pas à jour ?** Assurez‑vous d’appeler `firstRA.set(Asn.WORK_CONTOUR, …)` *avant* de récupérer les données temporelles.
- **Valeurs inattendues ?** Vérifiez que les dates de début et de fin de la tâche sont correctement définies dans le fichier MPP source.
- **Astuce de performance :** Réutilisez la même instance `Project` lors de l’itération sur plusieurs contours afin d’éviter des I/O de fichiers inutiles.

## FAQ
### Puis‑je utiliser Aspose.Tasks avec d’autres bibliothèques Java ?
Oui, Aspose.Tasks peut être intégré à d’autres bibliothèques Java pour enrichir les capacités de gestion de projet.

### Aspose.Tasks convient‑il aux projets d’entreprise à grande échelle ?
Absolument, Aspose.Tasks est conçu pour gérer des projets de toutes tailles, y compris les initiatives d’entreprise à grande échelle.

### Aspose.Tasks prend‑il en charge différents formats de fichiers de projet ?
Oui, Aspose.Tasks prend en charge une variété de formats, tels que MPP, XML et MPX.

### Puis‑je personnaliser les contours de travail selon les exigences de mon projet ?
Oui, vous pouvez définir des contours de travail personnalisés pour répondre à des besoins de planification spécifiques.

### Existe‑t‑il un forum communautaire où je peux obtenir de l’aide avec Aspose.Tasks ?
Oui, vous pouvez consulter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir du support et participer aux discussions.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.Tasks pour Java (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}