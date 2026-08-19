---
date: 2026-02-28
description: Apprenez à obtenir la durée en minutes, jours, heures, semaines et mois
  en utilisant Aspose.Tasks pour Java. Guide détaillé avec des exemples de code.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment obtenir la durée dans différentes unités avec Aspose.Tasks
url: /fr/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir la durée dans différentes unités avec Aspose.Tasks

## Introduction
Comprendre **comment obtenir la durée** pour les tâches est une partie essentielle de tout flux de travail de gestion de projet. Que vous ayez besoin de minutes pour un suivi précis ou de mois pour une planification de haut niveau, Aspose.Tasks for Java rend la conversion simple. Dans ce tutoriel, nous vous guiderons pour récupérer la durée d’une tâche en minutes, jours, heures, semaines et mois, tout en expliquant pourquoi chaque unité peut être utile dans des projets réels.

## Quick Answers
- **Que signifie « how to get duration » ?** C’est le processus d’extraction de la période d’une tâche et de la conversion dans l’unité dont vous avez besoin.  
- **Quelle méthode API effectue la conversion ?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise en production.  
- **Puis‑je convertir vers des unités personnalisées ?** Vous pouvez enchaîner les conversions ou utiliser `TimeSpan` pour des calculs personnalisés.  
- **Le code est‑il compatible avec Java 17 ?** Oui, Aspose.Tasks prend en charge Java 8 et les versions ultérieures.

## What is “how to get duration” in Aspose.Tasks?
Aspose.Tasks stocke la durée d’une tâche sous forme d’un objet `Duration`. En appelant la méthode `convert` et en spécifiant un `TimeUnitType` (Minute, Hour, Day, Week, Month), vous pouvez récupérer la même valeur sous‑jacente exprimée dans l’unité souhaitée. Cette flexibilité vous permet de générer des rapports, d’effectuer des calculs ou d’alimenter d’autres systèmes sans faire de mathématiques manuelles.

## Why use Aspose.Tasks for duration conversion?
- **Précision :** Gère automatiquement les exceptions de calendrier, le temps de travail et les calendriers non standard.  
- **Performance :** La conversion en une seule ligne évite les boucles ou le parsing personnalisé.  
- **Portabilité :** Fonctionne de la même manière sur les environnements Windows, Linux et macOS.  
- **Intégration :** S’intègre parfaitement aux applications Java existantes qui utilisent déjà Aspose.Tasks.

## Prerequisites
Before we dive into the code, make sure you have:

- Java Development Kit (JDK) installed
- Aspose.Tasks for Java library. You can download it [here](https://releases.aspose.com/tasks/java/)
- A basic understanding of Java programming

## Import Packages
In your Java project, include the Aspose.Tasks library. Add the following import statement at the beginning of your code:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
Create a new Java project in your favorite IDE (IntelliJ, Eclipse, VS Code, etc.) and add the Aspose.Tasks JAR to the project’s classpath. This ensures the classes above are available at compile time.

## Step 2: Read Project Template
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Remplacez `"Your Document Directory"` par le dossier réel contenant votre fichier de projet `.xml` ou `.mpp`.

## Step 3: Retrieve a Task
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

L’appel `getById(1)` récupère la tâche dont l’ID est 1. Ajustez l’ID pour cibler une autre tâche dans votre fichier.

## Step 4: Duration in Minutes – How to get duration in minutes?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

La variable `mins` contient maintenant la durée de la tâche exprimée en minutes.

## Step 5: Duration in Days – How to get duration in days?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Utilisez cette valeur lorsque vous avez besoin d’une granularité au jour près pour les rapports ou l’allocation des ressources.

## Step 6: Duration in Hours – How to get duration in hours?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Les heures sont pratiques pour les feuilles de temps ou lorsque vous souhaitez décomposer une journée en équipes de travail.

## Step 7: Duration in Weeks – How to get duration in weeks?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Les semaines sont souvent utilisées dans les diagrammes de Gantt de haut niveau ou la planification des jalons.

## Step 8: Duration in Months – How to get duration in months?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Les durées au niveau du mois aident lorsque vous alignez les phases du projet avec les périodes fiscales.

## Common Issues and Solutions
| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| `NullPointerException` on `task` | ID de tâche incorrect ou enfants manquants | Vérifiez que l’ID de la tâche existe en utilisant `project.getRootTask().getChildren()` |
| Valeurs inattendues (p. ex., 0) | Le projet utilise un calendrier personnalisé avec des jours non travaillés | Assurez‑vous que le calendrier du projet est correctement défini ou utilisez `project.getCalendar()` pour l’inspecter |
| La conversion renvoie des semaines fractionnaires | Les semaines sont calculées en fonction de la durée de semaine par défaut du projet (généralement 5 jours) | Multipliez par 5 si vous avez besoin de semaines calendaires, ou ajustez les paramètres du calendrier |

## Frequently Asked Questions
### Q: Puis‑je utiliser Aspose.Tasks for Java avec n’importe quel IDE Java?
A: Oui, Aspose.Tasks for Java est compatible avec tout environnement de développement intégré (IDE) Java.

### Q: Comment puis‑je obtenir l’ID d’une tâche dans un fichier Microsoft Project?
A: Vous pouvez inspecter le fichier de projet manuellement ou appeler `project.getRootTask().getChildren()` et parcourir la collection pour lire l’`ID` de chaque tâche.

### Q: Aspose.Tasks convient‑il à la gestion de projets à grande échelle?
A: Absolument. Aspose.Tasks est conçu pour traiter efficacement des projets contenant des milliers de tâches et de ressources.

### Q: Où puis‑je trouver une documentation supplémentaire?
A: Consultez la [documentation](https://reference.aspose.com/tasks/java/) pour des références d’API complètes, des exemples de code et des guides de bonnes pratiques.

### Q: Puis‑je essayer Aspose.Tasks for Java avant d’acheter?
A: Oui, vous pouvez explorer un [essai gratuit](https://releases.aspose.com/) pour évaluer ses capacités.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}