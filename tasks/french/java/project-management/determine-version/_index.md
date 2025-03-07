---
title: Déterminer la version de MS Project avec Aspose.Tasks
linktitle: Déterminer la version du projet avec Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment déterminer la version des fichiers MS Project par programme à l'aide d'Aspose.Tasks pour Java. Guide étape par étape avec des exemples de code.
weight: 12
url: /fr/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Déterminer la version de MS Project avec Aspose.Tasks

## Introduction
Ce didacticiel vous guidera dans l'utilisation d'Aspose.Tasks pour Java pour déterminer étape par étape la version d'un fichier MS Project. Aspose.Tasks est une API Java puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Fichier JAR Aspose.Tasks for Java : téléchargez la bibliothèque Aspose.Tasks for Java à partir du[site web](https://releases.aspose.com/tasks/java/) et ajoutez-le à votre projet Java.
3. Fichier MS Project : préparez un fichier MS Project (format XML) pour les tests.

## Importer des packages
Avant de plonger dans le code, importons les packages nécessaires :
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Étape 1 : configurer le projet
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès au répertoire contenant votre fichier MS Project.
## Étape 2 : Charger le projet
```java
Project project = new Project(dataDir + "input.xml");
```
 Remplacer`"input.xml"` avec le nom de votre fichier MS Project.
## Étape 3 : Déterminer la version du projet
```java
//Afficher la propriété de la version du projet
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Cet extrait de code récupère et imprime la version et la date du dernier enregistrement du fichier MS Project.
## Étape 4 : Afficher le résultat
```java
//Afficher le résultat de la conversion.
System.out.println("Process completed Successfully");
```
Cette ligne indique la fin du processus.

## Conclusion
Dans ce didacticiel, vous avez appris à déterminer la version d'un fichier MS Project à l'aide d'Aspose.Tasks pour Java. En suivant le guide étape par étape, vous pouvez travailler efficacement et sans problème avec les fichiers MS Project dans vos applications Java.

## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres langages de programmation ?
R : Oui, Aspose.Tasks prend en charge plusieurs langages de programmation, notamment .NET, Java et C.++.
### Q : Aspose.Tasks est-il adapté aux projets à grande échelle ?
: Absolument, Aspose.Tasks est conçu pour gérer facilement des projets de toute taille.
### Q : Puis-je personnaliser les données du projet à l’aide d’Aspose.Tasks ?
R : Oui, vous pouvez manipuler les données du projet, modifier les tâches, les ressources et bien plus encore à l'aide d'Aspose.Tasks.
### Q : Aspose.Tasks nécessite-t-il l'installation de Microsoft Project ?
R : Non, Aspose.Tasks fonctionne de manière indépendante et ne nécessite pas l'installation de Microsoft Project.
### Q : Le support technique est-il disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez obtenir une assistance technique sur le forum Aspose.Tasks à l'adresse[ici](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
