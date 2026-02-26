---
date: 2026-02-26
description: Apprenez à enregistrer un projet au format PDF et à générer une feuille
  de tâches à l’aide d’Aspose.Tasks pour Java. Exportez rapidement un MPP en PDF grâce
  à ce guide étape par étape.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Enregistrer le projet au format PDF – Générer la feuille de tâches avec Aspose.Tasks
  pour Java
url: /fr/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet au format PDF – Rendre la feuille de tâches avec Aspose.Tasks

## Introduction
Dans ce guide complet, vous découvrirez comment **save project as PDF** et générer une feuille de tâches avec Aspose.Tasks pour Java. Que vous ayez besoin d’exporter un fichier MPP en PDF pour des revues avec les parties prenantes ou simplement de rendre une feuille de tâches propre pour le reporting, ce tutoriel vous accompagne à chaque étape, explique pourquoi chaque paramètre est important et montre le code exact à exécuter.

## Réponses rapides
- **Que fait “save project as pdf” ?** Il convertit un fichier Microsoft Project (MPP) en document PDF, en le formatant éventuellement comme une feuille de tâches.  
- **Quel format est utilisé pour un PDF de feuille de tâches ?** L’option `PresentationFormat.TaskSheet` dans `PdfSaveOptions`.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une licence temporaire ou complète est requise en production ; un essai gratuit suffit pour l’évaluation.  
- **Quels sont les prérequis principaux ?** Java JDK, la bibliothèque Aspose.Tasks for Java, et un fichier de projet valide (par ex., *.mpp).  
- **Puis‑je personnaliser la mise en page du PDF ?** Oui, Aspose.Tasks propose de nombreuses propriétés `PdfSaveOptions` pour le style et la configuration de la page.

## Qu’est‑ce que “save project as pdf” ?
Enregistrer un projet au format PDF transforme les données internes du projet en un document portable et en lecture seule. C’est idéal pour partager des plannings, des feuilles de tâches ou des rapports d’état avec des parties prenantes qui n’ont pas Microsoft Project installé.

## Pourquoi rendre une feuille de tâches ?
Une feuille de tâches présente chaque tâche sous forme tabulaire, affichant les ID, les noms, les dates de début/fin et d’autres champs. La rendre en PDF garantit un formatage cohérent sur toutes les plateformes et facilite l’impression ou l’intégration dans d’autres documents.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – dernière version installée et `java`/`javac` disponibles dans votre PATH.  
2. **Aspose.Tasks for Java** – téléchargez la bibliothèque depuis le site officiel [here](https://releases.aspose.com/tasks/java/).  
3. Un **fichier de projet** valide (`*.mpp`) que vous souhaitez convertir, par ex., `NewProductDev.mpp`.  

## Importer les packages
Tout d’abord, importez les classes Aspose.Tasks requises. Ces imports vous donnent accès aux options d’enregistrement PDF, aux formats de présentation et à l’objet principal `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de vos documents
Définissez le dossier où se trouve le fichier MPP source et où le PDF généré sera écrit. L’utilisation d’un chemin absolu ou relatif fonctionne ; assurez‑vous simplement que le dossier existe.

```java
String dataDir = "Your Document Directory";
```

### Étape 2 : Charger le fichier de projet
Créez une instance `Project` en chargeant le fichier MPP existant. Cet objet représente toute la structure du projet en mémoire.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Étape 3 : Configurer les options d’enregistrement – Exporter le MPP en PDF
Instanciez `PdfSaveOptions` et indiquez à Aspose.Tasks que vous voulez que le PDF soit rendu comme une **feuille de tâches**. C’est l’étape clé pour le cas d’utilisation *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Étape 4 : Enregistrer le projet en tant que feuille de tâches – Enregistrer le projet au format PDF
Appelez la méthode `save` sur l’objet `Project`, en passant le nom du fichier cible et les options configurées. Cette action **convertit le fichier MPP en PDF** formaté comme une feuille de tâches.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Étape 5 : Examiner le résultat
Naviguez vers le répertoire que vous avez spécifié (`dataDir`). Vous devriez voir `taskSheet.pdf` contenant une liste soigneusement formatée de toutes les tâches. Ouvrez‑le avec n’importe quel lecteur PDF pour vérifier que la conversion a réussi.

## Problèmes courants et solutions
- **FileNotFoundException** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) et que le nom du fichier MPP est correct.  
- **LicenseException** – Si vous rencontrez des erreurs de licence, appliquez une licence temporaire ou achetée avant d’appeler toute API Aspose.Tasks.  
- **Blank PDF** – Vérifiez que le projet contient réellement des tâches ; un projet vide produira un PDF vide.

## Questions fréquentes

**Q : Aspose.Tasks est‑il compatible avec toutes les versions de Java ?**  
R : Oui, Aspose.Tasks fonctionne avec un large éventail de versions Java. Consultez la [documentation](https://reference.aspose.com/tasks/java/) pour plus de détails.

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Absolument ! Explorez la version d’essai gratuite [here](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**  
R : Rejoignez la communauté Aspose.Tasks sur le [forum](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide et participer aux discussions.

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Obtenez votre licence temporaire [here](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.Tasks pour Java ?**  
R : Achetez Aspose.Tasks pour Java [here](https://purchase.aspose.com/buy).

## Conclusion
En suivant ces étapes, vous avez appris comment **save project as PDF**, en particulier en rendant une feuille de tâches, à l’aide d’Aspose.Tasks pour Java. Cette fonctionnalité vous permet d’*export MPP to PDF* rapidement, de partager des instantanés de projet lisibles et d’intégrer les données du projet dans des flux de travail de reporting plus larges.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}