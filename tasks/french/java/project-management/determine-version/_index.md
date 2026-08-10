---
date: 2026-05-31
description: Apprenez comment obtenir la version du projet et récupérer la date de
  dernière sauvegarde des fichiers MS Project à l'aide d'Aspose.Tasks pour Java. Guide
  étape par étape avec des exemples de code.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Déterminer la version du projet avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment obtenir la version du projet – Aspose Tasks Java Tutoriel
url: /fr/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir la version du projet – Tutoriel Aspose Tasks Java

Dans ce **tutoriel Aspose Tasks Java**, vous apprendrez **comment obtenir la version du projet** d’un fichier Microsoft Project ainsi que **comment récupérer la date de dernière sauvegarde** en utilisant la bibliothèque Aspose.Tasks pour Java. Connaître la version du fichier et le horodatage de sauvegarde vous aide à éviter les problèmes de compatibilité, à appliquer les politiques de migration et à tenir des journaux d’audit précis. Nous parcourrons chaque étape — de la configuration de l’environnement à l’affichage de la version et de la date — afin que vous puissiez intégrer cette vérification dans n’importe quelle application Java en toute confiance.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Détermination de la version du fichier MS Project et de la date de dernière sauvegarde avec Aspose.Tasks pour Java.  
- **Dois‑je installer Microsoft Project ?** Non, Aspose.Tasks fonctionne indépendamment de Microsoft Project.  
- **Quels formats de fichiers sont pris en charge ?** Les fichiers Project basés sur XML tels que MPP et XML sont entièrement pris en charge.  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour une vérification de version basique.  
- **Une licence est‑elle requise ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est nécessaire pour une utilisation en production.

## Qu’est‑ce que le tutoriel Aspose Tasks Java ?
Le tutoriel `Aspose.Tasks` Java est un guide concis et pratique qui montre comment interagir avec les données Microsoft Project de façon programmatique. Il vous montre comment lire, modifier et analyser les informations du projet sans nécessiter l’installation de Microsoft Project sur le serveur. De plus, il couvre le chargement des fichiers, l’accès aux propriétés et l’enregistrement des modifications, permettant aux développeurs d’automatiser efficacement les tâches de gestion de projet.

## Pourquoi utiliser Aspose.Tasks pour déterminer la version du projet ?
Aspose.Tasks fournit **des métadonnées de version exactes** et **des horodatages de dernière sauvegarde** tout en s’exécutant sur tout OS supportant Java. Il traite des fichiers jusqu’à **500 pages en moins de 2 secondes** sur un CPU standard de 2,5 GHz, ce qui le rend idéal pour l’automatisation par lots et les scénarios de migration à grande échelle.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java JAR** – téléchargez-le depuis le [site web](https://releases.aspose.com/tasks/java/) et ajoutez-le au classpath de votre projet.  
3. **Fichier MS Project** – un fichier Project basé sur XML (par ex., `input.xml`) que vous souhaitez inspecter.  

> **Astuce :** Stockez le fichier Project dans un dossier dédié `data` pour garder les chemins propres et éviter les écrasements accidentels.

## Importer les packages
Tout d’abord, importez les classes essentielles d’Aspose.Tasks :

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Comment configurer le répertoire du projet
Pour localiser correctement vos fichiers de projet, créez un répertoire dédié au sein de la structure de votre application et stockez-y tous les fichiers d’entrée. Cela maintient le code propre et évite les erreurs liées aux chemins lors du chargement des fichiers. Utilisez un nom de variable clair pour le chemin du répertoire, qui peut être absolu ou relatif à la racine du projet.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu ou relatif où se trouve `input.xml`.

## Comment charger le projet
`Project` est l’objet principal d’Aspose.Tasks qui représente un fichier Microsoft Project en mémoire, vous donnant accès à toutes les propriétés et collections du projet. Après avoir créé l’instance `Project`, vous pouvez interroger ses champs, parcourir les tâches ou modifier les données avant d’enregistrer le fichier sur le disque.

```java
Project project = new Project(dataDir + "input.xml");
```

Si votre fichier porte un autre nom, ajustez `"input.xml"` en conséquence.

## Comment déterminer la version du projet
`Prj.SAVE_VERSION` est une propriété qui indique le numéro de version de Microsoft Project qui a enregistré le fichier. `Prj.LAST_SAVED` est une propriété qui stocke la date et l’heure de la dernière sauvegarde du fichier. `Prj.SAVE_VERSION` renvoie la version numérique de l’application Microsoft Project qui a enregistré le fichier (par ex., 12 pour Project 2010). `Prj.LAST_SAVED` fournit la date et l’heure exactes de la sauvegarde la plus récente.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Ces valeurs vous permettent d’appliquer programmétiquement des règles métier spécifiques à la version ou de générer des rapports d’audit.

## Comment afficher le résultat
Après avoir récupéré les informations de version et de dernière sauvegarde, vous souhaitez généralement les afficher dans la console ou dans un fichier de journal. Utilisez `System.out.println` pour afficher les valeurs, en formatant la date si nécessaire. Cela confirme que l’extraction a réussi et fournit un retour immédiat pendant le développement ou dans les scripts automatisés.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| `NullPointerException` sur `project.get(...)` | Fichier non trouvé ou chemin incorrect | Vérifiez `dataDir` et le nom du fichier ; utilisez un chemin absolu pour les tests. |
| Numéro de version inattendu (par ex., 0) | Chargement d’un fichier XML qui n’est pas un Project | Assurez‑vous que le fichier est un fichier Microsoft Project valide (MPP/XML). |
| Exception de licence | Utilisation de l’essai sans licence valide en production | Appliquez votre licence Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
**R :** Oui, Aspose.Tasks prend en charge .NET, Java et C++ entre autres.

**Q : Aspose.Tasks est‑il adapté aux projets à grande échelle ?**  
**R :** Absolument ; il peut traiter des projets de plusieurs centaines de pages en quelques secondes sans charger le fichier complet en mémoire.

**Q : Puis‑je personnaliser les données du projet avec Aspose.Tasks ?**  
**R :** Oui, vous pouvez modifier les tâches, les ressources, les calendriers et tout autre élément du projet via l’API.

**Q : Aspose.Tasks nécessite‑t‑il l’installation de Microsoft Project ?**  
**R :** Non, la bibliothèque fonctionne de manière indépendante et n’a pas besoin de Microsoft Project sur la machine hôte.

**Q : Un support technique est‑il disponible pour Aspose.Tasks ?**  
**R :** Oui, vous pouvez obtenir de l’aide sur le forum Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Comment récupérer d’autres propriétés du projet (par ex., auteur, société) ?**  
**R :** Utilisez `project.get(Prj.AUTHOR)` ou `project.get(Prj.COMPANY)` de la même façon que vous récupérez la version.

**Q : Puis‑je vérifier la version d’un fichier MPP (binaire) ?**  
**R :** Oui, Aspose.Tasks charge directement les fichiers `.mpp` ; la propriété `Prj.SAVE_VERSION` fonctionne également pour les formats binaires.

**Q : Existe‑t‑il un moyen de mettre à jour programmétiquement un ancien fichier de projet vers une version plus récente ?**  
**R :** Chargez le fichier ancien, puis enregistrez‑le avec `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks écrit le fichier au format le plus récent par défaut.

## Conclusion
Vous avez maintenant maîtrisé **comment obtenir la version du projet** et **récupérer la date de dernière sauvegarde** à partir des fichiers MS Project en utilisant Aspose.Tasks pour Java. Intégrez ces extraits dans des pipelines d’automatisation, des outils de reporting ou des utilitaires de migration pour garantir que vous connaissez toujours la version exacte du projet que vous manipulez.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Définir la date de début du projet dans MS Project avec Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)
- [Lire la base de données Microsoft Project avec Aspose.Tasks pour Java](/tasks/java/project-data-reading/read-project-database/)
- [Enregistrer le projet en tant que modèle, CSV et texte avec Aspose.Tasks pour Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}