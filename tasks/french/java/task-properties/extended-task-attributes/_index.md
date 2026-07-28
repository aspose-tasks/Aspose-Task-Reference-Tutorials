---
date: 2026-01-28
description: Apprenez à lire les attributs de tâche étendus à l’aide d’Aspose.Tasks
  pour Java et à changer le type de champ personnalisé efficacement.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Lire les attributs de tâche étendus avec Aspose.Tasks pour Java
url: /fr/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les attributs de tâche étendus avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel complet, vous découvrirez comment **lire les attributs de tâche étendus** à partir de fichiers Microsoft Project en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un outil de reporting, synchronisiez des données ou ayez simplement besoin d’une compréhension plus approfondie des champs personnalisés, maîtriser cette fonctionnalité vous permettra d’extraire chaque information stockée dans un projet. Nous parcourrons la configuration requise, vous montrerons comment changer le type de champ personnalisé lors du traitement des attributs, et vous donnerons des conseils pratiques pour éviter les pièges courants.

## Réponses rapides
- **Que signifie « lire les attributs de tâche étendus » ?** Il s’agit d’extraire les valeurs des champs personnalisés qui vont au‑delà des propriétés de tâche par défaut dans un fichier Project.  
- **Quelle classe donne accès à ces attributs ?** La classe `ExtendedAttribute` dans Aspose.Tasks.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je changer le type d’attribut à l’exécution ?** Oui – utilisez l’instruction `switch` pour **changer le type de champ personnalisé** en fonction de `CustomFieldType`.  
- **Cette fonctionnalité est‑elle compatible avec Java 8 et versions ultérieures ?** Absolument, l’API prend en charge JDK 8+.

## Qu'est-ce que la lecture des attributs de tâche étendus ?
Les attributs de tâche étendus sont des champs définis par l'utilisateur (texte, date, nombre, indicateur, etc.) qui complètent les propriétés de tâche standard dans Microsoft Project. Aspose.Tasks les expose via la collection `ExtendedAttribute` attachée à chaque objet `Task`, vous permettant de lire ou de modifier leurs valeurs de façon programmatique.

## Pourquoi lire les attributs de tâche étendus ?
- **Visibilité totale :** Obtenez des informations sur les données personnalisées ajoutées par les parties prenantes au planning.  
- **Automatisation :** Alimentez des tableaux de bord, générez des rapports personnalisés ou migrez des données vers d’autres systèmes sans exportation manuelle.  
- **Flexibilité :** Travaillez avec n’importe quel type de champ personnalisé — texte, date, durée, coût, indicateur—en gérant chaque cas de manière appropriée.

## Prérequis
- Connaissances de base en programmation Java.  
- Java Development Kit (JDK) installé sur votre machine.  
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.  

## Importer les packages
Commencez par importer les classes nécessaires pour le projet Aspose.Tasks :

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Étape 1 : Accéder aux tâches et aux attributs étendus
Chargez un fichier Project et parcourez chaque tâche pour atteindre ses attributs étendus :

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Étape 2 : Récupérer l'ID du champ et le GUID de la valeur
Affichez les identifiants internes qui vous aident à comprendre quel champ personnalisé vous traitez :

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Étape 3 : Comment changer le type de champ personnalisé lors de la lecture des attributs de tâche étendus
Utilisez une instruction `switch` sur `CustomFieldType` pour gérer correctement chaque type de donnée possible :

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Répétez ces étapes pour chaque tâche de votre projet afin d’explorer et de manipuler chaque attribut de tâche étendu.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Valeurs null retournées** | Vérifiez que le champ personnalisé est réellement renseigné dans le fichier .mpp source. |
| **Type affiché incorrect** | Assurez‑vous d’utiliser le bon `CustomFieldType` dans l’instruction `switch` ; des types incompatibles entraîneront des valeurs par défaut. |
| **Ralentissement des performances sur de gros projets** | Traitez les tâches par lots ou filtrez uniquement les tâches nécessaires en utilisant `project.getRootTask().getChildren().stream()` avec les prédicats appropriés. |

## Questions fréquemment posées
### Puis‑je modifier les attributs de tâche étendus par programme ?
Oui, vous pouvez modifier les attributs de tâche étendus en utilisant Aspose.Tasks pour Java. Consultez la documentation pour des instructions détaillées.

### Une version d'essai est‑elle disponible ?
Oui, vous pouvez accéder à la version d’essai gratuite [ici](https://releases.aspose.com/).

### Où puis‑je trouver du support pour Aspose.Tasks pour Java ?
Pour le support, visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Comment obtenir une licence temporaire ?
Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Où puis‑je acheter la version complète d'Aspose.Tasks pour Java ?
Vous pouvez acheter la version complète [ici](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-01-28  
**Testé avec :** Aspose.Tasks Java API (dernière version stable)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}