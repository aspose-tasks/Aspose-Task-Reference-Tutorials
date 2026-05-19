---
date: 2026-01-15
description: Apprenez à travailler avec le travail à coût budgété planifié dans les
  fichiers Microsoft Project en utilisant Aspose.Tasks pour Java. Suivez notre guide
  étape par étape.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Travail de coût budgété planifié avec Aspose.Tasks pour Java
url: /fr/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# coût budgété du travail planifié avec Aspose.Tasks pour Java

## Introduction

La gestion du **budgeted cost work scheduled** (BCWS) est essentielle pour maintenir un projet sur la bonne voie et garantir que les prévisions financières sont alignées avec le travail planifié. Dans Microsoft Project, BCWS représente le montant d'argent qui aurait dû être dépensé pour le travail programmé jusqu'à une date donnée. Aspose.Tasks pour Java vous offre un contrôle programmatique complet sur ces valeurs, vous permettant de lire, modifier et rapporter les coûts des ressources sans jamais ouvrir le fichier .mpp manuellement. Dans ce tutoriel, nous parcourrons un exemple complet montrant comment charger un projet, itérer sur ses ressources et afficher le budgeted cost work scheduled aux côtés d'autres indicateurs de coût clés.

## Quick Answers
- **What does BCWS mean?** Budgeted Cost Work Scheduled – the planned cost for work scheduled to date.  
- **Which API property retrieves BCWS?** `Rsc.BCWS` on a `Resource` object.  
- **Do I need a license to run the sample?** A free evaluation license works for testing; a full license is required for production.  
- **Can I modify BCWS values?** Yes, you can set `Rsc.BCWS` just like any other numeric field.  
- **Supported Project versions?** All Microsoft Project versions from 2000 to the latest .mpp format.

## What is budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** est une mesure de performance qui reflète le coût qui aurait dû être engagé pour le travail planifié jusqu'à un moment donné. C’est un pilier de l’Earned Value Management (EVM) et aide les chefs de projet à comparer les dépenses prévues aux dépenses réelles.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d’avoir :

1. Une bonne maîtrise des fondamentaux de Java.  
2. Aspose.Tasks pour Java ajouté à votre projet (Maven/Gradle ou JAR).  
3. Un fichier Microsoft Project (`.mpp`) contenant des ressources avec des données de coût (par ex., *ResourceCosts.mpp*).

## Import Packages

Tout d’abord, importez les classes Aspose.Tasks nécessaires à la gestion des projets et des ressources :

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Define the Data Directory

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu ou relatif où se trouve *ResourceCosts.mpp*.

## Step 2: Load the MS Project File

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Le constructeur `Project` lit le fichier .mpp et crée une représentation en mémoire que vous pouvez interroger.

## Step 3: Iterate Through Resources

```java
for (Resource res : prj.getResources()) {
```

Cette boucle parcourt chaque ressource définie dans le projet, vous donnant accès à ses champs de coût.

## Step 4: Check Resource Name and Costs

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

À l’intérieur du bloc `if` nous :

* Affichons le **total cost** (`Rsc.COST`).  
* Affichons le **actual cost of work performed** (`Rsc.ACWP`).  
* Affichons le **budgeted cost work scheduled** (`Rsc.BCWS`) – la métrique principale sur laquelle nous nous concentrons.  
* Affichons le **budgeted cost work performed** (`Rsc.BCWP`).

Ces quatre valeurs vous offrent un aperçu rapide de la situation financière du projet.

## Why monitoring budgeted cost work scheduled matters

* **Early warning :** Si le BCWS est nettement supérieur au coût réel, vous pourriez sur‑allouer les ressources.  
* **Earned Value Analysis :** Le BCWS est une donnée clé pour calculer le Cost Variance (CV) et le Schedule Variance (SV).  
* **Forecasting :** Des données BCWS précises aident à prévoir les besoins futurs de trésorerie et à informer les rapports aux parties prenantes.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `null` printed for BCWS | Resource has no cost rate table defined | Define a cost rate table for the resource in Microsoft Project or set it programmatically via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` when iterating resources | Project file corrupted or contains empty resource entries | Validate the .mpp file in Microsoft Project and remove empty resources |
| Unexpected values (e.g., negative BCWS) | Custom fields overriding standard cost fields | Ensure you’re accessing the standard `Rsc.BCWS` and not a custom field with the same name |

## Frequently Asked Questions

**Q: Can I update the BCWS value programmatically?**  
A: Yes. Use `res.set(Rsc.BCWS, newValue)` and then save the project with `prj.save("Updated.mpp")`.

**Q: Does Aspose.Tasks support multi‑currency projects?**  
A: Absolutely. Cost fields respect the currency settings defined in the Project file.

**Q: Is there a way to export these cost metrics to CSV?**  
A: You can iterate over the resources and write the values to a `StringBuilder` or use a CSV library to generate the file.

**Q: How does BCWS differ from BCWP?**  
A: BCWS is the planned cost for scheduled work, while BCWP (Budgeted Cost Work Performed) reflects the planned cost for work that has actually been completed.

**Q: Do I need a special license to read cost data?**  
A: The evaluation license provides full read/write access; a commercial license is required for production deployments.

## Conclusion

En exploitant Aspose.Tasks pour Java, vous obtenez un accès précis et programmatique au **budgeted cost work scheduled** ainsi qu’à d’autres indicateurs de coût essentiels. Cela vous permet de créer des tableaux de bord personnalisés, d’automatiser les rapports Earned Value et de garder vos projets financièrement sur la bonne voie—le tout sans interaction manuelle avec Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-15  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest)  
**Auteur :** Aspose