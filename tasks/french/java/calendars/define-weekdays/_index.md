---
date: 2025-12-02
description: Apprenez à définir le calendrier, à spécifier les jours de la semaine
  dans MS Project et à configurer des jours ouvrés personnalisés à l’aide d’Aspose.Tasks
  pour Java. Enregistrez le projet au format XML en quelques lignes de code.
language: fr
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment définir le calendrier et les jours de la semaine dans MS Project avec
  Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le calendrier et les jours de la semaine dans MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment définir les paramètres du calendrier** de manière programmatique et comment définir les jours de la semaine dans un fichier Microsoft Project à l'aide de la bibliothèque Aspose.Tasks pour Java. Que vous ayez besoin de créer une semaine de travail standard, d'ajouter des jours ouvrables le week‑end ou de configurer un horaire court le vendredi, ce guide vous accompagne pas à pas — de la création du projet à l'enregistrement du fichier au format XML.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Tasks pour Java  
- **Puis‑je ajouter des jours ouvrables le week‑end ?** Oui – il suffit d’ajouter le samedi et le dimanche comme jours ouvrables.  
- **Comment enregistrer le projet ?** Utilisez `prj.save(..., SaveFileFormat.Xml)`.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite suffit pour l’évaluation ; une licence est requise en production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.

## Qu’entend‑on par « comment définir le calendrier » dans le contexte de MS Project ?
Définir un calendrier dans MS Project consiste à spécifier quels jours sont ouvrables, les heures de travail quotidiennes et les exceptions éventuelles comme les jours fériés. Ce calendrier pilote la planification des tâches, l’allocation des ressources et les échéanciers globaux du projet.

## Pourquoi utiliser Aspose.Tasks pour la manipulation du calendrier ?
- **Contrôle total** – créez, modifiez ou supprimez des calendriers programmatique­ment sans ouvrir l’interface utilisateur.  
- **Multi‑plateforme** – fonctionne sur tout OS supportant Java.  
- **Prise en charge de tous les formats** – MPP, MPT et XML, vous pouvez ainsi *enregistrer le projet au format XML* pour une intégration facile avec d’autres systèmes.  
- **Aucune dépendance COM** – contrairement à la bibliothèque Microsoft Project Interop.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK) 8+** – téléchargez‑le depuis le [site d’Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks pour Java** – obtenez le JAR le plus récent sur la [page de téléchargement d’Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Un IDE ou un outil de construction (Maven/Gradle) pour ajouter le JAR Aspose.Tasks à votre classpath.

## Importer les packages
Tout d’abord, importez les classes dont vous aurez besoin. Ces imports vous donnent accès aux objets projet, calendrier et temps de travail.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guide étape par étape

### Étape 1 : Créer une instance de projet
Créez un nouvel objet `Project`. Cet objet représente le fichier MS Project que vous allez modifier.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Étape 2 : Définir un nouveau calendrier
Ajoutez un nouveau calendrier au projet. Lui donner un nom clair est utile lorsqu’il y a plusieurs calendriers.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Étape 3 : Ajouter les jours ouvrables standards (lundi‑jeudi)
Utilisez l’assistant intégré `WeekDay.createDefaultWorkingDay` pour définir l’horaire par défaut de 9 h à 17 h pour la semaine de travail principale.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Étape 4 : Ajouter des jours ouvrables le week‑end
Si votre projet fonctionne le week‑end, ajoutez simplement le samedi et le dimanche comme jours ouvrables réguliers. Cela illustre **l’ajout de jours ouvrables le week‑end**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Étape 5 : Définir un jour de travail court personnalisé (vendredi)
Ici, nous **définissons des jours ouvrables personnalisés** pour le vendredi : une première plage (9 h‑12 h) et une seconde (13 h‑16 h).

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Étape 6 : Enregistrer le projet au format XML
Enfin, persistez les modifications. L’option `SaveFileFormat.Xml` vous permet de **enregistrer le projet au format XML**, ce qui est pratique pour l’intégration avec d’autres outils.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Les heures de travail ne sont pas appliquées** | Assurez‑vous d’appeler `setDayWorking(true)` sur le `WeekDay` personnalisé. |
| **Fichier introuvable lors de l’enregistrement** | Vérifiez que `dataDir` pointe vers un dossier existant et que votre application dispose des droits d’écriture. |
| **Le calendrier n’est pas reflété dans les tâches** | Assignez le nouveau calendrier aux ressources ou aux tâches avec `task.setCalendar(cal)`. |

## Questions fréquentes

**Q : Puis‑je définir des jours non ouvrables personnalisés avec Aspose.Tasks pour Java ?**  
R : Oui. Réglez la propriété `DayWorking` sur `false` pour tout `WeekDay` que vous souhaitez marquer comme non ouvrable.

**Q : Comment ajouter des jours fériés ou des exceptions d’entreprise ?**  
R : Créez des objets `CalendarException`, spécifiez les dates d’exception, puis ajoutez‑les à `cal.getExceptions()`.

**Q : La bibliothèque est‑elle compatible avec les anciennes versions de MS Project ?**  
R : Absolument. Aspose.Tasks prend en charge les formats MPP, MPT et XML sur de multiples versions de Project.

**Q : Puis‑je modifier un calendrier existant dans un projet importé ?**  
R : Chargez le projet avec `new Project("existing.mpp")`, récupérez le calendrier souhaité, effectuez les modifications, puis enregistrez.

**Q : Aspose.Tasks gère‑t‑il également les tâches récurrentes ?**  
R : Oui, vous pouvez créer et modifier des tâches récurrentes à l’aide de la classe `RecurringTask`.

## Conclusion
Vous savez maintenant **comment définir les paramètres du calendrier**, **définir les jours de la semaine dans MS Project**, ajouter des jours ouvrables le week‑end et créer un horaire court le vendredi — le tout avec Aspose.Tasks pour Java. Enregistrez le résultat au format XML et intégrez la logique du calendrier dans toute solution de gestion de projet basée sur Java.

---

**Dernière mise à jour :** 2025-12-02  
**Testé avec :** Aspose.Tasks pour Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}