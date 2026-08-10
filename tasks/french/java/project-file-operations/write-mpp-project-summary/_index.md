---
date: 2026-03-29
description: Apprenez comment définir les mots‑clés et la date de création dans un
  projet MPP en Java à l’aide d’Aspose.Tasks for Java. Guide étape par étape avec
  des exemples de code.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment définir des mots‑clés dans le résumé du projet MPP avec Aspose.Tasks
url: /fr/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir des mots‑clés dans le résumé du projet MPP avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment définir des mots‑clés** et d'autres informations de résumé pour un fichier de projet MPP en utilisant Aspose.Tasks pour Java. Que vous ayez besoin d'intégrer les détails de l'auteur, les numéros de révision ou une date de création personnalisée, ce guide vous accompagne pas à pas, avec du code prêt à l'exécution. À la fin, vous pourrez définir des mots‑clés, définir la date de création java, et récupérer les données depuis le fichier.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Tasks for Java  
- **Objectif principal ?** Définir des mots‑clés, les informations d'auteur et la date de création dans un fichier MPP  
- **Combien d'étapes de code ?** Trois blocs de code simples (initialisation, sauvegarde, lecture)  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production  
- **Version Java prise en charge ?** Java 8 et supérieures  

## Qu’est‑ce que « comment définir des mots‑clés » dans un fichier MPP ?
Les mots‑clés sont des champs de métadonnées stockés à l'intérieur d'un fichier Microsoft Project (MPP). Ils aident à catégoriser les projets, à permettre une recherche rapide et à fournir des informations contextuelles pour les outils en aval. Aspose.Tasks expose la propriété `Prj.KEYWORDS`, ce qui rend simple l'écriture ou la mise à jour de cette valeur par programme.

## Pourquoi utiliser Aspose.Tasks pour Java afin de définir des mots‑clés et la date de création ?
* **Compatibilité .MPP complète** – fonctionne avec tous les formats Project 2007‑2023.  
* **Pas d'installation COM ou Office requise** – Java pur, parfait pour les environnements serveur.  
* **API riche** – en plus des mots‑clés, vous pouvez définir l'auteur, la révision, les commentaires et les dates en un seul appel.  
* **Optimisé pour la performance** – lecture/écriture rapide même pour les gros fichiers de projet.  

## Prérequis
1. **Java Development Kit (JDK)** – JDK 8 ou plus récent installé.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, ou tout éditeur de votre choix.

## Importer les packages
Tout d'abord, importez les classes dont vous avez besoin. Ces importations vous donnent accès à l'objet `Project`, à l'énumération `Prj` pour les champs de résumé, et à l'énumération `SaveFileFormat` pour l'enregistrement.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Étape 1 : Configurer le projet et définir les informations de résumé
Créez une instance `Project`, puis utilisez la méthode `set` pour écrire les métadonnées souhaitées. Notez comment nous **définissons les mots‑clés** et **définissons la date de création java** à l'aide d'un objet `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Étape 2 : Enregistrer les informations de résumé du projet
Après avoir rempli les champs, persistez les modifications. Ici nous enregistrons le projet au format XML pour une inspection facile, mais vous pouvez également le sauvegarder au format MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Étape 3 : Lire les informations de résumé du projet
Pour vérifier que les métadonnées ont été correctement écrites, rechargez le fichier et lisez chaque propriété. Cette étape montre que **comment définir des mots‑clés** fonctionne réellement de bout en bout.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **NullPointerException sur `project.get(Prj.CREATION_DATE)`** | Le calendrier n'a jamais été défini avant l'enregistrement. | Assurez‑vous d'appeler `project.set(Prj.CREATION_DATE, cal.getTime())` avant `save()`. |
| **Les mots‑clés n'apparaissent pas dans l'interface de Microsoft Project** | Le fichier a été enregistré en XML et ouvert directement dans Project. | Enregistrez-le au format MPP (`SaveFileFormat.MPP`) ou ouvrez le XML via *Import* dans Project. |
| **Valeurs de date décalées par le fuseau horaire** | Java `Date` inclut l'information de fuseau horaire. | Utilisez `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` si vous avez besoin de dates en UTC. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java avec d'autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks pour Java peut être intégré de manière transparente avec d'autres bibliothèques Java pour améliorer vos capacités de gestion de projet.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite depuis [here](https://releases.aspose.com/).

**Q : À quelle fréquence Aspose.Tasks pour Java est‑il mis à jour ?**  
R : Aspose.Tasks pour Java est régulièrement mis à jour afin d'assurer la compatibilité avec les dernières versions de Java et les fichiers Microsoft Project.

**Q : Puis‑je personnaliser davantage les informations de résumé du projet ?**  
R : Absolument, Aspose.Tasks pour Java offre de nombreuses options pour personnaliser les informations de résumé du projet selon vos besoins spécifiques.

**Q : Où puis‑je obtenir de l'aide pour Aspose.Tasks pour Java ?**  
R : Vous pouvez obtenir de l'aide sur le forum communautaire Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}