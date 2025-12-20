---
date: 2025-12-20
description: Apprenez comment exporter un PDF avec Aspose.Tasks pour Java, un guide
  simple pour convertir MPP en PDF et enregistrer vos fichiers de projet efficacement.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment exporter un PDF dans Aspose.Tasks – Enregistrer sous PDF
url: /fr/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment exporter un PDF avec Aspose.Tasks – Enregistrer en PDF

## Introduction
Dans ce tutoriel, nous vous montrerons **comment exporter un PDF** avec Aspose.Tasks pour Java, en vous guidant à travers le processus d’enregistrement d’un projet au format PDF. Avec Aspose.Tasks, vous pouvez efficacement **convertir MPP en PDF**, assurant compatibilité et facilité de partage entre les équipes et les parties prenantes. Plongeons dans les étapes afin que vous puissiez rapidement obtenir un PDF imprimable à partir de n’importe quel fichier de projet.

## Quick Answers
- **Que signifie « export PDF » dans Aspose.Tasks ?** Cela signifie convertir un fichier de projet (par ex., MPP) en un document PDF qui préserve la mise en page visuelle.  
- **Quelle version de la bibliothèque est requise ?** Toute version d’Aspose.Tasks pour Java qui prend en charge `PdfSaveOptions` (la dernière version est recommandée).  
- **Ai‑je besoin d’une licence pour cette conversion ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je personnaliser l’apparence du PDF ?** Oui – vous pouvez définir l’échelle de temps, les légendes et d’autres `PdfSaveOptions`.  
- **La conversion est‑elle rapide pour les grands projets ?** Généralement quelques secondes ; les performances dépendent de la taille du projet et des options choisies.

## Qu’est‑ce que « how to export pdf » dans le contexte d’Aspose.Tasks ?
Exporter un PDF avec Aspose.Tasks signifie prendre un fichier de projet (tel que `.mpp`, `.xml` ou `.xlsx`) et générer un PDF qui reflète le diagramme de Gantt, la vue d’utilisation des tâches ou tout autre format de présentation que vous configurez. Cela est utile pour les rapports, la documentation ou le partage de vues en lecture seule avec des parties prenantes non techniques.

## Pourquoi exporter des fichiers de projet en PDF ?
- **Lisibilité universelle :** le PDF fonctionne sur n’importe quel appareil sans nécessiter le logiciel de projet d’origine.  
- **Présentation professionnelle :** préservez le formatage, les couleurs et la mise en page pour les rapports destinés aux clients.  
- **Distribution facile :** partagez par e‑mail, intranet ou stockage cloud sans souci de contrôle de version.  
- **Conformité et archivage :** les PDF sont idéaux pour le stockage à long terme et la conformité réglementaire.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

1. **Java Development Kit (JDK) :** JDK 8 ou version ultérieure installé sur votre machine.  
2. **Aspose.Tasks for Java Library :** Téléchargez la bibliothèque depuis le site officiel [ici](https://releases.aspose.com/tasks/java/).  
3. **Un fichier de projet :** Disposez d’un fichier de projet existant (par ex., `HomeMovePlan.mpp`) prêt à être converti.

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier `.mpp`. Cela charge le projet en mémoire afin que vous puissiez le manipuler ou l’exporter.

### Step 2: Save the Project as PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
La ligne ci‑dessus effectue une opération simple de **save project as PDF**, créant `Project5.pdf` dans le même dossier.

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Nous démontrons ici l’utilisation des **pdf save options** pour contrôler la mise en page :
- `setFitContent(true)` force le contenu à s’ajuster à la largeur de la cellule.  
- `setTimescale(Timescale.Months)` change l’échelle de temps en mois.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` sélectionne la vue Utilisation des tâches.

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
Désactiver les légendes peut rendre le PDF plus compact, surtout pour les grands projets.

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Cette étape finale écrit le PDF en utilisant les options personnalisées définies ci‑dessus, produisant un document propre, à l’échelle mensuelle, sans légendes par page.

## Common Issues & Tips
- **Fichier introuvable :** assurez‑vous que `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) et pointe vers le bon répertoire.  
- **Pages blanches :** vérifiez que le `PresentationFormat` sélectionné correspond à la vue attendue (par ex., Gantt, Utilisation des tâches).  
- **Les gros fichiers prennent plus de temps :** envisagez de définir `o.setFitContent(false)` pour les très grands projets afin de réduire le temps de traitement.  

## Frequently Asked Questions

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Java ?**  
R : Oui, Aspose.Tasks prend en charge les versions de Java à partir de JDK 6 et supérieures.

**Q : Puis‑je personnaliser l’apparence du PDF généré ?**  
R : Absolument ! Aspose.Tasks offre de nombreuses **pdf save options** — telles que l’échelle de temps, la visibilité des légendes et le format de présentation—pour adapter le PDF à vos besoins.

**Q : Aspose.Tasks prend‑il en charge d’autres formats de fichier pour la conversion ?**  
R : Oui, vous pouvez convertir entre MPP, XML, XLSX et bien d’autres formats, ce qui en fait un outil polyvalent pour **convert mpp to pdf** et d’autres transformations.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks ?**  
R : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Pour le support et l’assistance, visitez le forum officiel [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
En suivant ce guide, vous savez maintenant **comment exporter un PDF** depuis n’importe quel projet Java avec Aspose.Tasks, depuis une simple sauvegarde en une ligne jusqu’à une personnalisation avancée avec `PdfSaveOptions`. Utilisez ces techniques pour produire des PDF soignés et partageables pour les rapports, les présentations client ou l’archivage.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}