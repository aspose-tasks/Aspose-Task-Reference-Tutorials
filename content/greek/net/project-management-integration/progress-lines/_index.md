---
title: Χειρισμός Γραμμών Προόδου Έργου MS με το Aspose.Tasks
linktitle: Χειρισμός Γραμμών Προόδου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε τις γραμμές προόδου σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET, βελτιώνοντας την οπτικοποίηση και τη διαχείριση του έργου.
type: docs
weight: 15
url: /el/net/project-management-integration/progress-lines/
---
## Εισαγωγή
Το Microsoft Project (MS Project) είναι ένα ισχυρό εργαλείο για τη διαχείριση έργων, που επιτρέπει στους χρήστες να παρακολουθούν διάφορες πτυχές των έργων τους. Ένα κρίσιμο χαρακτηριστικό του MS Project είναι η ικανότητα οπτικοποίησης των γραμμών προόδου, οι οποίες βοηθούν τους ενδιαφερόμενους να κατανοήσουν την κατάσταση και την πορεία του έργου. Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο χειρισμού των γραμμών προόδου στο MS Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Visual Studio: Εγκαταστήστε το Visual Studio ή οποιοδήποτε άλλο προτιμώμενο περιβάλλον ανάπτυξης .NET.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Τώρα, ας αναλύσουμε κάθε βήμα στον χειρισμό των γραμμών προόδου:
## Βήμα 1: Φορτώστε το Αρχείο Έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Εδώ, φορτώνουμε το αρχείο MS Project`Project2.mpp` και ορίστε την ημερομηνία κατάστασής του.
## Βήμα 2: Ορίστε την προβολή γραφήματος Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Μεταφέρουμε την προβολή του έργου σε μια προβολή γραφήματος Gantt για περαιτέρω χειρισμό.
## Βήμα 3: Καθορισμός Γραμμών Προόδου
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Αρχικοποιούμε τις γραμμές προόδου για την προβολή γραφήματος Gantt.
## Βήμα 4: Διαμόρφωση ρυθμίσεων γραμμής προόδου
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Εδώ, ορίζουμε διάφορες ιδιότητες για τις γραμμές προόδου, όπως χρώμα γραμμής, μοτίβο, γραμματοσειρά κ.λπ.
## Βήμα 5: Ελέγξτε τη διαμόρφωση των γραμμών προόδου
```csharp
// Ρυθμίσεις γραμμών προόδου εξόδου
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Έξοδος άλλων ρυθμίσεων...
```
Εξάγουμε τις διαμορφωμένες ρυθμίσεις των γραμμών προόδου για επαλήθευση.
## Βήμα 6: Αποθηκεύστε το Αρχείο Έργου
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Τέλος, αποθηκεύουμε το τροποποιημένο αρχείο έργου με γραμμές προόδου.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να χειριζόμαστε τις γραμμές προόδου του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να προσαρμόσετε και να οπτικοποιήσετε αποτελεσματικά τις γραμμές προόδου στα αρχεία του MS Project μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Ε: Μπορώ να προσαρμόσω περαιτέρω την εμφάνιση των γραμμών προόδου;
Α: Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες όπως το χρώμα γραμμής, το μοτίβο και τη γραμματοσειρά για να ταιριάζουν στις απαιτήσεις σας.
### Ε: Το Aspose.Tasks υποστηρίζει άλλες δυνατότητες διαχείρισης έργου;
Α: Ναι, το Aspose.Tasks παρέχει εκτενή υποστήριξη για το χειρισμό διαφόρων πτυχών των αρχείων του MS Project, συμπεριλαμβανομένων εργασιών, πόρων και ημερολογίων.
### Ε: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες .NET;
Α: Απολύτως, το Aspose.Tasks έχει σχεδιαστεί για να ενσωματώνεται απρόσκοπτα με άλλες βιβλιοθήκες .NET, επιτρέποντάς σας να βελτιώσετε περαιτέρω τις εφαρμογές διαχείρισης έργων σας.
### Ε: Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.Tasks;
 Α: Ναι, μπορείτε να βρείτε χρήσιμους πόρους και να αναζητήσετε βοήθεια στο φόρουμ Aspose.Tasks.[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Το Aspose.Tasks προσφέρει προσωρινές άδειες για σκοπούς αξιολόγησης;
 Α: Ναι, μπορείτε να λάβετε προσωρινή άδεια για αξιολόγηση από[εδώ](https://purchase.aspose.com/temporary-license/).