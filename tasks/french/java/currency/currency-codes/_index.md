---
date: 2026-02-10
description: Apprenez comment récupérer les codes de devise à partir des fichiers
  MS Project en utilisant Aspose.Tasks pour Java – la façon rapide d’obtenir le code
  de devise dont les développeurs Java ont besoin.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment récupérer la devise de MS Project avec Aspose.Tasks
url: /fr/java/currency/currency-codes/
weight: 10
---

 content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment récupérer la devise à partir de MS Project avec Aspise.Tasks

## Introduction
Bienvenue ! Dans ce tutoriel, vous découvrirez **comment récupérer la devise** à partir d'un fichier MS Project en utilisant l'API Java d'Aspose.Tasks. Que vous génériez des rapports financiers multi‑devises, consolidiez des projets provenant de différentes régions, ou ayez simplement besoin des symboles monétaires corrects pour le traitement en aval, ce guide vous accompagne à chaque étape — de la configuration de votre environnement à l'extraction du code de devise de façon programmatique. À la fin, vous serez à l'aise pour lire les fichiers MS Project et utiliser l'appel **get currency code java** afin d'obtenir l'identifiant ISO de la devise.

## Quick Answers
- **Que fait l'API ?** Elle lit les fichiers MS Project et expose des propriétés telles que le code de devise.  
- **Quel langage est utilisé ?** Java, via la bibliothèque Aspose.Tasks pour Java.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je récupérer le code en une seule ligne ?** Oui — `prj.get(Prj.CURRENCY_CODE)` renvoie la chaîne du code de devise.  
- **Est‑il compatible avec toutes les versions de Project ?** Aspose.Tasks prend en charge les formats anciens (MPP) et récents (XML, XER).

## What is **read ms project file**?
Lire un fichier MS Project signifie ouvrir de façon programmatique un document de projet *.mpp* (ou tout autre format supporté) et accéder à ses structures de données — tâches, ressources, calendriers et paramètres financiers — sans interaction manuelle avec Microsoft Project lui‑même.

## Why use Aspose.Tasks to **read msproject** files?
- **Prise en charge complète des formats** – fonctionne avec les fichiers de Project 98 jusqu'aux dernières versions d'Office.  
- **Pas besoin d'installation COM ou Office** – Java pur, idéal pour l'automatisation côté serveur.  
- **API riche** – donne un accès direct aux propriétés comme `Prj.CURRENCY_CODE`, vous permettant d'obtenir instantanément les informations **how to retrieve currency**.  
- **Performance** – analyse légère, idéale pour le traitement par lots de nombreux projets.

## Prerequisites
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Java Development Kit (JDK) Installed
Assurez‑vous qu'un JDK récent est disponible sur votre machine. Vous pouvez télécharger et installer la dernière version du JDK depuis [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
Téléchargez et configurez la bibliothèque Aspose.Tasks pour Java. La documentation détaillée et les dernières binaires sont disponibles [here](https://reference.aspose.com/tasks/java/).

## Import Packages
Pour commencer, importons les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
Définissez le dossier contenant votre fichier *.mpp*. Ajustez le chemin pour qu'il corresponde à votre environnement.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Créez une instance `Project` en chargeant le fichier MS Project. C’est à ce moment que vous **read msproject** les données en mémoire.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
Maintenant que le projet est chargé, vous pouvez obtenir les informations **how to retrieve currency** avec un appel unique. Cela montre l’utilisation de **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
La sortie sera le code ISO à trois lettres (par ex., `USD`, `EUR`, `GBP`) que le projet a configuré.

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
Si vous devez stocker la valeur pour une utilisation ultérieure, assignez‑la simplement à une variable :

*No extra code block is required* – just keep the string returned by `prj.get(Prj.CURRENCY_CODE)` and pass it to any financial service, reporting engine, or UI component.

### Step 5: (Optional) Use the Currency Code
Vous pourriez vouloir appliquer le code récupéré ailleurs — par exemple pour formater les valeurs de coût dans un rapport personnalisé ou le transmettre à une API financière. Les scénarios typiques incluent :

- **Génération de rapports** – préfixez le code aux colonnes de coût (`USD 1,200`).
- **Intégration d'API** – envoyez le code ISO aux passerelles de paiement qui nécessitent un identifiant de devise.
- **Consolidation de données** – regroupez plusieurs projets par devise pour l'analyse de portefeuille.

## Common Issues and Solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Sortie nulle** | Le fichier projet ne définit pas de devise (la valeur par défaut est vide). | Définissez la devise dans Microsoft Project ou assignez‑la via `prj.set(Prj.CURRENCY_CODE, "USD");` avant la lecture. |
| **Fichier introuvable** | Chemin `dataDir` incorrect. | Vérifiez le chemin et assurez‑vous que le nom du fichier correspond exactement, y compris la sensibilité à la casse. |
| **Version de fichier non prise en charge** | Fichier *.mpp* très ancien ou corrompu. | Utilisez la dernière version d'Aspose.Tasks ou convertissez le fichier dans un format plus récent avec Microsoft Project d'abord. |

## Frequently Asked Questions

**Q : Aspose.Tasks peut‑il gérer des structures de projet complexes ?**  
R : Oui, l'API peut lire et manipuler des hiérarchies de tâches à plusieurs niveaux, des pools de ressources et des champs personnalisés sans problème.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers MS Project ?**  
R : Absolument. Il prend en charge les formats MPP, XML, XER et autres sur de nombreuses versions de Microsoft Project.

**Q : Aspose.Tasks fournit‑il de la documentation et du support ?**  
R : Une documentation complète, des exemples de code et un support dédié sont disponibles sur le site d'Aspose.

**Q : Puis‑je essayer Aspose.Tasks avant d'acheter ?**  
R : Un essai gratuit est proposé afin d'évaluer toutes les fonctionnalités, y compris la lecture des codes de devise.

**Q : Où puis‑je obtenir des licences temporaires pour Aspose.Tasks ?**  
R : Des licences temporaires peuvent être obtenues depuis le [website](https://purchase.aspose.com/temporary-license/) pour une évaluation à court terme.

---

**Dernière mise à jour :** 2026-02-10  
**Testé avec :** Aspose.Tasks for Java (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}