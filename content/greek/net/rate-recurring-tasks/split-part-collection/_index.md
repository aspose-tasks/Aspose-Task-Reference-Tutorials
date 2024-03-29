---
title: Συλλέξτε το MS Project of Split Parts στο Aspose.Tasks
linktitle: Συλλογή Split Parts στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να συλλέγετε διαχωρισμένα μέρη στο MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Αυτό το περιεκτικό σεμινάριο σας καθοδηγεί βήμα προς βήμα στη διαδικασία.
type: docs
weight: 19
url: /el/net/rate-recurring-tasks/split-part-collection/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στον τρόπο συλλογής διαχωρισμένων τμημάτων στο MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ο διαχωρισμός των εργασιών σε μέρη μπορεί να είναι μια κρίσιμη πτυχή της διαχείρισης έργου και το Aspose.Tasks παρέχει βολικές μεθόδους για να το χειριστείτε αποτελεσματικά.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Εγκατάσταση του Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής καθώς θα γράφουμε αποσπάσματα κώδικα σε C#.

## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Βήμα 1: Ρύθμιση του έργου σας
Αρχικά, δημιουργήστε ένα νέο έργο στο IDE που προτιμάτε και βεβαιωθείτε ότι το Aspose.Tasks για .NET αναφέρεται σωστά.
## Βήμα 2: Αρχικοποίηση του Αντικειμένου Έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Αρχικοποιήστε ένα νέο αντικείμενο Project με τη διαδρομή προς το αρχείο MS Project.
## Βήμα 3: Ανάκτηση Εργασίας και Επανάληψη μέσω Διαχωρισμού τμημάτων
```csharp
var task = project.RootTask.Children.GetById(1);
// Επαναλάβετε τα χωρισμένα μέρη
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Ανακτήστε την εργασία από το έργο και επαναλάβετε τα διαχωρισμένα μέρη του, εκτυπώνοντας τις ημερομηνίες έναρξης και λήξης τους.
## Βήμα 4: Λήψη διαχωρισμού μέρους ανά ευρετήριο
```csharp
// Λάβετε το μέρος ανά ευρετήριο
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Ανακτήστε ένα συγκεκριμένο διαχωρισμένο τμήμα ανά ευρετήριο και εκτυπώστε την ημερομηνία έναρξης του.

## συμπέρασμα
Η διαχείριση διαχωρισμένων τμημάτων σε αρχεία MS Project μπορεί να βελτιώσει σημαντικά την αποτελεσματικότητα της διαχείρισης έργου. Το Aspose.Tasks για .NET απλοποιεί αυτή τη διαδικασία παρέχοντας εύχρηστα API για τον απρόσκοπτο χειρισμό διαχωρισμένων εργασιών.
## Συχνές ερωτήσεις
### Ε: Μπορώ να διαχωρίσω τις εργασίες δυναμικά κατά τη διάρκεια του χρόνου εκτέλεσης;
Α: Ναι, μπορείτε να διαχωρίσετε εργασίες μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για .NET.
### Ε: Το Aspose.Tasks υποστηρίζει όλες τις εκδόσεις των αρχείων MS Project;
Α: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικές πλατφόρμες.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για δοκιμαστικούς σκοπούς;
 Α: Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμαστική έκδοση από[εδώ](https://releases.aspose.com/) για αξιολόγηση.
### Ε: Πώς μπορώ να λάβω προσωρινές άδειες για τα έργα μου;
 Α: Οι προσωρινές άδειες μπορούν να αποκτηθούν από[εδώ](https://purchase.aspose.com/temporary-license/) για βραχυπρόθεσμη χρήση.
### Ε: Πού μπορώ να αναζητήσω βοήθεια ή υποστήριξη σχετικά με το Aspose.Tasks;
 Α: Μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15)να ζητήσετε βοήθεια από την κοινότητα ή την ομάδα υποστήριξης της Aspose.