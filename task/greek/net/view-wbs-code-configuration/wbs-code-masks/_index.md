---
title: Βήμα προς βήμα Ρύθμιση κώδικα WBS στο Aspose.Tasks .NET
linktitle: Διαμόρφωση μάσκας κώδικα WBS στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε βήμα προς βήμα τη διαμόρφωση WBS Code Masks σε έργα .NET χρησιμοποιώντας Aspose.Tasks. Βελτιώστε τις δυνατότητες διαχείρισης έργου χωρίς κόπο.
type: docs
weight: 14
url: /el/net/view-wbs-code-configuration/wbs-code-masks/
---
## Εισαγωγή
Το Aspose.Tasks for .NET είναι μια ισχυρή βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές να χειρίζονται αποτελεσματικά τα δεδομένα διαχείρισης έργων σε εφαρμογές .NET. Σε αυτό το σεμινάριο, θα διερευνήσουμε τη διαδικασία ρύθμισης των μάσκες κώδικα δομής ανάλυσης εργασίας (WBS) χρησιμοποιώντας το Aspose.Tasks.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Aspose.Tasks for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από[Aspose.Tasks for .NET Documentation](https://reference.aspose.com/tasks/net/).
- Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα λειτουργικό περιβάλλον ανάπτυξης .NET.
- Κατάλογος εγγράφων: Επιλέξτε έναν κατάλογο στο σύστημά σας για να αποθηκεύσετε τα αρχεία του έργου.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας .NET, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων για εργασία με το Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Βήμα 1: Δημιουργήστε μια παρουσία έργου
Ξεκινήστε δημιουργώντας ένα νέο παράδειγμα έργου:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Βήμα 2: Ορισμός κωδικού WBS
Ρυθμίστε τον ορισμό κώδικα WBS για το έργο σας:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Βήμα 3: Προσθέστε μάσκες κώδικα WBS
Ορίστε τις μάσκες κώδικα WBS και προσθέστε τις στο έργο:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Βήμα 4: Δημιουργία εργασιών
Προσθήκη εργασιών στο έργο:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Βήμα 5: Υπολογίστε ξανά
Υπολογίστε ξανά το έργο για να διασφαλίσετε ότι οι κωδικοί WBS εφαρμόζονται σωστά:
```csharp
project.Recalculate();
```
## Βήμα 6: Εμφάνιση πληροφοριών μάσκας WBS
Εξαγωγή πληροφοριών σχετικά με τις μάσκες WBS στην κονσόλα:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Βήμα 7: Αποθηκεύστε το έργο
Αποθηκεύστε το έργο με τους πρόσθετους κωδικούς WBS:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Συγχαρητήρια! Διαμορφώσατε με επιτυχία τις παραμέτρους των μάσκες κώδικα WBS στο έργο Aspose.Tasks.
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τη διαδικασία βήμα προς βήμα της διαμόρφωσης των μασκών κώδικα WBS χρησιμοποιώντας το Aspose.Tasks για .NET. Αυτή η ισχυρή βιβλιοθήκη παρέχει στους προγραμματιστές έναν απρόσκοπτο τρόπο για να βελτιώσουν τις δυνατότητες διαχείρισης έργων στις εφαρμογές τους .NET.

## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks δωρεάν;
 Το Aspose.Tasks προσφέρει μια δωρεάν δοκιμή, την οποία μπορείτε να κατεβάσετε[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω επιπλέον υποστήριξη;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη.
### Πώς μπορώ να αποκτήσω προσωρινή άδεια;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Υπάρχει αναλυτική τεκμηρίωση διαθέσιμη;
 Ναι, η πλήρης τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tasks/net/).
### Πού μπορώ να αγοράσω το Aspose.Tasks;
 Αγορά Aspose.Tasks[εδώ](https://purchase.aspose.com/buy).