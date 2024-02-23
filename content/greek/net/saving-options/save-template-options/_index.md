---
title: Αποθηκεύστε τα αρχεία έργου MS ως πρότυπα με το Aspose.Tasks
linktitle: Αποθήκευση επιλογών προτύπου για Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να αποθηκεύετε αρχεία Microsoft Project ως πρότυπα χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε τις ρυθμίσεις προτύπου για βελτιωμένη διαχείριση έργου.
type: docs
weight: 18
url: /el/net/saving-options/save-template-options/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία αποθήκευσης ενός προτύπου χρησιμοποιώντας το Aspose.Tasks για .NET. Τα πρότυπα είναι χρήσιμα για την τυποποίηση των δομών και των ρυθμίσεων του έργου για μελλοντική χρήση. Θα δείξουμε πώς να αποθηκεύσετε ένα έργο ως πρότυπο, συντονίζοντας τις ιδιότητές του στην πορεία.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks for .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Γνώση προγραμματισμού C#: Απαιτούνται βασικές γνώσεις προγραμματισμού C# για την κατανόηση και την υλοποίηση των παρεχόμενων αποσπασμάτων κώδικα.
3. Αρχείο Microsoft Project: Έχετε έτοιμο ένα αρχείο Microsoft Project (μορφή MPP) που θέλετε να αποθηκεύσετε ως πρότυπο.

## Εισαγωγή χώρων ονομάτων
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Βήμα 1: Φόρτωση έργου
Αρχικά, πρέπει να φορτώσουμε το αρχείο Microsoft Project (.mpp) που θέλουμε να αποθηκεύσουμε ως πρότυπο.
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Βήμα 2: Λάβετε πληροφορίες αρχείου έργου
Ανακτήστε πληροφορίες σχετικά με το φορτωμένο αρχείο έργου, όπως τη μορφή του.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Βήμα 3: Διαμορφώστε τις επιλογές αποθήκευσης προτύπου
Δημιουργήστε επιλογές αποθήκευσης προτύπου και διαμορφώστε τις ιδιότητές του σύμφωνα με τις απαιτήσεις σας. Αυτές οι επιλογές σάς επιτρέπουν να προσαρμόσετε τα δεδομένα που πρέπει να αφαιρεθούν από το πρότυπο.
```csharp
var options = new SaveTemplateOptions
{
	// Καταργήστε όλα τα σταθερά κόστη από το πρότυπο έργου
	RemoveFixedCosts = true,
	// Καταργήστε όλες τις πραγματικές τιμές από το πρότυπο έργου
	RemoveActualValues = true,
	// Καταργήστε τα ποσοστά πόρων από το πρότυπο έργου
	RemoveResourceRates = true,
	// Καταργήστε όλες τις βασικές τιμές από το πρότυπο έργου
	RemoveBaselineValues = true
};
```
## Βήμα 4: Αποθήκευση έργου ως πρότυπο
Αποθηκεύστε το έργο ως πρότυπο με τις καθορισμένες επιλογές.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Βήμα 5: Λάβετε πληροφορίες αρχείου προτύπου
Ανακτήστε πληροφορίες σχετικά με το αποθηκευμένο αρχείο προτύπου, όπως τη μορφή του.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Συγχαρητήρια! Αποθηκεύσατε με επιτυχία ένα πρότυπο χρησιμοποιώντας το Aspose.Tasks για .NET, προσαρμόζοντας τις ιδιότητές του όπως απαιτείται.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να αποθηκεύσετε ένα αρχείο Microsoft Project ως πρότυπο χρησιμοποιώντας το Aspose.Tasks για .NET. Τα πρότυπα είναι πολύτιμα για την τυποποίηση των δομών και των ρυθμίσεων του έργου, για τον εξορθολογισμό των μελλοντικών δημιουργιών έργων.
## Συχνές ερωτήσεις
### Ε: Μπορώ να προσαρμόσω ποια δεδομένα να αφαιρέσω από το πρότυπο;
Α: Ναι, μπορείτε να διαμορφώσετε τις επιλογές αποθήκευσης προτύπου για να αφαιρέσετε συγκεκριμένα δεδομένα, όπως σταθερό κόστος, πραγματικές τιμές, ποσοστά πόρων και τιμές βάσης.
### Ε: Είναι το Aspose.Tasks για .NET συμβατό με όλες τις εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks για .NET παρέχει εκτεταμένη συμβατότητα με διάφορες εκδόσεις του Microsoft Project, διασφαλίζοντας απρόσκοπτη ενοποίηση και λειτουργικότητα.
### Ε: Μπορώ να εφαρμόσω πρότυπα σε υπάρχοντα έργα;
Α: Ναι, μπορείτε να εφαρμόσετε πρότυπα σε υπάρχοντα έργα φορτώνοντας το αρχείο προτύπου και συγχωνεύοντάς το με το τρέχον έργο σας, όπως απαιτείται.
### Ε: Το Aspose.Tasks για .NET υποστηρίζει την ανάπτυξη πολλαπλών πλατφορμών;
Α: Το Aspose.Tasks για .NET έχει σχεδιαστεί κυρίως για εφαρμογές πλαισίου .NET που εκτελούνται σε πλατφόρμες Windows.
### Ε: Είναι διαθέσιμη τεχνική υποστήριξη για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να ζητήσετε τεχνική βοήθεια και καθοδήγηση από την κοινότητα Aspose.Tasks.[φόρουμ](https://forum.aspose.com/c/tasks/15) ή επικοινωνήστε απευθείας με την ομάδα υποστήριξής τους.