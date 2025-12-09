---
date: 2025-12-03
description: Apprenez à créer un calendrier en Java avec Aspose.Tasks. Ce guide étape
  par étape vous montre comment créer un calendrier MS Project standard, ajouter un
  calendrier standard et utiliser efficacement Aspose.Tasks.
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment créer un calendrier – Créer un calendrier standard dans Aspose.Tasks
url: /fr/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un calendrier – Créer un calendrier standard dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer des objets calendrier** pour les fichiers Microsoft Project en utilisant la bibliothèque Aspose.Tasks for Java. Nous parcourrons la création d’un calendrier MS Project standard, la définition de celui‑ci comme calendrier par défaut (standard), et l’enregistrement du fichier projet. À la fin du guide, vous serez capable d’intégrer la création de calendriers dans n’importe quelle solution de gestion de projet basée sur Java.

## Réponses rapides
- **Que signifie « calendrier standard » ?** C’est la définition du temps de travail par défaut utilisée par les tâches qui ne spécifient pas de calendrier personnalisé.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (la partie « comment utiliser Aspose »).  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quel format de fichier est produit ?** Un fichier Microsoft Project basé sur XML (`.xml`).  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour un calendrier de base.

## Qu’est‑ce qu’un calendrier standard dans Microsoft Project ?
Un **calendrier standard** définit les jours et heures de travail par défaut pour un projet. Lorsque vous ajoutez un calendrier standard, toutes les tâches qui n’ont pas de calendrier spécifique assigné suivront son planning.

## Pourquoi utiliser Aspose.Tasks pour créer un calendrier ?
Aspose.Tasks fournit une API pure Java qui vous permet de manipuler les fichiers Project sans avoir besoin de Microsoft Project installé. Cela le rend idéal pour l’automatisation côté serveur, les pipelines CI, ou toute application Java qui doit **créer des objets calendrier MS Project** de façon programmatique.

## Prérequis
Avant de commencer, assurez‑vous que les éléments suivants sont en place :

### Installation du Java Development Kit (JDK)
Installez le dernier JDK depuis le site d’Oracle ou une distribution OpenJDK.

### Bibliothèque Aspose.Tasks for Java
Téléchargez la bibliothèque depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/). Ajoutez le JAR à votre classpath de projet.

## Importer les packages
Nous n’avons besoin que d’une seule importation pour ce tutoriel :

```java
import com.aspose.tasks.*;
```

## Guide étape par étape

### Étape 1 : Configurer le répertoire de données
Définissez où le fichier projet généré sera enregistré.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu sur votre machine (par ex., `C:/Projects/Output/`).

### Étape 2 : Créer une instance de projet
Instanciez un nouvel objet Project vide qui contiendra le calendrier.

```java
Project project = new Project();
```

### Étape 3 : Définir et rendre le calendrier standard
Ajoutez un nouveau calendrier nommé **« My Cal »** et promouvez‑le en tant que calendrier standard du projet.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Astuce :** La méthode `makeStandardCalendar` marque automatiquement le calendrier fourni comme défaut pour le projet, ce qui correspond exactement à ce dont vous avez besoin lorsque vous voulez **ajouter la fonctionnalité de calendrier standard**.

### Étape 4 : Enregistrer le projet
Persistez le projet (y compris le nouveau calendrier) dans un fichier XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Vous pouvez changer le nom du fichier ou le format (`SaveFileFormat.Pp`) si vous préférez une version différente de Project.

### Étape 5 : Afficher le message de fin
Donnez‑vous un indice visuel que le processus s’est terminé sans erreurs.

```java
System.out.println("Process completed Successfully");
```

## Problèmes courants & solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier introuvable** | `dataDir` pointe vers un dossier inexistant | Créez le dossier ou utilisez un chemin absolu |
| **Exception de licence** | Exécution sans licence Aspose.Tasks valide en production | Appliquez un fichier de licence via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Calendrier vide** | Oubli d’ajouter les définitions de temps de travail | Utilisez `cal1.getWeekDays().add(WeekDay.DayType.Monday)` etc., si vous avez besoin d’heures personnalisées |

## Questions fréquentes

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Microsoft Project ?**  
R : Oui, Aspose.Tasks prend en charge une large gamme de versions de Microsoft Project, de 2000 aux dernières versions.

**Q : Puis‑je personnaliser davantage les paramètres du calendrier ?**  
R : Absolument ! Vous pouvez modifier les jours ouvrés, ajouter des exceptions et définir des heures de travail spécifiques à l’aide des classes `WeekDay` et `WorkingTime`.

**Q : Aspose.Tasks convient‑il aux applications d’entreprise ?**  
R : Certainement. La bibliothèque est conçue pour des environnements haute performance et évolutifs et offre un support complet pour les gros fichiers Project.

**Q : Aspose.Tasks propose‑t‑il un support technique pour les développeurs ?**  
R : Oui, Aspose fournit des forums dédiés, un support par tickets et une documentation exhaustive pour vous aider à résoudre rapidement tout problème.

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Oui, vous pouvez explorer une version d’essai gratuite disponible sur le [site web](https://purchase.aspose.com/buy), vous permettant d’évaluer toutes les fonctionnalités avant de vous engager.

## Conclusion
Vous savez maintenant **comment créer des objets calendrier** dans Aspose.Tasks for Java, les définir comme calendrier standard, et enregistrer le fichier Project résultant. Cette capacité vous permet d’automatiser la planification de projet, d’imposer des heures de travail cohérentes et d’intégrer les données Microsoft Project directement dans vos applications Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-03  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

---