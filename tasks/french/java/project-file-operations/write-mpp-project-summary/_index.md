---
date: 2025-12-23
description: Apprenez à créer un résumé MPP et à mettre à jour l’auteur du projet
  avec Aspose.Tasks pour Java. Définissez et récupérez les informations du projet
  sans effort.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment créer un résumé MPP et mettre à jour l'auteur du projet avec Aspose.Tasks
url: /fr/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire le résumé du projet MPP dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous allez **create MPP summary** des informations pour un fichier Microsoft Project et apprendre comment **update project author** les détails en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un outil de gestion de projet ou automatisiez les rapports, contrôler les propriétés de résumé par programme fait gagner du temps et garantit la cohérence de vos projets.

## Réponses rapides
- **Que signifie “create MPP summary” ?** Cela signifie définir les propriétés de projet de haut niveau (author, revision, keywords, etc.) qui apparaissent dans la boîte de dialogue Project Summary Information de Microsoft Project.  
- **Quelle bibliothèque gère cela ?** Aspose.Tasks for Java fournit une API fluide pour lire et écrire ces propriétés.  
- **Ai-je besoin d’une licence ?** Un essai gratuit est disponible, mais une licence commerciale est requise pour une utilisation en production.  
- **Puis-je également changer l’auteur après que le fichier a été enregistré ?** Oui – vous pouvez **update project author** en appelant `project.set(Prj.AUTHOR, "New Author")` puis en réenregistrant le fichier.  
- **Quels formats de fichier sont pris en charge ?** Les formats MPP et XML (SaveFileFormat.Xml) sont entièrement pris en charge.

## Qu’est‑ce que create MPP summary ?
Créer un résumé MPP implique de remplir les métadonnées du projet — author, revision number, keywords, comments, creation date et printed date. Ces métadonnées sont stockées dans l’enregistrement Project Summary Information et affichées dans la section **File → Info** de Microsoft Project.

## Pourquoi mettre à jour l’auteur du projet ?
Maintenir les informations de **project author** précises est essentiel pour les pistes d’audit, la collaboration et les rapports. Lorsque plusieurs membres de l’équipe contribuent, il peut être nécessaire de **update project author** pour refléter les dernières modifications ou attribuer correctement le travail.

## Prérequis
1. Java Development Kit (JDK) installé sur votre machine.  
2. Aspose.Tasks for Java – téléchargez-le depuis [here](https://releases.aspose.com/tasks/java/).  
3. Un IDE tel que IntelliJ IDEA, Eclipse ou NetBeans.

## Importer les packages
Tout d’abord, importez les packages nécessaires dans votre classe Java :
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Étape 1 : Configurer le projet et définir les informations de résumé
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Dans le code ci‑above nous **create MPP summary** des champs tels que author, revision et keywords. Vous pouvez également **update project author** plus tard en appelant `project.set(Prj.AUTHOR, "New Name")`.

## Étape 2 : Enregistrer les informations de résumé du projet
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Enregistrer le projet persiste toutes les données de résumé que vous venez de définir.

## Étape 3 : Lire les informations de résumé du projet
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Cet extrait montre comment **read back** les informations de résumé, confirmant que l’opération **create MPP summary** a réussi.

## Problèmes courants et solutions
- **Valeurs null après lecture :** Assurez‑vous que le projet a été enregistré avec succès avant de le recharger. Vérifiez les chemins de fichier et les permissions.  
- **Différences de format de date :** `project.get(Prj.CREATION_DATE)` renvoie un `java.util.Date`. Utilisez `SimpleDateFormat` si vous avez besoin d’un format d’affichage personnalisé.  
- **Licence non définie :** Sans licence valide, Aspose.Tasks fonctionne en mode d’évaluation et peut ajouter un filigrane. Enregistrez votre licence tôt dans le code.

## Questions fréquentes
**Q : Puis‑je utiliser Aspose.Tasks for Java avec d’autres bibliothèques Java ?**  
A : Oui, Aspose.Tasks for Java peut être intégré de façon transparente avec d’autres bibliothèques Java pour améliorer vos capacités de gestion de projet.

**Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?**  
A : Oui, vous pouvez télécharger une version d’essai gratuite depuis [here](https://releases.aspose.com/).

**Q : À quelle fréquence Aspose.Tasks for Java est‑il mis à jour ?**  
A : Aspose.Tasks for Java est régulièrement mis à jour afin d’assurer la compatibilité avec les dernières versions de Java et des fichiers Microsoft Project.

**Q : Puis‑je personnaliser davantage les informations de résumé du projet ?**  
A : Absolument, Aspose.Tasks for Java offre de nombreuses options pour personnaliser les informations de résumé du projet selon vos besoins spécifiques.

**Q : Où puis‑je obtenir du support pour Aspose.Tasks for Java ?**  
A : Vous pouvez obtenir du support sur le forum communautaire Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
Dans ce tutoriel, nous vous avons montré comment **create MPP summary** des données, **update project author**, et vérifier ces modifications en utilisant Aspose.Tasks for Java. En automatisant ces étapes, vous obtenez un contrôle complet sur les métadonnées du projet, rendant vos applications plus robustes et vos rapports de projet plus précis.

---

**Dernière mise à jour :** 2025-12-23  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}