---
title: Χειρισμός εξαρτημάτων MS Project Split στο Aspose.Tasks
linktitle: Χειρισμός διαχωρισμένων εξαρτημάτων στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε αποτελεσματικά τα διαχωρισμένα εξαρτήματα του MS Project με το Aspose.Tasks για .NET. Βελτιώστε τη ροή εργασιών διαχείρισης του έργου σας.
weight: 18
url: /el/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Χειρισμός εξαρτημάτων MS Project Split στο Aspose.Tasks


## Εισαγωγή
Η διαχείριση τμημάτων του MS Project μπορεί να είναι μια κρίσιμη πτυχή της διαχείρισης έργου όταν χρησιμοποιείτε το Aspose.Tasks για .NET. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χειρίζεστε αποτελεσματικά τα σπασμένα μέρη χρησιμοποιώντας οδηγίες βήμα προς βήμα.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Εγκατάσταση του Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από το[δικτυακός τόπος](https://releases.aspose.com/tasks/net/).
   
2. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Βήμα 1: Δημιουργία παρουσίας έργου
```csharp
var project = new Project();
```
 Δημιουργήστε μια νέα παρουσία του`Project` τάξη.
## Βήμα 2: Ορισμός ημερομηνιών έναρξης και λήξης έργου
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Ορίστε τις ημερομηνίες έναρξης και λήξης για το έργο.
## Βήμα 3: Προσθήκη Εργασίας
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Προσθέστε μια νέα εργασία στο έργο.
## Βήμα 4: Ρύθμιση ιδιοτήτων εργασίας
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Ορίστε ιδιότητες όπως μη αυτόματη κατάσταση, ημερομηνία έναρξης και διάρκεια για την εργασία.
## Βήμα 5: Προσθήκη αναθέσεων πόρων
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Προσθέστε αναθέσεις πόρων στην εργασία.
## Βήμα 6: Ρύθμιση ιδιοτήτων ανάθεσης
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Ορίστε ιδιότητες όπως ημερομηνία έναρξης, εργασία και ημερομηνία λήξης για την ανάθεση.
## Βήμα 7: Δημιουργία δεδομένων χρονικής φάσης
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Δημιουργήστε δεδομένα χρονικής φάσης για την εργασία με βάση το ημερολόγιο του έργου.
## Βήμα 8: Διαχωρισμός της εργασίας
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Διαχωρίστε την εργασία σε πολλά μέρη εντός του καθορισμένου χρονικού πλαισίου.
## Βήμα 9: Επανάληψη με διαχωρισμό εξαρτημάτων
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Επαναλάβετε τα χωρισμένα μέρη της εργασίας και εκτυπώστε τις ημερομηνίες έναρξης και λήξης τους.

## συμπέρασμα
Ο αποτελεσματικός χειρισμός διαχωρισμένων εξαρτημάτων MS Project στο Aspose.Tasks για .NET είναι ζωτικής σημασίας για την αποτελεσματικότητα της διαχείρισης έργου. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να διαχειρίζεστε απρόσκοπτα διαχωρισμένες εργασίες και να βελτιώσετε τη ροή εργασιών διαχείρισης έργου.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλα πλαίσια .NET;
Α: Ναι, το Aspose.Tasks για .NET είναι συμβατό με διάφορα πλαίσια .NET, συμπεριλαμβανομένων των .NET Core και .NET Standard.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).
### Ε: Το Aspose.Tasks για .NET υποστηρίζει τη διαχείριση πόρων;
Α: Ναι, το Aspose.Tasks για .NET σάς επιτρέπει να διαχειρίζεστε αποτελεσματικά τους πόρους του έργου.
### Ε: Μπορώ να προσαρμόσω τα ημερολόγια έργων χρησιμοποιώντας το Aspose.Tasks για .NET;
Α: Οπωσδήποτε, μπορείτε να προσαρμόσετε τα ημερολόγια έργων σύμφωνα με τις απαιτήσεις του έργου σας.
### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks για .NET;
 Α: Μπορείτε να βρείτε υποστήριξη και βοήθεια στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
