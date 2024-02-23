---
title: Mastering WBS Sequences με Aspose.Tasks για .NET
linktitle: Καθορισμός ακολουθιών WBS στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ενισχύστε τη διαχείριση του έργου σας με το Aspose.Tasks για .NET – ορίστε απρόσκοπτα τις ακολουθίες WBS και βελτιώστε την αποτελεσματικότητα χωρίς κόπο. #Aspose #Tasks #MS Project
type: docs
weight: 16
url: /el/net/view-wbs-code-configuration/wbs-sequences/
---
## Εισαγωγή
Εργάζεστε σε μια εφαρμογή διαχείρισης έργου και χρειάζεστε ένα ισχυρό εργαλείο για να χειριστείτε ακολουθίες Δομής Ανάλυσης Εργασίας (WBS); Μην ψάχνετε πέρα από το Aspose.Tasks για .NET, μια ισχυρή βιβλιοθήκη που απλοποιεί τις εργασίες διαχείρισης έργου. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία καθορισμού των ακολουθιών WBS βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- [Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET](https://releases.aspose.com/tasks/net/)
- Βασικές γνώσεις προγραμματισμού C#
- Ένα περιβάλλον ανάπτυξης που έχει δημιουργηθεί για έργα .NET
## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, φροντίστε να συμπεριλάβετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τη λειτουργικότητα του Aspose.Tasks. Προσθέστε τα ακόλουθα στην αρχή του σεναρίου σας:
```csharp
    
    using Aspose.Tasks.Saving;
```
## Καθορισμός ακολουθιών WBS - Οδηγός βήμα προς βήμα
## Βήμα 1: Ρύθμιση του έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project();
```
## Βήμα 2: Διαμορφώστε τον ορισμό κώδικα WBS
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Βήμα 3: Ορίστε τις μάσκες κώδικα WBS
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
## Βήμα 4: Προσθήκη εργασιών στο έργο
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
```
## Βήμα 5: Υπολογισμός εκ νέου δεδομένων έργου
```csharp
project.Recalculate();
```
## Βήμα 6: Αποθηκεύστε το έργο
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Συγχαρητήρια! Έχετε ορίσει με επιτυχία ακολουθίες WBS στο έργο σας χρησιμοποιώντας το Aspose.Tasks για .NET.
## συμπέρασμα
Η διαχείριση των ακολουθιών WBS είναι ζωτικής σημασίας για την αποτελεσματική διαχείριση έργου και το Aspose.Tasks για .NET κάνει αυτή την εργασία απρόσκοπτη. Ακολουθώντας αυτά τα απλά βήματα, μπορείτε να βελτιώσετε τη λειτουργικότητα του WBS στην εφαρμογή διαχείρισης έργου.
## Συχνές Ερωτήσεις
### Είναι το Aspose.Tasks συμβατό με .NET Core;
Ναι, το Aspose.Tasks υποστηρίζει .NET Core, επιτρέποντάς σας να δημιουργείτε εφαρμογές πολλαπλών πλατφορμών.
### Μπορώ να προσαρμόσω περαιτέρω τη μορφή κώδικα WBS;
Απολύτως! Το Aspose.Tasks παρέχει ευελιξία στον καθορισμό κωδικών WBS σύμφωνα με τις απαιτήσεις του έργου σας.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση;
 Ναι μπορείς[κατεβάστε μια δωρεάν δοκιμή](https://releases.aspose.com/) για να εξερευνήσετε τις δυνατότητες πριν κάνετε μια αγορά.
### Πώς μπορώ να λάβω υποστήριξη κοινότητας για το Aspose.Tasks;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) να συνδεθείτε με την κοινότητα και να αναζητήσετε βοήθεια.
### Διατίθενται προσωρινές άδειες;
 Ναι, μπορείτε να πάρετε ένα[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για δοκιμαστικούς σκοπούς.