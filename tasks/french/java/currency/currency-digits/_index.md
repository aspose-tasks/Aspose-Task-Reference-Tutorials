---
date: 2026-02-10
description: Apprenez à obtenir les valeurs monétaires, à lire un fichier MS Project
  et à convertir le fichier de projet Java à l’aide d’Aspose.Tasks. Guide étape par
  étape pour extraire les chiffres de la devise.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment obtenir la devise depuis MS Project avec Aspose.Tasks
url: /fr/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir la devise à partir de MS Project avec Aspose.Tasks

## Introduction
Si vous vous demandez **comment obtenir la devise** d'un fichier Microsoft Project, vous êtes au bon endroit. Dans ce tutoriel complet, vous découvrirez **comment travailler avec les valeurs de devise de ms project** en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un outil de reporting, une utilité de migration, ou que vous ayez simplement besoin de lire les paramètres de devise d'un **fichier de projet java**, ce guide vous accompagne à chaque étape — du chargement d'un fichier *.mpp* à l'extraction des chiffres de la devise. À la fin, vous serez à l'aise pour manipuler les données de devise de ms project dans vos propres applications.

## Quick Answers
- **Quelle bibliothèque lit les fichiers MS Project ?** Aspose.Tasks for Java.  
- **Combien de lignes de code pour obtenir les chiffres de la devise ?** Juste trois lignes concises après le chargement du projet.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure (tout JDK qui exécute Aspose.Tasks).  
- **Puis-je récupérer d'autres propriétés du projet ?** Oui – Aspose.Tasks expose un ensemble complet de champs du projet (par ex., date de début, taux de coût, etc.).

## Qu'est-ce que la devise de ms project ?
`ms project currency` désigne la précision numérique (nombre de décimales) que Microsoft Project utilise lors de l'affichage des valeurs monétaires. Elle est stockée dans le fichier Project sous la propriété **CURRENCY_DIGITS** et détermine si les montants apparaissent comme des nombres entiers, à une décimale, deux décimales, etc.

## Pourquoi utiliser Aspose.Tasks pour gérer la devise de ms project ?
- **Aucune installation de Microsoft Project requise** – travaillez directement avec des fichiers *.mpp* sur n'importe quelle plateforme supportant Java.  
- **Sécurité de typage forte** – l'API renvoie des valeurs fortement typées, réduisant les erreurs d'analyse.  
- **Optimisé pour la performance** – chargez rapidement de grands projets et extrayez uniquement les champs dont vous avez besoin.  
- **Cross‑platform** – exécutez sur Windows, Linux ou macOS sans modification.

## Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. **Environnement de développement Java** – JDK 8 ou plus récent installé et configuré.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis le site officiel : [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – vous devez être à l'aise pour créer un projet Java, ajouter des bibliothèques externes et exécuter une méthode `main`.  

## Importer les packages
Tout d'abord, importez les classes dont nous aurons besoin.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : Définir le répertoire de données
Spécifiez le dossier qui contient votre **fichier de projet java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu ou relatif où se trouve `project.mpp`.

## Étape 2 : Charger le fichier MPP  
Nous allons maintenant voir **comment charger des fichiers mpp** avec Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assurez‑vous que le nom du fichier correspond exactement ; sinon, une `IOException` sera levée.

## Étape 3 : Récupérer les chiffres de la devise  
Une fois le projet chargé, extraire les chiffres de la **devise ms project** se fait en une seule ligne :  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
L'appel renvoie un `Integer` représentant le nombre de décimales (par ex., `2` pour les centimes). La valeur est affichée dans la console, mais vous pouvez également la stocker dans une variable pour un traitement ultérieur.

## Problèmes courants et conseils
- **Fichier non trouvé** – vérifiez à nouveau le chemin `dataDir` et assurez‑vous que le nom du fichier est correct, y compris l'extension `.mpp`.  
- **Version de fichier non prise en charge** – Aspose.Tasks prend en charge les formats Project 2000‑2024 ; les fichiers plus anciens ou corrompus peuvent nécessiter une conversion.  
- **Licence non définie** – pendant le développement, un essai fonctionne, mais en production vous devez appliquer une licence valide pour éviter les filigranes d'évaluation.

## Questions fréquentes

**Q : Aspose.Tasks peut‑il gérer d'autres attributs du projet en plus des chiffres de devise ?**  
R : Oui, Aspose.Tasks offre un large éventail de fonctionnalités pour manipuler divers aspects des fichiers Project, tels que les tâches, les ressources et les champs personnalisés.

**Q : Aspose.Tasks est‑il adapté aux applications de niveau entreprise ?**  
R : Absolument, Aspose.Tasks est conçu pour répondre aux exigences des projets de niveau entreprise, offrant haute performance et évolutivité.

**Q : Aspose.Tasks prend‑il en charge le développement multiplateforme ?**  
R : Oui, vous pouvez utiliser Aspose.Tasks pour Java sur n'importe quelle plateforme supportant le Java Runtime Environment (Windows, Linux, macOS).

**Q : Puis‑je essayer Aspose.Tasks avant d'acheter ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Vous pouvez trouver du support sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusion
Vous savez maintenant **comment obtenir les chiffres de la devise** à partir d'un fichier MS Project avec Aspose.Tasks pour Java. Le processus est simple : chargez le projet, appelez `project.get(Prj.CURRENCY_DIGITS)`, et utilisez le résultat dans votre application. N'hésitez pas à explorer d'autres propriétés du projet avec le même modèle, et à intégrer cette logique dans des solutions de reporting ou de migration plus larges.

---

**Dernière mise à jour :** 2026-02-10  
**Testé avec :** Aspose.Tasks for Java (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}