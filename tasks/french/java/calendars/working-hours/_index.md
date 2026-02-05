---
date: 2026-02-05
description: Apprenez à déterminer les jours ouvrables et à calculer la durée des
  tâches en extrayant les heures de travail des calendriers MS Project à l’aide d’Aspose.Tasks
  pour Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks
url: /fr/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks

## Introduction
Gestion des calendriers de projet est une partie essentielle d’une planification de projet réussie. Dans ce tutoriel, vous allez **déterminer les jours ouvrés** pour n’importe quelle tâche et **extraire les heures de travail** d’un calendrier MS Project en utilisant Aspose.Tasks for Java. À la fin du guide, vous serez capable de **calculer la durée des tâches**, de personnaliser les heures de travail et de **charger un fichier MPP** de manière fiable pour récupérer les données dont vous avez besoin. Vous verrez également comment **lire les fichiers MS Project** sans avoir Microsoft Project installé, rendant l’automatisation possible sur n’importe quelle plateforme.

## Réponses rapides
- **What does “determine working days” mean?** It means identifying which calendar dates are considered work‑days for a given task.  
- **Which library should I use?** Aspose.Tasks for Java provides a full‑featured API for working with MS Project files.  
- **How long does the implementation take?** Typically 10–15 minutes for a basic extraction.  
- **Do I need a license?** A free trial is available; a commercial license is required for production use.  
- **Can I customize working hours?** Yes – you can modify calendars, add holidays, and set custom work‑time ranges.  

## Qu’est‑ce que « déterminer les jours ouvrés » ?
Lorsque une tâche est planifiée, le calendrier du projet définit quels jours sont des jours ouvrés et quels jours sont non ouvrés (week‑ends, jours fériés). Déterminer les jours ouvrés signifie interroger ce calendrier pour savoir exactement quand le travail peut avoir lieu, ce qui est essentiel pour des calculs précis de **calculate task duration**.

## Pourquoi utiliser Aspose.Tasks pour récupérer les heures de travail ?
- **No Microsoft Project required** – you can read MS Project files directly from Java code.  
- **Full calendar support** – includes default, resource, and task calendars.  
- **High performance** – process large projects quickly.  
- **Extensive documentation** – examples and API reference are readily available.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – download the latest JAR from [here](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base en programmation Java.  

## Importer les packages
Tout d’abord, importez l’espace de noms principal d’Aspose.Tasks :

```java
import com.aspose.tasks.*;
```

## Comment charger un fichier MPP avec Aspose.Tasks ?
Le chargement du fichier projet est la première étape pour toute analyse de calendrier. L’API vous permet de **load an MPP file** en une seule ligne de code, sans besoin de l’interface MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Récupérer les informations de tâche et de calendrier
Sélectionnez la tâche que vous souhaitez analyser et obtenez son calendrier associé. C’est ici que nous **retrieve working hours** pour la tâche :

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Définir les dates de début et de fin
Configurez la fenêtre temporelle pour laquelle vous voulez **determine working days**. Utiliser les dates de début et de fin de la tâche garantit que vous n’évaluez que la période pertinente.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Parcourir les dates
Bouclez sur chaque date de la durée de la tâche. Cette boucle nous aidera à **customize working hours** plus tard si nécessaire :

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculer la durée
Lors de l’itération, nous vérifions si chaque jour est un jour ouvré, additionnons les heures de travail, puis calculons finalement la durée de la tâche en minutes, heures et jours. Cette étape montre comment **calculate working days** et **calculate task duration** de façon programmatique.

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Comment personnaliser les heures de travail et les jours fériés
Aspose.Tasks vous permet de modifier les plages de temps de travail du calendrier et d’ajouter des exceptions telles que les jours fériés. Vous pouvez appeler `taskCalendar.addWorkingTime()` ou `taskCalendar.addException()` pour adapter le planning aux politiques de votre organisation. Ceci est utile lorsque le planning par défaut 9‑5 ne correspond pas à la réalité.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La tâche renvoie `null` pour le calendrier** | Assurez‑vous que la tâche possède réellement un calendrier assigné ; sinon elle hérite du calendrier par défaut du projet. |
| **Durée incorrecte à cause des jours fériés** | Vérifiez que les jours fériés sont définis dans le calendrier de la tâche ou dans le calendrier de base du projet. |
| **Incohérence de fuseau horaire** | Utilisez `java.util.TimeZone` pour aligner le fuseau horaire du calendrier avec celui de votre système si nécessaire. |

## Questions fréquemment posées
### Q: Can Aspose.Tasks for Java handle complex project structures?
R: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
R: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
R: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
R: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
R: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

## Conclusion
Dans ce guide, nous avons démontré comment **determine working days**, **retrieve working hours**, et **calculate task duration** à partir d’un calendrier MS Project en utilisant Aspose.Tasks for Java. En suivant les étapes ci‑dessus, vous pouvez automatiser l’analyse des plannings, personnaliser les calendriers et garder vos plans de projet précis et à jour. Vous disposez désormais des outils pour **read MS Project** data, **load an MPP file**, et effectuer des calculs de durée précis sans besoin de Microsoft Project.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}