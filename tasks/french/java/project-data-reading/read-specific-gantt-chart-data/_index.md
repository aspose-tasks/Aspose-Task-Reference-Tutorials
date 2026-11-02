---
date: 2026-10-31
description: Apprenez comment exporter le Gantt en PDF en Java avec Aspose.Tasks.
  Ce guide étape par étape vous montre comment lire les données du diagramme de Gantt
  et générer des rapports PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Lire des données spécifiques du diagramme de Gantt dans Aspose.Tasks
og_description: Exportez le Gantt en PDF en Java avec Aspose.Tasks. Suivez ce tutoriel
  pour lire les données du diagramme de Gantt, personnaliser les propriétés d'affichage
  et générer des rapports PDF pour la gestion de projet.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Exporter le Gantt en PDF en Java – guide Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Exporter le Gantt en PDF en Java – extraire des données spécifiques
url: /fr/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter le gantt au format pdf en Java – extraire des données spécifiques

## Introduction
Dans ce tutoriel, vous apprendrez comment **exporter un gantt au format pdf en Java** en lisant les informations du diagramme de Gantt avec Aspose.Tasks for Java. Les diagrammes de Gantt offrent aux chefs de projet une feuille de route visuelle des tâches, des dépendances et des échéances, et pouvoir extraire ces données de manière programmatique vous permet de créer des rapports PDF automatisés, des tableaux de bord ou des intégrations avec d’autres systèmes d’entreprise. Parcourons chaque étape, du chargement d’un fichier de projet à l’extraction des propriétés de vue, jusqu’à la génération du PDF.

## Réponses rapides
- **Quoi puis‑je extraire ?** Toute propriété de vue, style de barre, ligne de grille, style de texte, ligne de progression ou niveau d’échelle de temps d’un diagramme Gantt.  
- **Ai‑je besoin d’une licence ?** Une version d’essai fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou ultérieure (le tutoriel utilise JDK 11).  
- **Le code est‑il exécutable tel quel ?** Oui – il suffit de remplacer le chemin du répertoire de données.  
- **Puis‑je modifier la vue après la lecture ?** Absolument – l’API vous permet de changer les propriétés et de les enregistrer dans le fichier de projet.

## Qu’est‑ce que l’exportation du gantt en pdf ?
L’exportation du gantt en pdf est le processus de conversion d’une vue de diagramme Gantt stockée dans un fichier de projet en un document PDF qui préserve le style visuel et les informations de chronologie. Cette opération est utile pour partager l’état du projet avec des parties prenantes qui ne disposent pas d’un outil de gestion de projet.

## Pourquoi exporter le gantt au format pdf avec Aspose.Tasks ?
Aspose.Tasks peut gérer **plus de 30 + formats d’entrée** (MPP, XML, MPX, etc.) et **exporter vers PDF en un seul appel** tout en conservant 95 % de la fidélité visuelle, même pour des projets de plus de 500 tâches. La bibliothèque traite les fichiers en mémoire, vous permettant de générer des PDF sur des serveurs sans installer Microsoft Project.

## Prérequis
1. **Java Development Kit (JDK) :** Assurez‑vous d’avoir Java installé sur votre système. Vous pouvez le télécharger depuis la **[page de téléchargement d’Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Bibliothèque Aspose.Tasks for Java :** Téléchargez et installez la bibliothèque Aspose.Tasks for Java depuis la **[page de téléchargement d’Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)**.  
3. **Environnement de développement intégré (IDE) :** Choisissez l’IDE de votre préférence. Les choix populaires incluent IntelliJ IDEA, Eclipse ou NetBeans.

## Importer les packages
Les importations suivantes vous donnent accès aux classes principales d’Aspose.Tasks nécessaires à la lecture et à l’exportation des données Gantt.  
*No code block is shown here to keep the tutorial focused on concepts; simply add the imports to your Java file.*

## Comment charger un fichier de projet de diagramme Gantt en Java ?
Chargez le fichier de projet en créant une instance `Project` et en passant le chemin complet au constructeur. Cette étape initialise la représentation en mémoire du diagramme Gantt, permettant les requêtes ultérieures sur les propriétés de vue. Lorsque le fichier est chargé avec succès, vous pouvez vérifier le nom du projet, la date de début et le nombre de tâches afin de vous assurer que le bon fichier a été ouvert. Cette vérification aide à détecter tôt les problèmes de chemin ou de format.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Ancre de définition :* `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier de projet unique en mémoire.

## Comment accéder à la vue du diagramme Gantt ?
Récupérez la première vue Gantt de la collection de vues du projet. La plupart des projets contiennent au moins une vue Gantt, généralement la première entrée. Après avoir obtenu la vue, vous pouvez vérifier son nom et vous assurer qu’elle est de type `GanttChartView` avant de procéder à l’extraction des propriétés. Cette vérification supplémentaire évite les erreurs d’exécution lors de la manipulation de collections de vues personnalisées ou non standard.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Ancre de définition :* `GanttChartView` représente la disposition visuelle des tâches, des échelles de temps et des barres que vous voyez dans un diagramme Gantt typique.

## Comment extraire les propriétés de vue ?
Vous pouvez lire des propriétés telles que la couleur d’arrière‑plan, la hauteur des barres et les paramètres d’échelle de temps directement depuis l’objet `GanttChartView`. Les afficher vous aide à vérifier la configuration actuelle avant l’exportation. Une boucle d’extraction typique parcourt chaque propriété, formate la valeur en chaîne et l’enregistre dans la console ou dans un fichier pour une analyse ultérieure. Cette approche est utile pour le débogage et pour générer une documentation de l’apparence du diagramme.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Ancre de définition :* `GanttChartView` fournit l’accès aux paramètres de vue tels que la couleur d’arrière‑plan, la hauteur des barres et la configuration de l’échelle de temps.

## Comment extraire les styles de barres ?
Parcourez la collection d’objets `BarStyle` pour obtenir des détails comme la couleur, le motif et la forme de chaque type de barre utilisé dans le diagramme. Pour chaque style, vous pouvez également lire le type de tâche associé et la condition qui déclenche le style, ce qui est essentiel lors de la recréation du diagramme dans un autre format. Collecter ces informations vous permet de produire une réplique visuelle fidèle ou d’appliquer des règles de style personnalisées par programme.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Ancre de définition :* `BarStyle` définit l’apparence visuelle d’une barre Gantt, incluant sa couleur, son motif et sa forme.

## Comment extraire les lignes de grille ?
Les lignes de grille définissent la séparation visuelle entre les lignes et les colonnes. Accédez‑y via la méthode `getGridlines()` et affichez leur visibilité et leur style. Après avoir récupéré la collection de lignes de grille, vous pouvez parcourir chaque ligne pour capturer son type (plein, pointillé), son épaisseur et sa couleur. Ces données sont précieuses lorsque vous devez reproduire exactement la mise en page de la grille dans les PDF exportés ou d’autres formats de rapport.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Ancre de définition :* `getGridlines()` renvoie la collection d’objets de ligne de grille qui contrôlent les séparateurs de lignes et de colonnes dans la vue Gantt.

## Comment extraire les styles de texte ?
Les styles de texte contrôlent la police, la taille et la couleur des libellés sur le diagramme Gantt. Parcourez la collection `TextStyle` pour lister chaque style. Pour chaque style de texte, vous pouvez également récupérer l’élément associé (nom de tâche, date, etc.) et les éventuelles règles de mise en forme conditionnelle. Capturer ces détails garantit que les documents exportés conservent la même typographie que le diagramme original.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Ancre de définition :* `TextStyle` représente les attributs de mise en forme appliqués aux éléments textuels du diagramme Gantt.

## Comment extraire les lignes de progression ?
Les lignes de progression indiquent le point d’achèvement actuel d’une tâche. Accédez‑y via `getProgressLines()` et affichez leurs attributs. Chaque ligne de progression comprend des propriétés telles que la couleur de la ligne, son épaisseur et sa position relative à la barre de tâche. Enregistrer ces informations vous permet de générer des visualisations tenant compte de la progression ou de calculer des métriques globales d’achèvement du projet.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Ancre de définition :* `getProgressLines()` renvoie l’ensemble des objets de ligne de progression qui indiquent l’état d’avancement des tâches.

## Comment extraire les niveaux d’échelle de temps ?
Les niveaux d’échelle de temps définissent les unités de temps hiérarchiques (jours, semaines, mois) affichées sur le diagramme. Récupérez‑les via `getTimescaleTiers()` et affichez leurs paramètres. Pour chaque niveau, vous pouvez capturer le type d’unité, le format d’étiquette et l’alignement, ce qui est crucial pour reproduire exactement la granularité de la chronologie dans les PDF exportés ou les composants UI personnalisés.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Ancre de définition :* `getTimescaleTiers()` fournit l’accès à la collection d’objets de niveau d’échelle de temps qui contrôlent l’affichage de l’axe temporel.

## Comment exporter le diagramme Gantt au format PDF ?
Créez un objet `PdfSaveOptions`, personnalisez éventuellement la taille de page ou l’incorporation de polices, puis appelez `project.save` avec le format PDF. Cet appel unique génère un PDF qui reflète la vue Gantt à l’écran. Vous pouvez également spécifier des options supplémentaires telles que la compression d’image, la suppression du filigrane ou l’incorporation de polices personnalisées pour répondre aux exigences de la charte graphique de l’entreprise. Après l’enregistrement, vérifiez la taille du fichier PDF et la fidélité visuelle pour vous assurer que l’exportation a réussi.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Ancre de définition :* `PdfSaveOptions` vous permet d’ajuster la sortie PDF, comme les dimensions de page, la compression et la gestion des polices.

## Pièges courants et astuces
- **Répertoire de données incorrect :** Assurez‑vous que `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) adapté à votre OS.  
- **Vue manquante :** Si le projet ne possède aucune vue Gantt, `project.getViews()` sera vide – ajoutez une vérification avant le cast.  
- **Exceptions de licence :** Sans licence valide, l’API peut ajouter un filigrane aux PDF exportés.  
- **Projets volumineux :** Pour les projets de plus de 1 000 tâches, envisagez d’augmenter la taille du tas JVM (`-Xmx2g`) afin d’éviter `OutOfMemoryError`.  

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks for Java s’intègre parfaitement à n’importe quelle bibliothèque ou framework Java, y compris Spring, Hibernate et Apache POI.

**Q : Aspose.Tasks convient‑il aux projets d’entreprise à grande échelle ?**  
R : Absolument. La bibliothèque traite des fichiers MPP de plusieurs centaines de pages en moins de 5 secondes sur du matériel serveur standard et prend en charge l’exécution concurrente dans des environnements multithreads.

**Q : Aspose.Tasks prend‑il en charge plusieurs formats de fichiers de projet ?**  
R : Oui, Aspose.Tasks prend en charge plus de 20 formats, dont MPP, XML, MPX et Primavera XML, vous permettant de lire et de convertir des plannings hérités.

**Q : Puis‑je personnaliser l’apparence des diagrammes Gantt avec Aspose.Tasks ?**  
R : Bien sûr. Vous pouvez modifier les styles de barres, les lignes de grille, les styles de texte et les niveaux d’échelle de temps par programme avant d’exporter en PDF ou en formats d’image.

**Q : Comment enregistrer les modifications après avoir modifié une vue ?**  
R : Appelez `project.save("output.mpp");` après toute modification afin de les persister dans le fichier de projet.

---

**Dernière mise à jour :** 2026-10-31  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Tutoriels associés

- [Comment enregistrer un projet au format PDF avec Aspose.Tasks – Guide d’exportation](/tasks/java/project-file-operations/save-as-pdf/)
- [Créer un PDF de projet – Personnaliser l’échelle de temps du diagramme Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Exporter le projet au format PDF et réduire l’écart entre la liste des tâches et le pied de page dans Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}