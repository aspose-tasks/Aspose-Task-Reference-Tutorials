---
date: 2025-12-25
description: Explorez ce tutoriel Aspose Tasks Java pour apprendre à déterminer la
  version du projet des fichiers MS Project. Guide étape par étape avec des exemples
  de code.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Tutoriel Aspose Tasks Java - Déterminer la version de MS Project'
url: /fr/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutoriel Aspose Tasks Java : Déterminer la version de MS Project

## Introduction
Dans ce **aspose tâches java tutoriel**, vous découvrirez comment trouver programméement la version d'un fichier Microsoft Project en utilisant la bibliothèque Aspose.Tasks pour Java. Connaître la version du fichier vous aide à gérer les problèmes de compatibilité, à appliquer les politiques de migration ou simplement à consigner quelle version du projet a créé le fichier. Nous parcourrons chaque étape — de la configuration de l’environnement à l’affichage de la version et de la date de dernière sauvegarde — afin que vous puissiez intégrer cette vérification dans n’importe quelle application Java en toute confiance.

## Réponses rapides
- **Que couvre ce didacticiel ?** Détermination de la version du fichier MS Project avec Aspose.Tasks pour Java.
- **Dois-je installer Microsoft Project ?** Non, Aspose.Tasks fonctionne indépendamment.
- **Quels formats de fichiers sont pris en charge ?** Fichiers de projet basés sur XML (MPP, XML, etc.).
- **Combien de temps dure la mise en œuvre ?** Environ 5 à 10 minutes pour une vérification de base.

- **Une licence est-elle requise ?** Une version d'essai gratuite permet l'évaluation ; une licence est nécessaire pour la production.

## Qu'est-ce que le tutoriel Java Aspose Tasks ?

Un **tutoriel Java Aspose Tasks** fournit des instructions pratiques pour utiliser l'API Aspose.Tasks dans les projets Java. Il vous montre comment lire, modifier et analyser les données de Microsoft Project sans avoir besoin de Microsoft Project lui-même.

## Pourquoi utiliser Aspose.Tasks pour déterminer la version d'un projet ?

- **Aucune dépendance à Microsoft Project** : idéal pour l'automatisation côté serveur.
- **Métadonnées de version précises** : récupération des champs exacts SAVE_VERSION et LAST_SAVED.
- **Multiplateforme** : fonctionne sur tout système d'exploitation compatible avec Java.
- **Hautes performances** : analyse syntaxique légère adaptée au traitement par lots.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

1. **Java Development Kit (JDK)** – toute version récente (8 ou supérieure).
2. **Aspose.Tasks for Java JAR** – téléchargez-le depuis le [site web](https://releases.aspose.com/tasks/java/) et ajoutez-le au classpath de votre projet.
3. **Fichier MS Project** – un fichier projet XML (par exemple, `input.xml`) que vous souhaitez analyser.

> **Conseil :** Placez le fichier projet dans un dossier `data` dédié pour simplifier la gestion des chemins.

## Importer les packages

Commencez par importer les classes Aspose.Tasks essentielles :

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Étape 1 : Configurer le répertoire du projet
Définissez le dossier contenant votre fichier de projet.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Remplacez « Votre répertoire de données » par le chemin absolu ou relatif où se trouve `input.xml`.

## Étape 2 : Charger le projet
Créez une instance de `Project` en chargeant le fichier XML.

```java
Project project = new Project(dataDir + "input.xml");
```

Si votre fichier porte un nom différent, modifiez `input.xml` en conséquence.

## Étape 3 : Déterminer la version du projet
Récupérez les informations de version et la date et l’heure de la dernière sauvegarde.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

La propriété `Prj.SAVE_VERSION` indique la version de Microsoft Project utilisée pour enregistrer le fichier (par exemple, 12 pour Project 2010). `Prj.LAST_SAVED` renvoie la date et l'heure de la dernière opération d'enregistrement.

## Étape 4 : Afficher le résultat
Signalez la réussite de la vérification de version.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Problèmes courants et solutions
| Problème | Raison | Solution |

|-------|--------|-----|

| `NullPointerException` sur `project.get(...)` | Fichier introuvable ou chemin incorrect | Vérifiez `dataDir` et le nom du fichier ; utilisez un chemin absolu pour les tests. |

| Numéro de version inattendu (par exemple, 0) | Chargement d'un fichier XML non-Project | Assurez-vous que le fichier est un fichier Microsoft Project valide (MPP/XML). |

| Exception de licence | Utilisation de la version d'essai sans licence valide en production | Appliquez votre licence Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Foire aux questions

### Q : Puis-je utiliser Aspose.Tasks avec d'autres langages de programmation ?

R : Oui, Aspose.Tasks prend en charge plusieurs langages, notamment .NET, Java et C++.

### Q : Aspose.Tasks est-il adapté aux projets de grande envergure ?

R : Absolument, Aspose.Tasks est conçu pour gérer facilement des projets de toute taille.

### Q : Puis-je personnaliser les données du projet avec Aspose.Tasks ?

R : Oui, vous pouvez manipuler les données du projet, modifier les tâches, les ressources et bien plus encore avec Aspose.Tasks.

### Q : Aspose.Tasks nécessite-t-il l’installation de Microsoft Project ?

R : Non, Aspose.Tasks fonctionne indépendamment et ne nécessite pas l’installation de Microsoft Project.

### Q : Une assistance technique est-elle disponible pour Aspose.Tasks ?

R : Oui, vous pouvez obtenir de l’aide sur le forum Aspose.Tasks à l’adresse [ici](https://forum.aspose.com/c/tasks/15).

### Questions/Réponses supplémentaires

**Q : Comment récupérer d’autres propriétés du projet (par exemple, l’auteur, l’entreprise) ?**

R : Utilisez `project.get(Prj.AUTHOR)` ou `project.get(Prj.COMPANY)`, comme dans l’exemple de version.

**Q : Puis-je vérifier la version d’un fichier MPP (format binaire) ?**

R : Oui, Aspose.Tasks peut charger directement les fichiers `.mpp` ; la propriété `Prj.SAVE_VERSION` fonctionne également.

**Q : Existe-t-il un moyen de mettre à jour par programmation un ancien fichier de projet vers une version plus récente ?**

R : Chargez l’ancien fichier, puis enregistrez-le avec `project.save("newfile.mpp", SaveFileFormat.MPP);`. Aspose.Tasks l’enregistre par défaut au format le plus récent.

## Conclusion
Vous venez de terminer un tutoriel concis sur **Aspose Tasks Java** qui explique **comment déterminer la version d'un projet** MS Project à l'aide d'Aspose.Tasks pour Java. Intégrez cet extrait de code dans des flux de travail d'automatisation, des outils de reporting ou des utilitaires de migration plus complexes afin de toujours connaître la version exacte du projet que vous utilisez.

---

**Dernière mise à jour :** 25/12/2025

**Testé avec :** Aspose.Tasks pour Java 24.11

**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}