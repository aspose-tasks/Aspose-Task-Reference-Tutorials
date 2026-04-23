---
date: 2026-02-07
description: Apprenez à définir le calendrier du projet en Java et à gérer les propriétés
  du calendrier MS Project à l’aide d’Aspose.Tasks. Guide étape par étape pour afficher
  les heures de travail du calendrier et personnaliser les plannings.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment définir le calendrier du projet Java avec Aspose.Tasks
url: /fr/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le calendrier de projet Java avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **how to set project calendar java** programmé à l'aide de la bibliothèque Aspose.Tasks pour Java. Contrôler les propriétés du calendrier vous permet de **display calendar working hours**, de définir des jours de travail personnalisés et d'aligner le planning de votre projet avec des contraintes du monde réel. Nous parcourrons chaque étape — de la configuration de l'environnement à l'itération sur les calendriers et la lecture de leurs propriétés — afin que vous puissiez gérer en toute confiance les paramètres **manage ms project calendar** dans vos applications.

## Quick Answers
- **What does “set project calendar” mean?** Cela signifie créer ou mettre à jour les heures de travail d'un calendrier, le calendrier de base et les types de jour dans un fichier MS Project.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Can I display calendar working hours?** Oui — en lisant chaque `WeekDay` vous pouvez afficher les heures pour chaque type de jour.  
- **Is this compatible with Maven/Gradle?** Absolument — ajoutez le JAR Aspose.Tasks en tant que dépendance.

## How to Set Project Calendar Java
Cette section répond directement au mot‑clé principal. Nous couvrirons les étapes exactes dont vous avez besoin pour **set project calendar java** valeurs, modifier les jours ouvrés du calendrier et calculer les heures de travail à la java‑style.

## What Is a Project Calendar?
Un calendrier de projet définit les jours ouvrés et les heures pour les tâches, les ressources et la chronologie globale du projet. Dans MS Project, les calendriers peuvent hériter d'un calendrier de base, et chaque type de jour (par ex., **Standard**, **Non‑working**) peut avoir son propre temps de travail. Gérer ces paramètres de manière programmatique permet des ajustements dynamiques du planning sans édition manuelle.

## Why Manage MS Project Calendar Programmatically?
- **Automation:** Ajuster les calendriers sur de nombreux projets avec un seul script.  
- **Consistency:** Appliquer les politiques d'heures de travail à l'échelle de l'organisation.  
- **Integration:** Synchroniser les calendriers avec des systèmes externes (RH, ERP).  
- **Visibility:** Afficher rapidement **display calendar working hours** pour les rapports ou le débogage.  
- **Flexibility:** Vous pouvez **modify calendar working days** ou ajouter des exceptions à la volée.

## Prerequisites
Before you start, make sure you have:

- **Java Development Kit (JDK) 8+** installé et `JAVA_HOME` configuré.  
- **Aspose.Tasks for Java** bibliothèque téléchargée depuis la [download page](https://releases.aspose.com/tasks/java/). Ajoutez le JAR au classpath de votre projet ou aux dépendances Maven/Gradle.

## Import Packages
Tout d'abord, importez les classes principales d'Aspose.Tasks que nous utiliserons tout au long du tutoriel :

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Définissez le dossier qui contient vos fichiers de projet. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Les temps de travail sont exprimés en millisecondes. Définir des constantes réutilisables rend le code plus lisible et vous aide à **calculate working hours java** avec précision.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Créez une instance `Project` en chargeant un fichier XML MS Project existant (`.xml` ou `.mpp`). Cela nous donne accès à tous les calendriers stockés dans le fichier.

```java
Project project = new Project(dataDir + "project.xml");
```

## Iterate Through Calendars Java
Nous parcourons maintenant chaque calendrier, affichons son identifiant unique, son nom, son calendrier de base et les heures de travail pour chaque type de jour. Cela démontre **how to set project calendar java** valeurs et aussi comment **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Le calendrier est lui‑même un calendrier de base (`isBaseCalendar()` renvoie `true`). | Utilisez la vérification ternaire comme indiqué (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | Le fichier de projet utilise une unité de temps différente (ticks). | Vérifiez le format du fichier ; Aspose.Tasks normalise en millisecondes, mais assurez‑vous de charger le bon type de fichier. |
| Unable to locate `project.xml` | Chemin `dataDir` incorrect. | Utilisez un chemin absolu ou `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Puis‑je modifier les propriétés du calendrier de manière programmatique en utilisant Aspose.Tasks ?**  
A: Oui, l'API offre un accès complet en lecture/écriture aux calendriers, vous permettant d'ajouter, modifier ou supprimer les temps de travail, les exceptions et les relations de calendrier de base.

**Q: Existe‑t‑il des limitations à la personnalisation du calendrier avec Aspose.Tasks ?**  
A: La bibliothèque reflète les capacités de Microsoft Project, vous pouvez donc personnaliser pratiquement tous les aspects du calendrier. Seules les très anciennes versions de fichiers Project peuvent présenter de légères incompatibilités.

**Q: Puis‑je intégrer la gestion du calendrier dans des projets Java existants ?**  
A: Absolument. Ajoutez simplement le JAR Aspose.Tasks à votre chemin de construction et utilisez les mêmes modèles de code présentés ici.

**Q: Aspose.Tasks prend‑il en charge d'autres fonctionnalités de gestion de projet en plus de la gestion des calendriers ?**  
A: Oui, il couvre les tâches, les ressources, les affectations, les structures, les lignes de base, et plus encore — offrant une solution complète pour l'automatisation de projets basée sur Java.

**Q: Un support technique est‑il disponible pour les développeurs utilisant Aspose.Tasks ?**  
A: Oui, Aspose propose des forums dédiés, un support par e‑mail et une documentation exhaustive pour tous les utilisateurs sous licence.

---

**Dernière mise à jour :** 2026-02-07  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}