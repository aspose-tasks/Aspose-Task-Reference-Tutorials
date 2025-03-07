---
title: Διαχείριση κριτηρίων ομάδας έργου MS με το Aspose.Tasks
linktitle: Διαχείριση συλλογής κριτηρίων ομάδας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τη συλλογή MS Criterion Project χρησιμοποιώντας το Aspose.Tasks για .NET. Οδηγός βήμα προς βήμα για προγραμματιστές.
weight: 28
url: /el/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση κριτηρίων ομάδας έργου MS με το Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks for .NET είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να διαχειριστείτε τη συλλογή Κριτηρίων ομάδας στο MS Project χρησιμοποιώντας το Aspose.Tasks.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1.  Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks στο έργο σας .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).

2. Αρχείο Microsoft Project: Έχετε ένα αρχείο Microsoft Project (MPP) έτοιμο για εργασία.

## Εισαγωγή χώρων ονομάτων

Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στον κώδικα C#. Αυτό το βήμα είναι ζωτικής σημασίας για την πρόσβαση στις λειτουργίες που παρέχονται από το Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Βήμα 1: Φορτώστε το Αρχείο Έργου

 Αρχικοποίηση α`Project` αντικείμενο με τη φόρτωση του αρχείου MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Βήμα 2: Πρόσβαση στα κριτήρια ομάδας

Ανάκτηση της ομάδας από το έργο και πρόσβαση στα κριτήριά της.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Βήμα 3: Επανάληψη των κριτηρίων ομάδας

Περιηγηθείτε σε κάθε κριτήριο της ομάδας και εμφανίστε τις ιδιότητές του.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Βήμα 4: Εκκαθάριση κριτηρίων ομάδας

Διαγράψτε τα υπάρχοντα κριτήρια ομάδας εάν δεν είναι μόνο για ανάγνωση.

```csharp
group.GroupCriteria.Clear();
```

## Βήμα 5: Προσθήκη νέου κριτηρίου

Δημιουργήστε ένα νέο κριτήριο ομάδας και προσθέστε το στην ομάδα.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Βήμα 6: Αντιγραφή κριτηρίων σε άλλη ομάδα

Αντιγράψτε τα κριτήρια από τη μια ομάδα στην άλλη.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να διαχειριζόμαστε τη συλλογή Group Criterion MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε αποτελεσματικά κριτήρια ομάδας στα αρχεία του Microsoft Project μέσω προγραμματισμού.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;

Α: Ναι, το Aspose.Tasks υποστηρίζει αρχεία Microsoft Project διαφόρων εκδόσεων, συμπεριλαμβανομένων των 2003, 2007, 2010, 2013 και 2016.

### Ε2: Μπορώ να εφαρμόσω πολλά κριτήρια σε μία ομάδα;

Α: Οπωσδήποτε, μπορείτε να προσθέσετε πολλά κριτήρια σε μια ομάδα επαναλαμβάνοντας το καθένα και προσθέτοντάς τα ανάλογα.

### Ε3: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;

 Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Tasks από[εδώ](https://releases.aspose.com/).

### Ε4: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks;

 Α: Μπορείτε να ανατρέξετε στην τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/).

### Ε5: Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα;

 Α: Εάν έχετε οποιεσδήποτε ερωτήσεις ή αντιμετωπίζετε προβλήματα, μπορείτε να ζητήσετε υποστήριξη από το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
