---
date: 2026-06-15
description: Apprenez comment convertir MPP en PDF et générer les vues Resource Usage
  et Sheet à l’aide d’Aspose.Tasks pour Java. Suivez notre guide étape par étape pour
  définir timescale et créer des rapports PDF détaillés sans effort.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Convertir MPP en PDF et générer la vue Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Convertir MPP en PDF et générer la vue Resource Usage – Aspose.Tasks
url: /fr/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir MPP en PDF et rendre la vue Utilisation des ressources – Aspose.Tasks

Dans ce tutoriel, vous apprendrez **comment convertir mpp en pdf** tout en rendant les vues Utilisation des ressources et Feuille d'un fichier Microsoft Project. L'utilisation d'Aspose.Tasks pour Java élimine le besoin de Microsoft Project sur le serveur, vous offrant un moyen rapide et fiable de créer des rapports PDF à partir de fichiers MPP. Nous vous montrerons également **comment définir l'échelle de temps** afin que la sortie corresponde à vos exigences de reporting.

## Réponses rapides
- **Que fait Aspose.Tasks ?** Il lit, modifie et convertit les fichiers Microsoft Project (MPP) sans nécessiter l'installation de MS Project.  
- **Puis-je convertir MPP en PDF en une seule ligne de code ?** Oui – chargez le projet, définissez SaveOptions et appelez `save`.  
- **Quelles échelles de temps sont prises en charge ?** Days, ThirdsOfMonths, et Months.  
- **Ai-je besoin d'une licence pour la production ?** Une licence commerciale est requise pour les déploiements non‑essai.  
- **La bibliothèque est‑elle compatible avec Java 8+ ?** Absolument – elle prend en charge Java 8 et les versions ultérieures.

## Qu'est-ce que la conversion mpp en pdf ?
*Convert mpp to pdf* désigne le processus consistant à prendre un fichier Microsoft Project (.mpp) et à générer une version au format Portable Document Format (PDF) qui reproduit fidèlement les tableaux, plannings, graphiques et allocations de ressources du projet. Le PDF résultant peut être facilement partagé, imprimé et archivé sans nécessiter l'installation de Microsoft Project sur la machine du destinataire.

## Pourquoi convertir un projet en PDF avec Aspose.Tasks ?
Aspose.Tasks prend en charge **plus de 50 formats d'entrée et de sortie** et peut rendre des projets de plusieurs centaines de pages sans charger le fichier complet en mémoire, réduisant l'utilisation de RAM jusqu'à 70 %. La sortie PDF conserve les tableaux, graphiques et allocations de ressources, ce qui la rend idéale pour la distribution aux parties prenantes et l'archivage.

## Prérequis
1. **Java Development Kit (JDK)** – Java 8 ou version plus récente installée sur votre machine.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).  

## Comment convertir mpp en pdf avec Aspose.Tasks pour Java ?
Chargez votre fichier MPP source, configurez l'échelle de temps souhaitée, définissez le format de présentation sur **ResourceUsage**, et enregistrez le résultat en PDF. Ce flux de bout en bout ne nécessite que quelques appels d'API et s'exécute en moins d'une seconde pour des projets de taille typique.

### Étape 1 : Lire le projet source
La classe `Project` représente un fichier Microsoft Project chargé en mémoire, offrant un accès à ses données et à sa structure.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Étape 2 : Définir SaveOptions avec les paramètres TimeScale requis
`SaveOptions` configure la façon dont le projet est enregistré, vous permettant de spécifier des paramètres spécifiques au format tels que l'échelle de temps.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Étape 3 : Définir le format de présentation sur ResourceUsage
`PresentationFormat` détermine quelle vue du projet (par ex., ResourceUsage) est rendue dans le document de sortie.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Étape 4 : Enregistrer le projet en PDF
`project.save` écrit le projet dans un fichier en utilisant les `SaveOptions` fournies, produisant le PDF final.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Étape 5 : Rendre les vues pour d'autres paramètres TimeScale
Répétez les étapes précédentes, en modifiant la valeur `TimeScale` pour rendre des vues d'échelle de temps supplémentaires.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Étape 6 : Optionnel – Convertir plusieurs projets en lot
Si vous devez **convertir un projet en pdf** pour de nombreux fichiers, placez la logique ci‑dessus dans une boucle qui parcourt un répertoire de fichiers *.mpp*. Cette approche **enregistre les pdf de ms project** en masse avec des modifications de code minimales.  
Le code suivant montre un exemple complet de conversion d'un fichier MPP en PDF avec les paramètres souhaités.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Problèmes courants et solutions
- **Polices manquantes dans le PDF** – Assurez-vous que les polices requises sont installées sur le serveur ou intégrez‑les via `PdfSaveOptions`.  
- **Les gros fichiers de projet provoquent OutOfMemoryError** – Utilisez `LoadOptions.setLoadAllResources(false)` pour charger les ressources à la demande.  
- **Rendu d'échelle de temps incorrect** – Vérifiez que `options.setTimeScale(TimeScale.Days)` (ou autre enum) correspond à la granularité souhaitée.

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il rendre d’autres vues en plus de Utilisation des ressources et Feuille ?**  
A: Oui, il prend également en charge le diagramme de Gantt, l’utilisation des tâches, le calendrier et de nombreuses vues supplémentaires.

**Q : Aspose.Tasks est‑il compatible avec différentes versions des fichiers Microsoft Project ?**  
A: Absolument – il gère les formats MPP, MPT et XML de Project 2000 à Project 2021.

**Q : Puis‑je personnaliser l’apparence des vues rendues ?**  
A: Oui, vous pouvez modifier les couleurs, les polices et la disposition des colonnes via `PdfSaveOptions` et `PresentationOptions`.

**Q : Aspose.Tasks nécessite‑t‑il l’installation de Microsoft Project ?**  
A: Non, c’est une bibliothèque autonome qui fonctionne dans tout environnement compatible Java.

**Q : Où puis‑je obtenir de l’assistance technique ?**  
A: Le support est disponible via le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.Tasks 24.12 for Java  
**Auteur :** Aspose

## Tutoriels associés

- [Rendre la vue Utilisation des ressources et Feuille dans Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Comment exporter un PDF dans Aspose.Tasks – Enregistrer en PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Comment créer des fichiers MPP avec Aspose.Tasks pour Java](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}