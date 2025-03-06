---
title: Master Extended Attribute Definitions MS Project στο Aspose.Tasks
linktitle: Συλλογή από εκτεταμένους ορισμούς χαρακτηριστικών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε εκτεταμένους ορισμούς χαρακτηριστικών στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε και βελτιώστε τα δεδομένα του έργου σας χωρίς κόπο.
weight: 14
url: /el/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master Extended Attribute Definitions MS Project στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε τον τρόπο εργασίας με εκτεταμένους ορισμούς χαρακτηριστικών στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Τα εκτεταμένα χαρακτηριστικά προσφέρουν έναν ευέλικτο τρόπο προσαρμογής και βελτίωσης των δεδομένων έργου, επιτρέποντας στους χρήστες να προσθέτουν επιπλέον πεδία πέρα από τα τυπικά που παρέχονται από προεπιλογή. Με το Aspose.Tasks, μπορείτε να διαχειριστείτε αβίαστα αυτά τα εκτεταμένα χαρακτηριστικά για να προσαρμόσετε τις ανάγκες διαχείρισης του έργου σας.
## Προαπαιτούμενα
Πριν προχωρήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τις ακόλουθες προϋποθέσεις:
- [.Πλαίσιο δικτύου](https://dotnet.microsoft.com/download)
-  Aspose.Tasks για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση σε κλάσεις και μεθόδους Aspose.Tasks στο έργο σας .NET. Ακολουθήστε αυτά τα βήματα:
## Βήμα 1: Ανοίξτε το έργο σας .NET
Ανοίξτε το έργο .NET στο IDE που προτιμάτε, όπως το Visual Studio.
## Βήμα 2: Προσθήκη χώρου ονομάτων Aspose.Tasks
Προσθέστε την ακόλουθη γραμμή στην αρχή του αρχείου κώδικα για να εισαγάγετε τον χώρο ονομάτων Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Τώρα, ας αναλύσουμε τα παρεχόμενα παραδείγματα κώδικα σε πολλαπλά βήματα για μια ολοκληρωμένη κατανόηση:
## Βήμα 1: Φορτώστε το αρχείο του έργου
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Βήμα 2: Διαγράψτε τους υπάρχοντες εκτεταμένους ορισμούς χαρακτηριστικών (προαιρετικό)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Βήμα 3: Δημιουργήστε και προσθέστε εκτεταμένο ορισμό χαρακτηριστικών για μια εργασία
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Βήμα 4: Επαναλάβετε τα εκτεταμένα χαρακτηριστικά εργασίας
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Βήμα 5: Δημιουργήστε και προσθέστε εκτεταμένο ορισμό χαρακτηριστικών για έναν πόρο
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Βήμα 6: Εισαγάγετε έναν ορισμό εκτεταμένου χαρακτηριστικού πόρων
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Βήμα 7: Καταργήστε ένα εκτεταμένο χαρακτηριστικό κατά ευρετήριο
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τα βασικά της εργασίας με εκτεταμένους ορισμούς χαρακτηριστικών στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά και να προσαρμόσετε τα εκτεταμένα χαρακτηριστικά για να ταιριάζουν στις απαιτήσεις διαχείρισης του έργου σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να τροποποιήσω τους υπάρχοντες εκτεταμένους ορισμούς χαρακτηριστικών;
Α: Ναι, μπορείτε να τροποποιήσετε υπάρχοντες εκτεταμένους ορισμούς χαρακτηριστικών ή να δημιουργήσετε νέους σύμφωνα με τις ανάγκες σας.
### Ε: Υποστηρίζονται εκτεταμένα χαρακτηριστικά σε όλες τις εκδόσεις του Microsoft Project;
Α: Ναι, τα εκτεταμένα χαρακτηριστικά υποστηρίζονται στις περισσότερες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των πρόσφατων.
### Ε: Μπορώ να χρησιμοποιήσω εκτεταμένα χαρακτηριστικά για τον υπολογισμό προσαρμοσμένων πεδίων;
Α: Αναμφίβολα, τα εκτεταμένα χαρακτηριστικά μπορούν να χρησιμοποιηθούν για τον υπολογισμό προσαρμοσμένων πεδίων με βάση συγκεκριμένα κριτήρια που ορίζετε.
### Ε: Είναι το Aspose.Tasks συμβατό με άλλα πλαίσια .NET;
Α: Το Aspose.Tasks είναι συμβατό με διάφορα πλαίσια .NET, εξασφαλίζοντας ευελιξία και ευκολία ενσωμάτωσης.
### Ε: Πού μπορώ να βρω περισσότερους πόρους και υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για υποστήριξη και εξερευνήστε την τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
