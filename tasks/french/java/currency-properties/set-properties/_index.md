---
date: 2025-12-04
description: Apprenez à définir la devise dans les projets Aspose.Tasks Java, y compris
  comment changer la devise et le symbole de devise en Java. Manipulez les fichiers
  Microsoft Project sans effort.
language: fr
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Comment définir la devise dans les projets Aspose.Tasks – Guide Java
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la devise dans les projets Aspose.Tasks – Guide Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir la devise** d’un fichier Microsoft Project à l’aide de l’API Aspose.Tasks pour Java. Que vous ayez besoin de *modifier la devise* pour des équipes internationales ou d’ajuster le *symbole monétaire* en Java, les étapes ci‑dessous vous guideront avec des explications claires et du code prêt à l’emploi.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java.  
- **Puis‑je changer le symbole monétaire ?** Oui – utilisez `CurrencySymbolPositionType` et `Prj.CURRENCY_SYMBOL`.  
- **Quels formats de fichier sont pris en charge ?** XML, MPP et bien d’autres via `SaveFileFormat`.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise en production.  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour une configuration de base.

## Qu’est‑ce que la « devise » dans un fichier Project ?
La devise d’un projet définit la façon dont les valeurs monétaires sont affichées : code (p. ex. `AUD`), nombre de décimales, symbole (`$`) et position du symbole. Définir ces propriétés garantit que chaque champ lié aux coûts (taux des ressources, budgets des tâches, etc.) reflète le format monétaire correct pour votre audience.

## Pourquoi utiliser Aspose.Tasks pour changer la devise ?
- **Pas d’installation de Microsoft Project requise** – manipulez les fichiers sur n’importe quel serveur.  
- **Couverture complète de l’API** – tous les champs liés à la devise sont exposés via les constantes `Prj`.  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS avec n’importe quel IDE compatible Java.  
- **Haute performance** – traite rapidement et de manière fiable de gros fichiers de projet.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks pour Java** – téléchargez le JAR le plus récent depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA ou tout autre éditeur de votre choix.  
4. **Un dossier accessible en écriture** – où le fichier de projet généré sera enregistré.

## Importer les packages
Tout d’abord, importez les classes qui donnent accès aux propriétés du projet et à la gestion des fichiers.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de données
Spécifiez le dossier qui contient vos fichiers source et où la sortie sera écrite.

```java
String dataDir = "Your Data Directory";
```

### Étape 2 : Créer une nouvelle instance de projet
Instanciez un nouvel objet `Project`. Cet objet représente fichier Microsoft Project en mémoire.

```java
Project project = new Project();
```

### Étape 3 : Définir les propriétés de la devise
C’est ici que nous **définissons la devise** : code, décimales, symbole et position du symbole.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Astuce :** Si vous devez **modifier la devise** d’un projet existant, chargez simplement le fichier avec `new Project("file.mpp")` avant d’appliquer les paramètres ci‑dessus.

### Étape 4 : Enregistrer le projet mis à jour
Écrivez le projet sur le disque dans le format souhaité. Dans cet exemple nous utilisons le format XML, mais vous pouvez également choisir `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Étape 5 : Confirmer le succès
Affichez un message convivial pour savoir que l’opération s’est terminée sans erreurs.

```java
System.out.println("Process completed Successfully");
```

## Problèmes courants & solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`NullPointerException` sur `project.save`** | `dataDir` n’est pas un chemin valide ou n’a pas les droits d’écriture. | Vérifiez que le répertoire existe et que votre processus Java possède les droits d’écriture. |
| **Le symbole monétaire n’apparaît pas** | La position du symbole est mal configurée pour votre locale. | Utilisez `CurrencySymbolPositionType.Before` si le symbole doit précéder le montant. |
| **Le fichier projet ne s’ouvre pas dans MS Project** | Enregistrement dans un format ancien avec des paramètres incompatibles. | Enregistrez avec `SaveFileFormat.MPP` pour une compatibilité totale avec les versions récentes de MS Project. |

## Foire aux questions

**Q : Puis‑je définir plusieurs devises dans un même projet avec Aspose.Tasks ?**  
R : Oui, Aspose.Tasks vous permet de gérer plusieurs devises au sein d’un même fichier projet en définissant les propriétés de devise au niveau de chaque ressource ou tâche.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. La bibliothèque prend en charge les fichiers MPP de Project 2000 jusqu’aux dernières versions, ainsi que les formats XML et d’autres formats.

**Q : Aspose.Tasks propose‑t‑il la prise en charge de formats de devise personnalisés ?**  
R : Oui, vous pouvez définir des symboles personnalisés, le nombre de décimales et la position du symbole pour répondre à n’importe quelle exigence régionale.

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres bibliothèques ou frameworks Java ?**  
R : Bien sûr. L’API est purement Java, elle s’intègre donc parfaitement avec Spring, Hibernate, Maven, Gradle et d’autres écosystèmes.

**Q : Où puis‑je trouver une assistance supplémentaire pour Aspose.Tasks ?**  
R : Consultez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide de la communauté, ou référez‑vous à la documentation officielle pour des références détaillées de l’API.

## Conclusion
Vous savez maintenant **comment définir la devise**, comment **modifier les valeurs monétaires** et comment **modifier le symbole monétaire en Java** à l’aide d’Aspose.Tasks pour Java. Ces capacités vous permettent d’adapter les données de coût pour des équipes mondiales, de générer des rapports spécifiques à une locale et de garder vos fichiers projet cohérents à l’échelle internationale.

---

**Dernière mise à jour :** 2025-12-04  
**Testé avec :** Aspose.Tasks pour Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}