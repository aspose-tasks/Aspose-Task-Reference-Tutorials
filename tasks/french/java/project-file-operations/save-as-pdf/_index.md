---
date: 2026-03-27
description: Apprenez à enregistrer un projet au format PDF avec Aspose.Tasks pour
  Java, un guide simple pour convertir MPP en PDF et exporter efficacement les fichiers
  de projet.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment enregistrer un projet au format PDF avec Aspose.Tasks – Guide d’exportation
url: /fr/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment enregistrer un projet au format PDF avec Aspise.Tasks – Guide d'exportation

## Introduction
Dans ce tutoriel, vous découvrirez **comment enregistrer un projet au format pdf** en utilisant Aspose.Tasks pour Java. Nous vous guiderons à travers tout, de la conversion en une seule ligne à la personnalisation avancée du PDF, afin que vous puissiez transformer n'importe quel MPP (ou autre format pris en charge) en un document PDF soigné et partageable. Que vous ayez besoin d'un rapport imprimable rapide ou d'un diagramme de Gantt entièrement stylisé, ces étapes vous y mèneront rapidement.

## Réponses rapides
- **Que signifie « export PDF » dans Aspose.Tasks ?** Cela signifie convertir un fichier de projet (par ex., MPP) en un document PDF qui conserve la mise en page visuelle.  
- **Quelle version de la bibliothèque est requise ?** Toute version d'Aspose.Tasks pour Java qui prend en charge `PdfSaveOptions` (la dernière version est recommandée).  
- **Ai-je besoin d'une licence pour cette conversion ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour une utilisation en production.  
- **Puis-je personnaliser l'apparence du PDF ?** Oui – vous pouvez définir l'échelle de temps, les légendes et d'autres `PdfSaveOptions`.  
- **La conversion est‑elle rapide pour les grands projets ?** Généralement quelques secondes ; les performances dépendent de la taille du projet et des options choisies.

## Qu'est‑ce que « enregistrer un projet au format pdf » dans le contexte d'Aspose.Tasks ?
Enregistrer un projet au format PDF avec Aspose.Tasks consiste à prendre un fichier de projet (tel que `.mpp`, `.xml` ou `.xlsx`) et à générer un PDF qui reproduit le diagramme de Gantt, la vue d'utilisation des tâches ou tout autre format de présentation que vous configurez. Cela est utile pour les rapports, la documentation ou le partage de vues en lecture seule avec des parties prenantes non techniques.

## Pourquoi exporter le diagramme de Gantt au format PDF ?
- **Lisibilité universelle :** les PDF s'ouvrent sur n'importe quel appareil sans nécessiter le logiciel de projet d'origine.  
- **Présentation professionnelle :** conservez les couleurs, les polices et la mise en page pour les rapports destinés aux clients.  
- **Distribution facile :** partagez par e‑mail, intranet ou stockage cloud sans soucis de contrôle de version.  
- **Conformité et archivage :** les PDF sont idéaux pour le stockage à long terme et la conformité réglementaire.

## Prérequis
Avant de commencer, assurez‑vous de disposer de ce qui suit :

1. **Java Development Kit (JDK) :** JDK 8 ou version ultérieure installé sur votre machine.  
2. **Bibliothèque Aspose.Tasks pour Java :** Téléchargez la bibliothèque depuis le site officiel [here](https://releases.aspose.com/tasks/java/).  
3. **Un fichier de projet :** Disposez d'un fichier de projet existant (par ex., `HomeMovePlan.mpp`) prêt pour la conversion.

## Importer les packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Guide étape par étape

### Étape 1 : Lire le fichier de projet d'entrée
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier `.mpp`. Cela charge le projet en mémoire afin que vous puissiez le manipuler ou l'exporter.

### Étape 2 : Enregistrer le projet au format PDF (conversion de base)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
La ligne ci‑dessus effectue une opération simple de **save project as pdf**, créant `Project5.pdf` dans le même dossier.

### Étape 3 : Ajuster le contenu à la taille de la cellule (options avancées de sauvegarde PDF)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Nous démontrons ici l'utilisation des **pdf save options** pour contrôler la mise en page :
- `setFitContent(true)` force le contenu à s'adapter à la largeur de la cellule.  
- `setTimescale(Timescale.Months)` change l'échelle de temps en mois.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` sélectionne la vue Task Usage.

### Étape 4 : Masquer les légendes (sortie plus propre)
```java
o.setLegendOnEachPage(false);
```
Désactiver les légendes peut rendre le PDF plus compact, surtout pour les grands projets.

### Étape 5 : Enregistrer le projet avec les options appliquées
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Cette étape finale écrit le PDF en utilisant les options personnalisées définies ci‑dessus, produisant un document propre, à l’échelle mensuelle, sans légendes par page.

## Exporter le diagramme de Gantt au PDF – Style personnalisé
Si vous souhaitez exporter uniquement le diagramme de Gantt avec un aspect spécifique, définissez `PresentationFormat` sur `GanttChart` et ajustez des options supplémentaires comme `setBarColor` ou `setShowCriticalTasks`. Cette approche vous permet de **export gantt chart to pdf** avec un contrôle total sur les éléments visuels.

## Problèmes courants et conseils
- **Fichier non trouvé :** assurez‑vous que `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) et pointe vers le bon répertoire.  
- **Pages blanches :** vérifiez que le `PresentationFormat` sélectionné correspond à la vue attendue (par ex., Gantt, Task Usage).  
- **Les gros fichiers prennent plus de temps :** envisagez de définir `o.setFitContent(false)` pour les très grands projets afin de réduire le temps de traitement.  

## Questions fréquentes

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Java ?**  
R : Oui, Aspose.Tasks prend en charge les versions Java à partir de JDK 6 et supérieures.

**Q : Puis‑je personnaliser l'apparence du PDF généré ?**  
R : Absolument ! Aspose.Tasks offre de nombreuses **pdf save options** — comme l’échelle de temps, la visibilité des légendes et le format de présentation — pour adapter le PDF à vos besoins.

**Q : Aspose.Tasks prend‑il en charge d’autres formats de fichier pour la conversion ?**  
R : Oui, vous pouvez convertir entre MPP, XML, XLSX et de nombreux autres formats, ce qui en fait un outil polyvalent pour **convert mpp to pdf** et d’autres transformations.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks ?**  
R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks depuis [here](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Pour le support et l'assistance, visitez le forum officiel [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
En suivant ce guide, vous savez maintenant **comment enregistrer un projet au format pdf** depuis n'importe quel projet Java en utilisant Aspose.Tasks, depuis une simple sauvegarde en une ligne jusqu'à une personnalisation avancée avec `PdfSaveOptions`. Utilisez ces techniques pour produire des PDF soignés et partageables pour les rapports, les présentations client ou les besoins d'archivage.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}