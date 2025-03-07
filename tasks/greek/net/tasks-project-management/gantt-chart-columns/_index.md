---
title: Προσαρμόστε τις στήλες γραφήματος Gantt με το Aspose.Tasks
linktitle: Στήλες γραφήματος Gantt στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να προσαρμόζετε τις στήλες του γραφήματος Gantt στο Aspose.Tasks για .NET ώστε να εμφανίζονται αποτελεσματικά συγκεκριμένες πληροφορίες εργασιών.
weight: 21
url: /el/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσαρμόστε τις στήλες γραφήματος Gantt με το Aspose.Tasks

## Εισαγωγή
Τα διαγράμματα Gantt είναι ένα θεμελιώδες εργαλείο στη διαχείριση έργου, παρέχοντας μια οπτική αναπαράσταση εργασιών, χρονοδιαγραμμάτων και πόρων. Το Aspose.Tasks για .NET προσφέρει ισχυρές δυνατότητες χειρισμού γραφημάτων Gantt, συμπεριλαμβανομένης της προσαρμογής στηλών για την εμφάνιση συγκεκριμένων πληροφοριών εργασιών. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να εργαστείτε με στήλες γραφήματος Gantt χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Εγκατάσταση: Aspose.Tasks για .NET εγκατεστημένο στο σύστημά σας. Εάν όχι, κατεβάστε το και εγκαταστήστε το από[εδώ](https://releases.aspose.com/tasks/net/).
2. .NET Development Environment: Γνώση εργασίας της C# και του πλαισίου .NET.
3. Δείγμα αρχείου έργου: Έχετε ένα δείγμα αρχείου Microsoft Project (`.mpp`) βολικό να πειραματιστείτε. Εάν δεν έχετε, μπορείτε να δημιουργήσετε ένα απλό έργο στο MS Project και να το αποθηκεύσετε.

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για να εργαστείτε με το Aspose.Tasks για .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
 Φορτώστε το αρχείο του έργου χρησιμοποιώντας το`Project` τάξη που παρέχεται από το Aspose.Tasks:
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Βήμα 2: Ορίστε στήλες γραφήματος Gantt
Καθορίστε τις στήλες που θέλετε να εμφανίζονται στο γράφημα Gantt. Μπορείτε να καθορίσετε ενσωματωμένα πεδία ή να δημιουργήσετε προσαρμοσμένα:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Βήμα 3: Επανάληψη πάνω από στήλες
Επαναλάβετε τις καθορισμένες στήλες για πρόσβαση στις ιδιότητές τους και εμφάνιση πληροφοριών:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Βήμα 4: Αποθηκεύστε το γράφημα Gantt στο CSV
Αποθηκεύστε το γράφημα Gantt με καθορισμένες στήλες σε ένα αρχείο CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Ακολουθώντας αυτά τα βήματα, μπορείτε να εργαστείτε αποτελεσματικά με στήλες γραφήματος Gantt στο Aspose.Tasks για .NET, επιτρέποντάς σας να προσαρμόσετε και να εμφανίσετε πληροφορίες εργασιών όπως απαιτείται.

## συμπέρασμα
Η γνώση της χειραγώγησης των στηλών γραφήματος Gantt στο Aspose.Tasks για .NET ανοίγει ατελείωτες δυνατότητες για την προσαρμογή των γραφικών διαχείρισης έργου στις συγκεκριμένες ανάγκες σας. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά τις πληροφορίες εργασιών και να βελτιώσετε τη σαφήνεια και την οργάνωση του έργου.
## Συχνές ερωτήσεις
### Ε: Μπορώ να δημιουργήσω προσαρμοσμένες στήλες στο Aspose.Tasks για .NET;
Α: Ναι, μπορείτε να ορίσετε προσαρμοσμένες στήλες για την εμφάνιση συγκεκριμένων χαρακτηριστικών εργασιών σύμφωνα με τις απαιτήσεις του έργου σας.
### Ε: Είναι το Aspose.Tasks για .NET συμβατό με όλες τις εκδόσεις των αρχείων Microsoft Project;
Α: Το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα έργου.
### Ε: Πώς μπορώ να χειριστώ πολύπλοκες δομές έργου με το Aspose.Tasks για .NET;
Α: Το Aspose.Tasks για .NET παρέχει ολοκληρωμένα API και δυνατότητες για τη διαχείριση πολύπλοκων δομών έργων, προσφέροντας ευελιξία και επεκτασιμότητα.
### Ε: Υπάρχουν περιορισμοί στον αριθμό των στηλών που μπορώ να προσθέσω σε ένα γράφημα Gantt;
Α: Το Aspose.Tasks για .NET προσφέρει εκτενείς επιλογές προσαρμογής, επιτρέποντάς σας να προσθέσετε σημαντικό αριθμό στηλών στα γραφήματα Gantt χωρίς περιορισμούς.
### Ε: Πού μπορώ να βρω πρόσθετη υποστήριξη και πόρους για το Aspose.Tasks για .NET;
Α: Μπορείτε να εξερευνήσετε την τεκμηρίωση, τα φόρουμ κοινότητας και τα κανάλια υποστήριξης που παρέχονται από το Aspose.Tasks για το .NET για πρόσβαση σε ολοκληρωμένους πόρους και βοήθεια.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
