---
title: Διαχείριση εργασιών στο Aspose.Tasks
linktitle: Διαχείριση εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε τον αναλυτικό οδηγό για τη διαχείριση εργασιών με το Aspose.Tasks για .NET. Μάθετε να προσθέτετε, να εμφανίζετε διαχωρισμένα μέρη, να μετακινείτε, να λαμβάνετε/ορίζετε ιδιότητες και πολλά άλλα.
type: docs
weight: 15
url: /el/net/task-table-management/managing-tasks/
---
## Εισαγωγή
Εάν είστε προγραμματιστής .NET που θέλει να διαχειριστεί αποτελεσματικά τις εργασίες στα έργα σας, το Aspose.Tasks για .NET παρέχει μια ισχυρή λύση. Αυτό το σεμινάριο θα σας καθοδηγήσει σε διάφορες πτυχές της διαχείρισης εργασιών χρησιμοποιώντας το Aspose.Tasks, προσφέροντας οδηγίες βήμα προς βήμα και παραδείγματα κώδικα. Είτε προσθέτετε εργασίες, εμφανίζετε διαχωρισμένα μέρη, μετακινείτε εργασίες κάτω από τον ίδιο γονέα, λαμβάνετε/ρυθμίζετε ιδιότητες εργασιών, επαναλαμβάνετε τις αναθέσεις εργασιών, διαβάζετε γραμμές βάσης εργασιών ή διαγράφετε εργασίες, αυτός ο οδηγός σας καλύπτει.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks for .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
2. Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο όπου θα αποθηκεύονται τα έγγραφα του έργου σας.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας .NET, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων για να εργαστείτε με το Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Προσθήκη Εργασίας σε Έργο
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
// Προσθέστε μια εργασία
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Αποθηκεύστε το έργο
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Εμφάνιση τμημάτων διαχωρισμού της εργασίας
```csharp
// Φορτώστε ένα έργο με διαχωρισμένες εργασίες
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Πρόσβαση σε μια εργασία
var task = project.RootTask.Children.GetById(4);
// Εμφάνιση διαχωρισμένων εξαρτημάτων
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Μετακίνηση μιας εργασίας κάτω από τον ίδιο γονέα
```csharp
try
{
    // Φορτώστε ένα έργο
    var project = new Project(DataDir + "MoveTask.mpp");
    // Μετακινήστε εργασίες με αναγνωριστικό 5 πριν από εργασία με αναγνωριστικό 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Αποθηκεύστε το τροποποιημένο έργο
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Λήψη/Ορισμός ιδιοτήτων εργασίας
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
// Προσθέστε μια εργασία και ορίστε ιδιότητες
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Συλλέξτε και εμφανίστε τις ιδιότητες εργασίας
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Επανάληψη των εργασιών της εργασίας
```csharp
// Φορτώστε ένα έργο με εργασίες
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Συλλέξτε και εμφανίστε αναθέσεις εργασιών
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Ανάγνωση των γραμμών βάσης της εργασίας
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
// Προσθέστε μια εργασία και ορίστε μια γραμμή βάσης
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Εμφάνιση διάρκειας γραμμής βάσης εργασίας
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Διαγραφή Εργασίας
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
// Προσθέστε μια εργασία
var task = project.RootTask.Children.Add("Task");
// Εμφάνιση του αριθμού των εργασιών πριν και μετά τη διαγραφή
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Διαγράψτε την εργασία
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## συμπέρασμα
Η διαχείριση εργασιών στο Aspose.Tasks για .NET είναι μια απρόσκοπτη διαδικασία με τα παρεχόμενα παραδείγματα. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, η ενσωμάτωση αυτών των τεχνικών θα ενισχύσει τις δυνατότητες διαχείρισης του έργου σας.
## Συχνές Ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με όλα τα πλαίσια .NET;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορα πλαίσια .NET, διασφαλίζοντας τη συμβατότητα με το περιβάλλον ανάπτυξής σας.
### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Tasks;
 Α: Μπορείτε να λάβετε μια προσωρινή άδεια 30 ημερών από[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Υπάρχουν περιορισμοί κατά την εργασία με διαχωρισμένες εργασίες στο Aspose.Tasks;
 Α: Οι εργασίες διαχωρισμού είναι μια ισχυρή δυνατότητα και μπορείτε να βρείτε λεπτομερή τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/).
### Ε: Μπορώ να προσαρμόσω τις ιδιότητες της εργασίας πέρα από αυτό που φαίνεται στα παραδείγματα;
Α: Απολύτως! Το Aspose.Tasks παρέχει εκτενείς επιλογές προσαρμογής για ιδιότητες εργασιών. Ελέγξτε την τεκμηρίωση για περισσότερες λεπτομέρειες.
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Α: Επισκεφθείτε το[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη και συζητήσεις.