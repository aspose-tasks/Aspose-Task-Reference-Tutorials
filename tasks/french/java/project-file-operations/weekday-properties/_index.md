---
date: 2025-12-23
description: Apprenez à utiliser Aspose.Tasks Java pour mettre à jour le planning
  du projet, définir le jour de début de la semaine, modifier le nombre de jours par
  mois et personnaliser le calendrier du projet efficacement.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Gestion des propriétés des jours de la semaine
url: /fr/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Gestion des propriétés des jours de la semaine

## Introduction
Aspose.Tasks for Java (aspose tasks java) est une API robuste qui permet aux développeurs Java de travailler avec les fichiers Microsoft Project sans avoir besoin d’installer Microsoft Project. Dans ce tutoriel, vous apprendrez comment **charger un fichier MPP**, **définir le jour de début de semaine**, **modifier le nombre de jours par mois**, et **personnaliser le calendrier du projet**—des étapes essentielles pour mettre à jour le planning d’un projet. À la fin, vous serez capable d’ajuster les propriétés des jours de la semaine par programme et d’enregistrer les modifications dans le format souhaité.

## Quick Answers
- **Quelle est la classe principale pour gérer les projets ?** `Project` de la bibliothèque Aspose.Tasks.  
- **Comment changer le jour de début de semaine ?** Utilisez `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Puis‑je charger un fichier .mpp existant ?** Oui—instanciez `Project` avec le chemin du fichier.  
- **Quelle méthode enregistre le projet en XML ?** `project.save(path, SaveFileFormat.Xml)`.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour l’évaluation ; une licence est requise en production.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir les éléments suivants :

- **Java Development Kit (JDK)** – dernière version installée.  
- **Aspose.Tasks for Java library** – téléchargez‑la [ici](https://releases.aspose.com/tasks/java/).  
- **Un IDE** tel qu’IntelliJ IDEA, Eclipse ou NetBeans.  

## Import Packages
Pour commencer, importez les classes essentielles d’Aspose.Tasks :

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Passons maintenant en revue chaque étape de la gestion des propriétés des jours de la semaine.

## Step 1: Load an MPP File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Ici nous **chargeons un fichier .mpp existant** (`load mpp file`) afin de pouvoir inspecter et modifier ses paramètres de calendrier.*

## Step 2: Display Current Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Ce code affiche le **jour de début de semaine**, le **nombre de jours par mois**, les **minutes par jour** et les **minutes par semaine**—les éléments de base que vous devrez souvent **personnaliser le calendrier du projet**.

## Step 3: Set New Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Dans cette étape, nous **définissons le jour de début de semaine** à Monday, **modifions le nombre de jours par mois** à 24, et ajustons les comptes de minutes quotidiennes et hebdomadaires. Ces réglages sont typiques lorsque vous devez **mettre à jour le planning du projet** pour correspondre à un calendrier de travail non standard.

## Step 4: Save the Updated Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Le projet modifié est enregistré au format XML, ce qui facilite le partage ou l’importation dans d’autres outils.

## Step 5: Confirm the Operation
```java
System.out.println("Process completed Successfully");
```
Un simple message console vous indique que le flux de travail s’est terminé sans erreurs.

## Common Issues & Tips
- **Chemin de fichier incorrect** – Vérifiez que `dataDir` se termine par une barre oblique ou utilisez `Paths.get(...)` pour des chemins indépendants de la plateforme.  
- **Licence non définie** – En environnement de production, appelez `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` avant de créer `Project`.  
- **Jour de début de semaine inattendu** – Assurez‑vous d’utiliser la bonne valeur d’énumération `DayType` (par ex., `DayType.Sunday`).  

## Frequently Asked Questions

**Q : Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?**  
R : Oui, Aspose.Tasks for Java offre un support complet pour gérer des structures de projet complexes avec facilité.

**Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument, Aspose.Tasks for Java prend en charge diverses versions de fichiers Microsoft Project, garantissant la compatibilité sur toutes les plateformes.

**Q : Puis‑je intégrer Aspose.Tasks for Java dans mes applications Java existantes ?**  
R : Oui, Aspose.Tasks for Java propose des capacités d’intégration transparentes, vous permettant d’enrichir vos applications Java avec des fonctionnalités puissantes de gestion de projet.

**Q : Aspose.Tasks for Java fournit‑il de la documentation et du support ?**  
R : Oui, vous pouvez accéder à une documentation exhaustive et à un support communautaire pour Aspose.Tasks for Java sur leur [site web](https://releases.aspose.com/).

**Q : Existe‑t‑il une version d’essai gratuite pour Aspose.Tasks for Java ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.Tasks for Java depuis leur [site web](https://reference.aspose.com/tasks/java/) pour explorer les fonctionnalités avant d’effectuer un achat.

---

**Dernière mise à jour :** 2025-12-23  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}