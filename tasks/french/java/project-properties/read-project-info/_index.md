---
date: 2025-12-31
description: Apprenez à lire les informations du projet, y compris le planning depuis
  le départ, en utilisant Aspose.Tasks pour Java. Découvrez comment extraire rapidement
  les propriétés du projet en Java.
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment lire les informations de projet à partir de Microsoft Project avec
  Aspose.Tasks pour Java
url: /fr/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire les informations de projet à partir de Microsoft Project avec Aspose.Tasks pour Java

## Introduction
Si vous avez besoin de **how to read project** des détails tels que les dates de début, les dates de fin ou les paramètres du calendrier directement à partir d'un fichier Microsoft Project, Aspose.Tasks pour Java vous offre une approche propre, axée sur le code. Dans ce tutoriel, vous verrez exactement **how to read project** les métadonnées, comprendre le **project schedule from start**, et apprendre à extraire d'autres propriétés clés — le tout en quelques lignes de code Java.

## Quick Answers
- **What does Aspose.Tasks for Java do?** Il permet l'accès programmatique aux fichiers Microsoft Project (MPP, XML, etc.) sans nécessiter l'installation de Microsoft Project.  
- **Which property tells if the schedule is based on start?** `Prj.SCHEDULE_FROM_START` – true signifie que le planning est basé sur le début, false signifie qu'il est basé sur la fin.  
- **Can I extract project properties in Java?** Oui, vous pouvez lire la date de début, la date de fin, la date actuelle, la date d'état et le nom du calendrier.  
- **Do I need a license for development?** Une licence temporaire gratuite suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **What Java version is required?** Java 8 ou supérieur avec le JAR Aspose.Tasks sur le classpath.

## Prerequisites
Avant de commencer, assurez-vous d'avoir :

1. **Environnement de développement Java** – JDK 8 ou plus récent installé et configuré.  
2. **Aspose.Tasks pour Java** – Téléchargez la dernière bibliothèque depuis le [website](https://releases.aspose.com/tasks/java/).  

## Import Packages
Pour interagir avec les fichiers de projet, importez l'espace de noms principal d'Aspose.Tasks :

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
Définissez le dossier contenant votre fichier `.mpp`. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Créez une instance `Project` en chargeant le fichier Microsoft Project que vous souhaitez inspecter.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### Step 3: Determine the Project Schedule Basis
Vérifiez si le planning est calculé à partir de la date de début du projet ou de la date de fin. C’est le cœur de **how to read project** les informations de planification.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **Pro tip:** `Prj.SCHEDULE_FROM_START` renvoie un booléen ; `true` signifie *project schedule from start*.

### Step 4: Retrieve Additional Project Schedule Information
Au-delà des dates de début/fin, vous avez souvent besoin de la date actuelle, de la date d'état et du calendrier associé au projet. Cela montre **read project properties java** en action.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## Common Issues & Solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| `NullPointerException` sur `project.get(Prj.CALENDAR)` | Le fichier projet ne possède pas de calendrier par défaut. | Assurez-vous que le fichier MPP définit un calendrier ou gérez les vérifications de `null`. |
| Dates affichées comme `null` | Fichier projet corrompu ou champs de date manquants. | Validez le fichier source dans Microsoft Project avant le traitement. |
| Erreur de compilation : `cannot find symbol Prj` | Le JAR Aspose.Tasks n'est pas sur le classpath. | Ajoutez `aspose-tasks-xx.jar` au chemin de construction de votre projet. |

## Frequently Asked Questions

### Q : Puis‑je utiliser Aspose.Tasks pour Java avec n'importe quelle version de fichiers Microsoft Project ?
R : Oui, Aspose.Tasks pour Java prend en charge diverses versions de fichiers Microsoft Project, y compris les formats MPP et XML.

### Q : Aspose.Tasks pour Java est‑il compatible avec tous les environnements de développement Java ?
R : Aspose.Tasks pour Java est compatible avec la plupart des environnements de développement Java, garantissant une flexibilité d'intégration.

### Q : Aspose.Tasks pour Java offre‑t‑il un support pour la manipulation des données de projet au‑delà de la lecture d'informations ?
R : Absolument, Aspose.Tasks pour Java propose de nombreuses fonctionnalités pour manipuler les données de projet, y compris l'édition, la sauvegarde et l'exportation.

### Q : Puis‑je automatiser l'extraction d'informations de projet en utilisant Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks pour Java permet l'automatisation via son API complète, facilitant les processus d'extraction et d'analyse des données.

### Q : Existe‑t‑il un forum communautaire ou un canal de support disponible pour les utilisateurs d'Aspose.Tasks pour Java ?
R : Oui, vous pouvez trouver des ressources utiles et interagir avec la communauté sur le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q : Comment lire les propriétés du projet en Java sans charger l'arbre complet des tâches ?
R : Utilisez la méthode `Project.get` avec les valeurs d'énumération `Prj` requises ; cela ne récupère que les métadonnées demandées, limitant l'utilisation de la mémoire.

### Q : Quelle est la meilleure façon de gérer de gros fichiers MPP lors de l'extraction des propriétés ?
R : Chargez le projet en mode *lecture‑seule* (`new Project(filePath, LoadOptions)`) et interrogez uniquement les propriétés nécessaires afin d'éviter une consommation élevée de mémoire.

## Conclusion
En suivant ce guide, vous savez maintenant **how to read project** les informations telles que l'origine du planning, les dates et les détails du calendrier en utilisant Aspose.Tasks pour Java. Intégrer ces extraits de code dans vos applications permet de générer des rapports automatisés, des tableaux de bord personnalisés et de prendre des décisions plus intelligentes sans interaction manuelle avec Microsoft Project.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}