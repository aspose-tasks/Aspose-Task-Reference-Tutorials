---
title: Συλλογή ορισμών κώδικα περίγραμμα στο Aspose.Tasks .NET
linktitle: Συλλογή ορισμών κώδικα περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε τους ορισμούς του κώδικα περίγραμμα σε έγγραφα του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Κατηγοριοποίηση των δεδομένων του έργου σας χωρίς κόπο.
type: docs
weight: 13
url: /el/net/outline-code-page-settings/outline-code-definition-collection/
---
## Εισαγωγή
Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη .NET που έχει σχεδιαστεί για να χειρίζεται έγγραφα του Microsoft Project με ευκολία και αποτελεσματικότητα. Ένα από τα βασικά χαρακτηριστικά του είναι η δυνατότητα εργασίας με ορισμούς κώδικα περιγράμματος, επιτρέποντας στους χρήστες να οργανώνουν και να κατηγοριοποιούν αποτελεσματικά τα δεδομένα του έργου. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να εργαστούμε με ορισμούς κώδικα περιγράμματος χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν βουτήξουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
1. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.
2. Visual Studio: Εγκαταστήστε το Visual Studio ή οποιοδήποτε άλλο προτιμώμενο περιβάλλον ανάπτυξης C#.
3.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Βήμα 1: Φορτώστε ένα έγγραφο Microsoft Project
Αρχικά, φορτώστε ένα έγγραφο του Microsoft Project για να ξεκινήσετε να εργάζεστε με ορισμούς κώδικα περίληψης:
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Βήμα 2: Αποκτήστε πρόσβαση στους ορισμούς του κώδικα περίγραμμα
Τώρα, ας αποκτήσουμε πρόσβαση στους ορισμούς του κώδικα περιλήψεων εντός του έργου:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Βήμα 3: Προσθέστε Προσαρμοσμένους Ορισμούς Κώδικα Περιγράμματος
Μπορείτε να προσθέσετε προσαρμοσμένους ορισμούς κώδικα περίγραμμα ως εξής:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Βήμα 4: Τροποποιήστε τους ορισμούς του κώδικα περίγραμμα
Τροποποιήστε εύκολα τους υπάρχοντες ορισμούς κώδικα περίγραμμα:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Βήμα 5: Καταργήστε τους ορισμούς κωδικών περίγραμμα
Καταργήστε τους ορισμούς του περιγράμματος κώδικα όταν δεν χρειάζονται πλέον:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Βήμα 6: Αποθήκευση αλλαγών
Τέλος, αποθηκεύστε τις αλλαγές σας στο έγγραφο του έργου:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## συμπέρασμα
Συμπερασματικά, το Aspose.Tasks για .NET παρέχει ολοκληρωμένη λειτουργικότητα για τη διαχείριση ορισμών κώδικα περίγραμμα στα έγγραφα του Microsoft Project. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά τους ορισμούς του κώδικα περιγράμματος για να οργανώσετε και να κατηγοριοποιήσετε αποτελεσματικά τα δεδομένα του έργου σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να προσθέσω πολλαπλούς ορισμούς κώδικα περιλήψεων σε ένα μόνο έργο;
 Α: Ναι, μπορείτε να προσθέσετε πολλούς ορισμούς κωδικών περιλήψεων σε ένα έργο με βάση τις απαιτήσεις σας. Απλώς χρησιμοποιήστε το`Add` μέθοδος για κάθε ορισμό που θέλετε να συμπεριλάβετε.
### Ε: Είναι δυνατόν να αφαιρεθούν όλοι οι ορισμοί του κώδικα περίγραμμα από ένα έργο ταυτόχρονα;
 Α: Ναι, μπορείτε να διαγράψετε όλους τους ορισμούς του κώδικα περίγραμμα από ένα έργο χρησιμοποιώντας το`Clear` μέθοδος.
### Ε: Τι θα συμβεί αν προσπαθήσω να τροποποιήσω έναν ορισμό κώδικα περίληψης μόνο για ανάγνωση;
Α: Εάν ένας ορισμός κώδικα περίγραμμα είναι μόνο για ανάγνωση, δεν θα μπορείτε να τον τροποποιήσετε απευθείας. Θα πρέπει να ελέγξετε την κατάστασή του μόνο για ανάγνωση πριν επιχειρήσετε οποιεσδήποτε τροποποιήσεις.
### Ε: Υπάρχουν περιορισμοί ως προς τον αριθμό των ορισμών του κώδικα περίγραμμα που μπορώ να προσθέσω σε ένα έργο;
Α: Το Aspose.Tasks για το .NET δεν επιβάλλει συγκεκριμένους περιορισμούς στον αριθμό των ορισμών κώδικα περίγραμμα που μπορείτε να προσθέσετε σε ένα έργο. Ωστόσο, λάβετε υπόψη τις επιπτώσεις της απόδοσης όταν εργάζεστε με μεγάλο αριθμό ορισμών.
### Ε: Μπορώ να χρησιμοποιήσω ορισμούς κώδικα περιγράμματος για να ομαδοποιήσω εργασίες με βάση προσαρμοσμένα κριτήρια;
Α: Ναι, οι ορισμοί του περίγραμμα κώδικα σάς επιτρέπουν να κατηγοριοποιείτε εργασίες με βάση προσαρμοσμένα κριτήρια, παρέχοντας ευελιξία στην οργάνωση των δεδομένων έργου.## Πλήρης Πηγαίος Κώδικας