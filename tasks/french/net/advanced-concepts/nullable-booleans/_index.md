---
date: 2026-03-14
description: Apprenez à utiliser les booléens nullables dans Aspose.Tasks pour .NET,
  y compris la conversion des valeurs booléennes nullables et la définition des propriétés
  booléennes nullables.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment utiliser les booléens nullables dans Aspose.Tasks
url: /fr/net/advanced-concepts/nullable-booleans/
weight: 21
---

 if needed" Not needed.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser les booléens nullable dans Aspose.Tasks

Dans ce tutoriel, nous allons montrer **comment utiliser les booléens nullable** lors de l'utilisation de l'API .NET Aspose.Tasks. Les booléens nullable vous offrent trois états possibles — `true`, `false` ou *undefined* — ce qui est particulièrement pratique pour les paramètres au niveau du projet qui ne sont pas explicitement spécifiés. Vous verrez comment créer, convertir et **définir des booléens nullable**, et pourquoi gérer correctement les booléens nullable peut éviter un comportement inattendu dans vos applications de planification.

## Réponses rapides
- **Qu'est‑ce qu'un booléen nullable ?** Un type qui peut contenir `true`, `false`, ou être undefined.  
- **Pourquoi utiliser les booléens nullable dans Aspose.Tasks ?** Ils vous permettent de représenter des propriétés de projet optionnelles sans deviner une valeur par défaut.  
- **Comment convertir un booléen nullable en booléen standard ?** Utilisez la conversion implicite ou vérifiez d'abord `IsDefined`.  
- **Quelle est la classe principale ?** `NullableBool` dans l'espace de noms `Aspose.Tasks`.  
- **Ai‑je besoin d'une licence ?** Oui, une licence valide Aspose.Tasks est requise pour une utilisation en production.

## Qu'est‑ce qu'un booléen nullable ?

Un booléen nullable (`NullableBool`) étend le type `bool` standard en ajoutant un drapeau *IsDefined*. Lorsque `IsDefined` est `false`, la valeur est considérée comme undefined, vous permettant de différencier “false” de “not set”.

## Pourquoi gérer les booléens nullable dans les paramètres du projet ?

De nombreuses options de projet — comme **ActualsInSync** ou **HonorConstraints** — sont optionnelles. Utiliser un `bool` simple vous oblige à choisir `true` ou `false`, ce qui peut écraser involontairement l'intention d'un utilisateur. En **gérant les booléens nullable**, vous préservez l'état original et évitez les changements de configuration accidentels.

## Prérequis

1. **Visual Studio** (ou tout IDE compatible .NET).  
2. **Aspose.Tasks for .NET** – téléchargez-le depuis [here](https://releases.aspose.com/tasks/net/).

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms requis :

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Passons maintenant en revue chaque exemple étape par étape.

## Travailler avec `NullableBool`

### Étape 1 : Créez une nouvelle instance `Project`.

```csharp
var project = new Project();
```

### Étape 2 : Instanciez un objet `NullableBool` avec des valeurs spécifiées.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Étape 3 : Vérifiez la valeur et le statut défini de l'objet `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Étape 4 : **Définir un booléen nullable** sur le projet.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Étape 5 : Instanciez un autre objet `NullableBool` avec une seule valeur.

```csharp
var honorConstraints = new NullableBool(true);
```

### Étape 6 : Affichez la représentation sous forme de chaîne de l'objet `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Étape 7 : Utilisez l'instance `NullableBool` en la définissant dans le projet.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Comparer les instances `NullableBool`

### Étape 1 : Instanciez deux objets `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Étape 2 : Vérifiez la représentation sous forme de chaîne de chaque objet `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Étape 3 : Conversion implicite en `bool` et affichez le résultat.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Étape 4 : Comparez les deux objets `NullableBool` pour l'égalité.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Obtenir le code de hachage de `NullableBool`

### Étape 1 : Instanciez deux objets `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Étape 2 : Affichez le code de hachage de chaque objet `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Pièges courants & conseils

- **Ne jamais supposer qu'un booléen nullable est défini.** Vérifiez toujours `IsDefined` avant d'utiliser `Value`.  
- **Convertir en booléen standard** sans vérification peut lever une exception si la valeur est undefined. Utilisez la conversion implicite uniquement lorsque vous êtes sûr qu'elle est définie.  
- **Lors de la définition des propriétés du projet**, utilisez la méthode `Set` avec un `NullableBool` pour préserver l'état undefined si nécessaire.

## Questions fréquentes

**Q : Qu'est‑ce qu'un booléen nullable ?**  
R : Un booléen nullable peut représenter `true`, `false` ou un état undefined, offrant ainsi trois résultats distincts.

**Q : Comment convertir en toute sécurité un booléen nullable en booléen standard ?**  
R : Vérifiez d'abord `IsDefined`, puis utilisez la propriété `Value` ou reposez-vous sur la conversion implicite lorsque vous êtes certain qu'il est défini.

**Q : Pourquoi devrais‑je utiliser des booléens nullable au lieu de booléens simples dans Aspose.Tasks ?**  
R : Ils vous permettent de laisser les paramètres de projet optionnels intacts, évitant ainsi les écrasements accidentels.

**Q : Puis‑je définir un booléen nullable comme undefined ?**  
R : Oui — utilisez le constructeur qui accepte uniquement le drapeau défini, par ex., `new NullableBool(false, false)`.

**Q : Où puis‑je trouver une documentation supplémentaire sur Aspose.Tasks pour .NET ?**  
R : Vous pouvez trouver une documentation détaillée [here](https://reference.aspose.com/tasks/net/).

---

**Dernière mise à jour :** 2026-03-14  
**Testé avec :** Aspose.Tasks for .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}