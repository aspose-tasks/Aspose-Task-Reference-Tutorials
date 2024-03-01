---
title: Attributs de tâches étendus dans Aspose.Tasks
linktitle: Attributs de tâches étendus dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explorez les attributs de tâches étendus dans Aspose.Tasks pour Java. Guide étape par étape, FAQ et assistance. Optimisez votre gestion de projet dès aujourd'hui !
type: docs
weight: 16
url: /fr/java/task-properties/extended-task-attributes/
---
## Introduction
Bienvenue dans notre guide complet sur l'exploitation des attributs de tâches étendus dans Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java qui vous permet de travailler de manière transparente avec les documents Microsoft Project. Dans ce didacticiel, nous approfondirons les attributs de tâches étendus et démontrerons comment vous pouvez les utiliser pour améliorer vos capacités de gestion de projet.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Connaissance de base de la programmation Java.
- Kit de développement Java (JDK) installé sur votre ordinateur.
- Un environnement de développement intégré (IDE) tel qu'IntelliJ ou Eclipse.
## Importer des packages
Commencez par importer les packages nécessaires pour lancer votre projet Aspose.Tasks :
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Maintenant, décomposons l'exemple en plusieurs étapes pour vous guider tout au long du processus :
## Étape 1 : accès aux tâches et aux attributs étendus
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Étape 2 : Récupération de l'ID de champ et du GUID de valeur
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Étape 3 : Gestion de différents types d'attributs
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
Répétez ces étapes pour chaque tâche de votre projet afin d'explorer et de manipuler les attributs de tâche étendus.
## Conclusion
En conclusion, comprendre et utiliser les attributs de tâches étendus dans Aspose.Tasks pour Java peut améliorer considérablement vos capacités de gestion de projet. Ce guide fournit une base solide pour vous lancer dans ce voyage.
## Questions fréquemment posées
### Puis-je modifier les attributs de tâches étendus par programme ?
Oui, vous pouvez modifier les attributs de tâches étendus à l'aide d'Aspose.Tasks pour Java. Reportez-vous à la documentation pour des instructions détaillées.
### Existe-t-il une version d'essai disponible ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.Tasks pour Java ?
 Pour obtenir de l'aide, visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Comment puis-je obtenir un permis temporaire ?
 Vous pouvez obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter la version complète d’Aspose.Tasks pour Java ?
 Vous pouvez acheter la version complète[ici](https://purchase.aspose.com/buy).