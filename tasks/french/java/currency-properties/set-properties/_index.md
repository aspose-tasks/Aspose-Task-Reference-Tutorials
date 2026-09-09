---
date: 2026-09-09
description: Apprenez comment modifier le symbole monétaire dans les projets Aspose.Tasks
  Java, définir les codes de devise, ajuster les symboles et appliquer des formats
  personnalisés pour les fichiers Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Définir les propriétés monétaires dans les projets Aspose.Tasks
og_description: Comment modifier le symbole monétaire dans Aspose.Tasks avec Java.
  Découvrez des instructions étape par étape, les prérequis et des astuces pour personnaliser
  le format des coûts du projet.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Comment modifier le symbole monétaire dans Aspose.Tasks – guide Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Comment modifier le symbole monétaire dans les projets Aspose.Tasks – guide
  Java
url: /fr/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier le symbole monétaire dans Aspose.Tasks – guide Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment modifier le symbole monétaire** d’un fichier Microsoft Project en utilisant l’API Aspose.Tasks Java. Que vous prépariez des rapports pour un client étranger, consolidiez des budgets à travers plusieurs régions, ou que vous ayez simplement besoin d’aligner vos standards comptables, ajuster le symbole monétaire garantit que chaque champ lié aux coûts affiche le signe monétaire correct. Le guide parcourt chaque étape, de la configuration de l’environnement de développement à la persistance des modifications dans un nouveau fichier de projet ou un fichier existant.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java.  
- **Puis-je modifier le symbole monétaire ?** Oui – définissez `Prj.CURRENCY_SYMBOL` et choisissez `CurrencySymbolPositionType`.  
- **Quels formats de fichiers sont pris en charge ?** XML, MPP, et bien d’autres via `SaveFileFormat`.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour une configuration de base.

## Comment modifier le symbole monétaire dans Aspose.Tasks avec Java ?
Chargez le projet cible (ou créez‑en un nouveau), définissez les propriétés monétaires souhaitées, puis enregistrez le fichier. L’opération complète se résume à trois appels API : créer ou charger un objet `Project`, attribuer le code, le symbole et la position de la monnaie, puis appeler `project.save`. Cette approche fonctionne tant pour les projets neufs que pour les fichiers existants, sans nécessiter l’installation de Microsoft Project.

## Pourquoi utiliser Aspose.Tasks pour modifier la monnaie ?
Aspose.Tasks offre **une couverture API complète pour plus de 30 propriétés liées à la monnaie**, vous permettant de définir le code, le symbole, les décimales et le positionnement en un seul endroit. La bibliothèque traite des fichiers Project de plusieurs centaines de pages en moins d’une seconde sur du matériel serveur typique, et fonctionne sous Windows, Linux et macOS sans dépendances supplémentaires.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK) 8 ou supérieur** – l’API nécessite au moins JDK 8.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA, ou tout éditeur supportant Java.  
4. **Un dossier accessible en écriture** – où le fichier de projet généré sera enregistré.

## Importer les packages
Les classes suivantes vous donnent accès aux propriétés du projet, à la gestion des fichiers et aux paramètres monétaires.  

`Project` – représente un fichier Microsoft Project en mémoire.  
`Prj` – contient les constantes pour toutes les propriétés au niveau du projet, y compris les champs monétaires.  
`CurrencySymbolPositionType` – énumère les positions possibles du symbole monétaire (avant ou après le montant).  

Ces imports sont requis avant que tout code ne puisse manipuler un projet.

## Guide étape par étape

### Étape 1 : Définir le répertoire de données
Choisissez un dossier qui contient vos fichiers sources et où la sortie sera écrite. Assurez‑vous que le répertoire existe et que votre processus Java possède les droits d’écriture.

### Étape 2 : Créer une nouvelle instance de projet
La classe `Project` est l’objet de haut niveau d’Aspose.Tasks qui représente un fichier Project unique en mémoire. L’instancier crée un projet vierge prêt à être configuré.

### Étape 3 : Définir les propriétés monétaires
Ici vous configurez le code monétaire, le nombre de décimales, le symbole lui‑même et la position du symbole.  

- **Code monétaire** – un code ISO 4217 à trois lettres tel que `AUD` ou `USD`.  
- **Chiffres décimaux** – généralement 2 pour la plupart des monnaies.  
- **Symbole monétaire** – le caractère ou la chaîne affichée avec les montants, par ex. `$` ou `€`.  
- **Position du symbole** – `CurrencySymbolPositionType.Before` place le symbole avant le nombre ; `After` le place après.  

Ces paramètres affectent chaque champ lié aux coûts (taux des ressources, budgets des tâches, etc.) dans le projet.

> **Astuce :** Si vous devez modifier la monnaie d’un fichier existant, chargez‑le avec `new Project("file.mpp")` avant d’appliquer les paramètres ci‑dessus.

### Étape 4 : Enregistrer le projet mis à jour
Écrivez le projet sur le disque en utilisant le format souhaité. Le format XML est lisible par l’homme, tandis que `SaveFileFormat.MPP` préserve la pleine compatibilité avec Microsoft Project.

### Étape 5 : Confirmer le succès
Affichez un court message ou une entrée de journal afin de savoir que l’opération s’est terminée sans erreur. Ceci est particulièrement utile dans les pipelines automatisés.

## Problèmes courants & solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **`NullPointerException` on `project.save`** | `dataDir` n’est pas un chemin valide ou n’a pas les permissions d’écriture. | Assurez‑vous que le répertoire existe et que votre processus Java a les droits d’écriture. |
| **Currency symbol not showing** | La position du symbole est définie de manière incorrecte pour votre paramètre régional. | Utilisez `CurrencySymbolPositionType.Before` si le symbole doit précéder le montant. |
| **Project file does not open in MS Project** | Enregistrement dans un format plus ancien avec des paramètres incompatibles. | Enregistrez en utilisant `SaveFileFormat.MPP` pour une compatibilité totale avec les versions récentes de MS Project. |

## Questions fréquemment posées

**Q : Puis‑je définir plusieurs monnaies dans un même projet avec Aspose.Tasks ?**  
R : Oui, vous pouvez attribuer différents paramètres monétaires à des ressources ou tâches individuelles en modifiant leurs champs de coût respectifs après avoir défini la monnaie au niveau du projet.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. La bibliothèque prend en charge les fichiers MPP de Project 2000 jusqu’aux dernières versions, ainsi que les formats XML et autres formats d’échange.

**Q : Aspose.Tasks propose‑t‑il une prise en charge des formats monétaires personnalisés ?**  
R : Oui, vous pouvez définir des symboles personnalisés, le nombre de décimales et le positionnement pour répondre à toute exigence régionale, et ces paramètres sont persistés dans le fichier enregistré.

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres frameworks Java ?**  
R : Bien sûr. L’API est purement Java, elle s’intègre donc parfaitement avec Spring, Hibernate, Maven, Gradle et d’autres écosystèmes.

**Q : Où puis‑je trouver de l’aide supplémentaire ou des exemples ?**  
R : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour l’assistance communautaire, ou consultez la documentation officielle pour des références API détaillées.

## Conclusion
Vous savez maintenant **comment modifier le symbole monétaire** dans les projets Aspose.Tasks avec Java, comment définir le code monétaire, ajuster les décimales et appliquer un symbole personnalisé. Ces capacités vous permettent de générer des rapports de coûts adaptés à chaque locale, d’aligner les budgets de projet avec les normes comptables régionales et de garder vos fichiers Microsoft Project cohérents au sein d’équipes mondiales.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Tutoriels associés

- [propriétés du projet java – Extraire le symbole monétaire d’un MPP avec Aspose.Tasks pour Java](/tasks/java/currency/currency-symbols/)
- [Lire les propriétés monétaires Java avec les projets Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Gérer les codes monétaires Java avec Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}