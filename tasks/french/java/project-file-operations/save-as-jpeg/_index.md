---
date: 2025-12-20
description: Apprenez comment ajuster la qualité JPEG et exporter des images JPEG
  à partir de fichiers Microsoft Project à l'aide d'Aspose.Tasks pour Java.
linktitle: Save Project As JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ajuster la qualité JPEG lors de l'enregistrement de MS Project en JPEG
url: /fr/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajuster la qualité JPEG lors de l'enregistrement de MS Project en JPEG avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez comment **ajuster la qualité JPEG** lors de l'enregistrement d'un fichier Microsoft Project en image JPEG en utilisant Aspose.Tasks pour Java. Cette fonctionnalité est pratique pour créer des rapports visuels clairs, intégrer des instantanés de projet dans des présentations, ou simplement exporter des fichiers JPEG avec le niveau de détail exact dont vous avez besoin.

## Réponses rapides
- **Que fait «ajuster la qualité JPEG»?** Cela vous permet de contrôler le niveau de compression du JPEG exporté, en équilibrant la taille du fichier et la fidélité visuelle.
- **Quelle bibliothèque gérer la conversion?** Aspose.Tasks pour Java fournit une API simple pour exporter les fichiers Project en JPEG.
- **Ai‑je besoin d’une licence?** Un essai gratuit suffit pour l’évaluation; une licence commerciale est requise pour une utilisation en production.
- **Puis‑je définir la qualité dans le code?** Oui, utilisez la méthode `ImageSaveOptions.setJpegQuality(int)` (plage 0‑100).
- **Le processus est‑il rapide?** La conversion d'un fichier projet typique en JPEG ne prend que quelques secondes sur du matériel moderne.

## Qu'est-ce que « ajuster la qualité JPEG » ?
Ajuster la qualité JPEG consiste à définir le facteur de compression appliqué lorsqu’une image est enregistrée au format JPEG. Une qualité supérieure (valeurs proches de 100) conserve plus de détails mais génère des fichiers plus volumineux, tandis qu'une qualité inférieure réduit la taille du fichier au détriment de la netteté visuelle.

## Pourquoi utiliser Aspose.Tasks pour l'export JPEG ?
Aspose.Tasks offre une méthode fiable et indépendante de la plateforme pour rendre les diagrammes de Gantt, les vues de ressources et d'autres visualisations de projet directement en fichiers image. Elle répond au besoin de captures d’écran manuelles et garantit une sortie cohérente sur tous les environnements.

## Prérequis
Avant de commencer, assurez-vous de disposer de :
1. Java Development Kit (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version depuis le [site Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks pour Java : téléchargez et configurez Aspose.Tasks pour Java en suivant les instructions fournies dans la [documentation](https://reference.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre fichier Java :
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Étape 1 : Définir le répertoire de données
Définissez le chemin vers votre répertoire de données où se trouve votre fichier MS Project.
```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Charger le fichier MS Project
Chargez le fichier MS Project en utilisant Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Étape 3 : Ajuster la qualité JPEG (facultatif)
Si vous souhaitez affiner la sortie, vous pouvez **définir la qualité JPEG** à l’aide de la classe `ImageSaveOptions`. La valeur de qualité varie de 0 à 100, et c’est la façon typique de **définir la qualité jpeg en Java**.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Étape 4 : Enregistrer le projet au format JPEG
Enregistrez le fichier MS Project en tant qu’image JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Comment exporter des fichiers JPEG depuis MS Project
Les étapes ci‑dessus démontrent **comment exporter un JPEG** depuis un fichier Microsoft Project. En ajustant la qualité JPEG, vous contrôlez le compromis entre la clarté de l’image et la taille du fichier, rendant l’image exportée adaptée à la publication web, aux rapports imprimés ou aux diapositives intégrées.

## Conclusion
Dans ce tutoriel, nous avons expliqué comment **ajuster la qualité JPEG** lors de la conversion d’un fichier Microsoft Project en image JPEG à l’aide d’Aspose.Tasks pour Java. Cette approche simplifie le partage des visualisations du projet, garantit une qualité d’image constante et vous offre un contrôle total sur la taille du résultat.

## Questions fréquemment posées supplémentaires

**Q : Le réglage de la qualité JPEG affecte‑t‑il la lisibilité du diagramme de Gantt ?**
R : Une qualité supérieure préserve le texte et les détails des lignes, tandis qu'une qualité très basse peut rendre les petites étiquettes difficiles à lire.

**Q : Puis‑je exporter d’autres formats d’image en plus du JPEG ?**
R : Oui, Aspose.Tasks prend en charge PNG, BMP et TIFF via l'énumération `SaveFileFormat` appropriée.

**Q : Est-il possible d’exporter plusieurs pages (par ex., différentes vues) en une fois ?**
R : Vous pouvez parcourir les vues souhaitées et enregistrer chacune comme un JPEG séparé en utilisant la même configuration `ImageSaveOptions`.

**Q : Quelle version de Java est requise ?**
R: Aspose.Tasks pour Java fonctionne avec JDK8 et supérieur.

**Q : Comment gérer les grands projets qui produisent de grandes images ?**
R : Envisagez de réduire la qualité JPEG ou de redimensionner les dimensions de l’image via des paramètres supplémentaires de `ImageSaveOptions`.

---

**Dernière mise à jour :** 20/12/2025
**Testé avec :** Aspose.Tasks pour Java 24.11
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}