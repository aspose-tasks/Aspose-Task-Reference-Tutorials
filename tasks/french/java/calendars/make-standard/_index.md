---
date: 2026-08-13
description: Apprenez à créer un calendrier standard MS Project en Java avec Aspose.Tasks.
  Ce guide étape par étape vous montre comment créer un calendrier standard MS Project,
  le définir comme défaut et enregistrer le fichier.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Créer un calendrier standard dans Aspose.Tasks
og_description: Comment créer un calendrier en Java avec Aspose.Tasks. Apprenez à
  créer un calendrier standard MS Project, le définir comme défaut et enregistrer
  le fichier de projet en quelques minutes.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Comment créer un calendrier – créer un calendrier standard dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Comment créer un calendrier – créer un calendrier standard dans Aspose.Tasks
url: /fr/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un calendrier – créer un calendrier standard avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer des objets calendrier** pour les fichiers Microsoft Project en utilisant la bibliothèque Aspose.Tasks for Java. Nous parcourrons la création d’un calendrier standard MS Project, sa définition comme calendrier par défaut (standard), et l’enregistrement du fichier projet. À la fin du guide, vous pourrez intégrer la création de calendriers dans toute solution de gestion de projet basée sur Java.

## Réponses rapides
- **Que signifie « calendrier standard » ?** C’est la définition du temps de travail par défaut appliquée aux tâches qui n’ont pas de calendrier personnalisé assigné.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java – une API pure Java qui fonctionne sans Microsoft Project installé.  
- **Ai-je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour les déploiements en production.  
- **Quel format de fichier est produit ?** Un fichier Microsoft Project basé sur XML (`.xml`).  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour une configuration de calendrier basique.

## Qu’est‑ce qu’un calendrier standard dans Microsoft Project ?
Un calendrier standard définit les jours et heures de travail par défaut pour un projet, généralement du lundi au vendredi, de 8 h à 17 h. Lorsque vous ajoutez un calendrier standard, toute tâche qui n’a pas de calendrier personnalisé hérite de ces heures de travail, assurant une planification cohérente à travers le projet.

## Pourquoi utiliser Aspose.Tasks pour créer un calendrier ?
Aspose.Tasks for Java prend en charge **plus de 50 formats d’entrée et de sortie** et peut traiter des projets contenant jusqu’à **10 000 tâches** sans charger le fichier complet en mémoire. Cette bibliothèque pure Java vous permet d’automatiser la création de fichiers Project sur des serveurs, des pipelines CI ou toute application Java, éliminant ainsi le besoin d’une installation Microsoft Project sous licence.

## Prérequis

### Installation du Java Development Kit (JDK)
Installez le JDK le plus récent depuis le site d’Oracle ou une distribution OpenJDK.

### Bibliothèque Aspose.Tasks pour Java
Téléchargez la bibliothèque depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/). Ajoutez le JAR au classpath de votre projet.

## Importer les packages
Nous n’avons besoin que d’un seul import pour ce tutoriel :

```java
import com.aspose.tasks.*;
```

## Guide étape par étape

### Étape 1 : configurer le répertoire de données
Définissez l’endroit où le fichier de projet généré sera enregistré.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu sur votre machine (par ex., `C:/Projects/Output/`).

### Étape 2 : créer une instance de projet
`Project` est l’objet de haut niveau d’Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire. L’instancier vous fournit un conteneur pour les calendriers, tâches, ressources et autres données du projet.

```java
Project project = new Project();
```

### Étape 3 : définir et rendre le calendrier standard
`Calendar` est la classe qui modélise un planning de temps de travail. Ajouter un nouveau calendrier nommé **« My Cal »** et appeler `makeStandardCalendar` le promeut en tant que calendrier par défaut pour l’ensemble du projet.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Astuce :** La méthode `makeStandardCalendar` marque automatiquement le calendrier fourni comme le calendrier par défaut du projet, ce qui est exactement ce dont vous avez besoin lorsque vous souhaitez **ajouter la fonctionnalité de calendrier standard**.

### Étape 4 : enregistrer le projet
`SaveFileFormat` est une énumération qui spécifie le format de fichier à utiliser lors de l’enregistrement d’un projet.  
Persistez le projet (y compris le nouveau calendrier) dans un fichier XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Vous pouvez changer le nom du fichier ou le format (`SaveFileFormat.Pp`) si vous préférez une version différente de Project.

### Étape 5 : afficher le message de fin
Affichez un indice visuel indiquant que le processus s’est terminé sans erreur.

```java
System.out.println("Process completed Successfully");
```

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier non trouvé** | `dataDir` pointe vers un dossier inexistant | Créez le dossier ou utilisez un chemin absolu |
| **Exception de licence** | Exécution sans licence Aspose.Tasks valide en production | Appliquez un fichier de licence via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Calendrier vide** | Oubli d’ajouter les définitions d’heures de travail | Utilisez `cal1.getWeekDays().add(WeekDay.DayType.Monday)` etc., si vous avez besoin d’heures personnalisées |

## Questions fréquemment posées

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Microsoft Project ?**  
R : Oui, Aspose.Tasks prend en charge une large gamme de versions de Microsoft Project, de 2000 aux dernières versions.

**Q : Puis‑je personnaliser davantage les paramètres du calendrier ?**  
R : Absolument ! Vous pouvez modifier les jours ouvrés, ajouter des exceptions et définir des heures de travail spécifiques en utilisant les classes `WeekDay` et `WorkingTime`.

**Q : Aspose.Tasks convient‑il aux applications de niveau entreprise ?**  
R : Certainement. La bibliothèque est conçue pour des environnements haute performance et évolutifs et offre un support complet pour les gros fichiers Project.

**Q : Aspose.Tasks propose‑t‑il un support technique pour les développeurs ?**  
R : Oui, Aspose propose des forums dédiés, un support par tickets et une documentation exhaustive pour vous aider à résoudre rapidement tout problème.

**Q : Puis‑je essayer Aspose.Tasks avant d’effectuer un achat ?**  
R : Oui, vous pouvez explorer une version d’essai gratuite disponible sur le [site web](https://purchase.aspose.com/buy), vous permettant d’évaluer toutes les fonctionnalités avant de vous engager.

---

**Dernière mise à jour :** 2026-08-13  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks pour Java](/tasks/java/calendars/create/)
- [Comment définir le calendrier du projet Java avec Aspose.Tasks](/tasks/java/calendars/properties/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks pour Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}