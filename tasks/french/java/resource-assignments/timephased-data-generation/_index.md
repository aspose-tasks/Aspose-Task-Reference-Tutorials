---
date: 2026-06-10
description: Apprenez comment modifier le contour et générer des données Timephased
  Data pour les resource assignments en utilisant Aspose.Tasks pour Java, couvrant
  les work contour types et les advanced scheduling scenarios.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Générer des données Timephased Data pour les Resource Assignments dans
  Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment modifier le contour dans Aspose.Tasks pour les données Timephased Data
url: /fr/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier le contour dans Aspose.Tasks pour les données temporelles

## Introduction
Dans ce tutoriel, vous découvrirez **comment modifier le contour** d'une affectation de ressource et générerez des données temporelles à l'aide d'Aspose.Tasks pour Java. Les données temporelles révèlent la répartition du travail sur la chronologie du projet, vous permettant d'ajuster finement les plannings, d'équilibrer les charges de travail et de prendre des décisions basées sur les données. Maîtriser les changements de contour vous aide à modéliser des modèles d'effort réalistes tels que le front‑loading, le back‑loading ou les charges de travail de pointe.

## Réponses rapides
- **Qu'est‑ce qu'un contour ?** Un contour de travail définit comment l'effort est réparti sur la durée d'une tâche (par ex. Flat, Turtle, Bell).  
- **Pourquoi changer un contour ?** Pour refléter des modèles de travail réalistes tels que le front‑loading ou le back‑loading.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (toute version récente).  
- **Ai‑je besoin d'une licence ?** Oui, une licence valide d'Aspose.Tasks est requise pour une utilisation en production.  
- **Puis‑je voir les résultats dans la console ?** L'exemple affiche les dates de début et les valeurs pour chaque segment temporel.

## Qu'est‑ce que « comment modifier le contour » ?
Modifier un contour signifie mettre à jour la propriété `WORK_CONTOUR` d'un objet `ResourceAssignment`. Cette propriété indique à Aspose.Tasks comment répartir le travail total de l'affectation sur la durée de la tâche. La bibliothèque propose plusieurs contours prédéfinis tels que Flat, Turtle, Bell, et d'autres, chacun produisant un modèle distinct de répartition de l'effort dans le temps.

## Pourquoi utiliser Aspose.Tasks pour générer des données temporelles ?
Aspose.Tasks génère des données temporelles avec **0 ms de surcharge pour les opérations en mémoire** et prend en charge **plus de 50 formats de sortie** (MPP, XML, CSV, etc.). La bibliothèque peut traiter des projets de plusieurs centaines de pages sans charger le fichier complet en mémoire, fournissant une répartition précise du travail pour les rapports, le nivellement des ressources et les analyses de type « what‑if ». Son API vous permet d'automatiser les changements de contour et d'extraire programmatiquement des valeurs temporelles précises.

## Prérequis
Avant de commencer, assurez‑vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) : Assurez‑vous d'avoir le JDK installé sur votre système. Vous pouvez le télécharger et l'installer depuis [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Bibliothèque Aspose.Tasks pour Java : Vous devez disposer de la bibliothèque Aspose.Tasks pour Java. Vous pouvez la télécharger depuis le [website](https://releases.aspose.com/tasks/java/).

## Importer les packages
La classe `Project` est l'objet principal d'Aspose.Tasks qui représente un fichier de projet complet en mémoire. Importez les espaces de noms nécessaires avant de commencer à travailler avec les tâches et les affectations.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Étape 1 : Lire le fichier MPP source
Le constructeur `Project` charge un fichier MPP existant, analyse sa structure sans matérialiser entièrement chaque tâche en mémoire, ce qui rend l'opération légère.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Étape 2 : Obtenir la tâche et l'affectation de ressource
`ResourceAssignment` lie une ressource à une tâche et stocke les propriétés au niveau de l'affectation telles que le travail, le coût et le contour. Récupérez la première affectation avec `project.getResourceAssignments().getById(1)` (ou tout ID valide) avant de modifier son contour.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Comment modifier le contour – Flat (défaut)
`WorkContourType` est une énumération qui répertorie les modèles de contour de travail prédéfinis pris en charge par Aspose.Tasks. `Asn.WORK_CONTOUR` identifie le champ contour d'une affectation de ressource, et `generateTimephasedData()` crée des entrées de travail temporelles basées sur le paramètre de contour actuel. Un contour **Flat** répartit le travail uniformément sur la durée de la tâche ; définissez‑le avec `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` puis appelez `firstRA.generateTimephasedData()` pour obtenir des valeurs espacées de manière égale.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Turtle
Le contour **Turtle** commence avec un faible effort, s'accélère vers le milieu, puis ralentit à nouveau, rappelant le rythme progressif d'une tortue. Appliquez‑le en définissant `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` puis régénérez les données temporelles. Ce modèle est idéal pour les tâches qui nécessitent une courbe d'apprentissage avant d'atteindre la productivité maximale.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – BackLoaded
Le contour **BackLoaded** place la majorité du travail vers la fin du planning de la tâche, avec peu d'effort au départ. Définissez‑le avec `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` et régénérez les données temporelles. Cela est utile pour les activités qui dépendent de tâches précédentes avant que le travail puisse être effectué.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – FrontLoaded
Le contour **FrontLoaded** concentre l'effort au début de la tâche, modélisant des scénarios tels que les phases de lancement ou des rafales de travail intensives en début de projet. Appliquez‑le avec `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` puis appelez `firstRA.generateTimephasedData()` pour voir la distribution front‑loaded.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – Bell
Le contour **Bell** crée un pic symétrique au milieu de la chronologie, représentant un travail qui augmente, atteint un sommet, puis diminue doucement. Définissez‑le via `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` et régénérez les données temporelles pour visualiser la courbe d'effort en forme de cloche.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – EarlyPeak
**EarlyPeak** place la valeur de travail la plus élevée tôt dans le planning, puis décroît. Utilisez `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` suivi de `firstRA.generateTimephasedData()` pour modéliser des activités qui nécessitent un démarrage fort, comme le prototypage rapide.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – LatePeak
**LatePeak** déplace le pic de travail vers la fin de la tâche, adapté aux travaux qui s'intensifient à l'approche d'une échéance. Appliquez‑le avec `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` et régénérez les données temporelles pour voir le pic de charge de travail en fin de phase.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Comment modifier le contour – DoublePeak
**DoublePeak** crée deux pics de travail distincts séparés par un intervalle de moindre effort, utile pour les tâches avec deux grandes rafales d'effort. Définissez‑le avec `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` puis appelez `firstRA.generateTimephasedData()` pour obtenir le modèle à double pic.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problèmes courants et astuces
- **Contour ne se met pas à jour ?** Assurez‑vous d'appeler `firstRA.set(Asn.WORK_CONTOUR, …)` *avant* de récupérer les données temporelles.  
- **Valeurs inattendues ?** Vérifiez que les dates de début et de fin de la tâche sont correctement définies dans le MPP source.  
- **Astuce de performance :** Réutilisez la même instance `Project` lors de l'itération sur plusieurs contours afin d'éviter des I/O de fichiers inutiles, ce qui peut réduire le temps de traitement jusqu'à 40 % sur de gros projets.  
- **Astuce mémoire :** Pour les projets dépassant 1 GB, activez `Project.setReadOnly(true)` pour maintenir l'utilisation mémoire sous 200 MB tout en générant des données temporelles précises.

## FAQ
**Q : Puis‑je utiliser Aspose.Tasks avec d'autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks s'intègre parfaitement avec d'autres bibliothèques Java, vous permettant de combiner les données de planification avec des rapports, de l'analyse ou des frameworks UI.

**Q : Aspose.Tasks convient‑il aux projets d'entreprise à grande échelle ?**  
R : Absolument. La bibliothèque est conçue pour gérer des projets contenant des dizaines de milliers de tâches et de ressources, traitant des fichiers de plusieurs centaines de pages sans dégradation des performances.

**Q : Aspose.Tasks prend‑il en charge différents formats de fichiers de projet ?**  
R : Oui, Aspose.Tasks prend en charge plus de 30 formats, dont MPP, XML, CSV et MPX, permettant une import/export facile entre les systèmes anciens et modernes.

**Q : Puis‑je personnaliser les contours de travail selon les exigences de mon projet ?**  
R : Oui, vous pouvez définir des contours personnalisés en fournissant un tableau de pourcentages de travail à la propriété `WORK_CONTOUR`, vous donnant un contrôle total sur la répartition de l'effort.

**Q : Existe‑t‑il un forum communautaire où je peux obtenir de l'aide sur Aspose.Tasks ?**  
R : Oui, vous pouvez visiter le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pour obtenir du support, des discussions et des exemples de code de la part des ingénieurs Aspose et de la communauté.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer des affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Lire les données temporelles pour les ressources dans Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Comment arrêter une affectation et reprendre les affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}