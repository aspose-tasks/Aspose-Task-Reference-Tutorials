---
title: Mastering WBS Code Masks με Aspose.Tasks για .NET
linktitle: Συλλογή από WBS Code Mask στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Βελτιώστε τη διαχείριση έργων με το Aspose.Tasks για .NET. Μάθετε να δημιουργείτε, να διαχειρίζεστε και να μεταφέρετε μάσκες κώδικα WBS χωρίς κόπο σε αυτό το ολοκληρωμένο σεμινάριο.
type: docs
weight: 15
url: /el/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Εισαγωγή
Στον δυναμικό κόσμο της διαχείρισης έργων, η αποτελεσματική οργάνωση των εργασιών είναι ζωτικής σημασίας. Το Aspose.Tasks for .NET παρέχει μια ισχυρή λύση για τη διαχείριση των κωδίκων ανάλυσης δομής εργασιών έργου (WBS) χωρίς κόπο. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη Συλλογή των Μάσκες Κώδικα WBS, διερευνώντας πώς να τις εφαρμόσουμε και να τις χειριστούμε χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το ταξίδι κωδικοποίησης, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Γνώση εργασίας γλώσσας προγραμματισμού C#.
-  Το Aspose.Tasks για .NET είναι εγκατεστημένο στο περιβάλλον ανάπτυξης σας. Εάν όχι, κατεβάστε το[εδώ](https://releases.aspose.com/tasks/net/).
- Ένα πρόγραμμα επεξεργασίας κώδικα όπως το Visual Studio για μια απρόσκοπτη εμπειρία κωδικοποίησης.
## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Αρχικοποιήστε τον ορισμό κώδικα έργου και WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Ορίστε τις μάσκες κωδικών WBS
Διαγράψτε τυχόν υπάρχουσες μάσκες κώδικα και προσθέστε νέες:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Εμφάνιση πληροφοριών για μάσκες κώδικα
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Προσθέστε Εργασίες στο Έργο
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Ανάκτηση πληροφοριών εργασίας
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Χειριστείτε τις μάσκες κωδικών
Αφαιρέστε μια μάσκα κωδικού και βεβαιωθείτε ότι έχει αφαιρεθεί:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Αντιγράψτε τις μάσκες κώδικα σε άλλο έργο
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Εμφάνιση μάσκες κώδικα σε άλλο έργο
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Προσθέστε Εργασίες στο Άλλο Έργο
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Εμφάνιση κωδικών WBS στο άλλο έργο
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## συμπέρασμα
Με το Aspose.Tasks για .NET, η διαχείριση κωδικών WBS γίνεται μια αβίαστη εργασία. Αυτό το σεμινάριο κάλυψε τη δημιουργία, τον χειρισμό και τη μεταφορά των μάσκες κώδικα WBS, παρέχοντάς σας έναν ολοκληρωμένο οδηγό για να βελτιώσετε την εμπειρία διαχείρισης έργου.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλες γλώσσες προγραμματισμού;
Α: Το Aspose.Tasks υποστηρίζει κυρίως γλώσσες .NET, αλλά μπορείτε να εξερευνήσετε επιλογές διαλειτουργικότητας με άλλες γλώσσες.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να κάνετε λήψη της δοκιμαστικής έκδοσης[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να αναζητήσω βοήθεια ή να αναφέρω προβλήματα με το Aspose.Tasks για .NET;
 Α: Επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για υποστήριξη και συζητήσεις.
### Ε: Ποιος είναι ο σκοπός των κωδικών WBS στη διαχείριση έργων;
Α: Οι κώδικες WBS βοηθούν στην οργάνωση και τη δομή των εργασιών του έργου ιεραρχικά, παρέχοντας μια συστηματική προσέγγιση στο σχεδιασμό του έργου.
### Ε: Μπορώ να προσαρμόσω τη μορφή των κωδικών WBS στο Aspose.Tasks για .NET;
Α: Απολύτως, έχετε τον πλήρη έλεγχο της μορφής και της δομής των κωδικών WBS χρησιμοποιώντας το Aspose.Tasks για .NET.