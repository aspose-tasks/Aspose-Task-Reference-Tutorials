---
title: Διαμόρφωση επιλογών MS Project XLSX στο Aspose.Tasks για .NET
linktitle: Διαμόρφωση επιλογών XLSX στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαμορφώνετε τις επιλογές του MS Project XLSX στο Aspose.Tasks για .NET. Προσαρμόστε στήλες, κωδικοποίηση και πιο εύκολα.
type: docs
weight: 11
url: /el/net/file-format-options/configuring-xlsx-options/
---
## Εισαγωγή
Το Microsoft Project (MS Project) είναι ένα ισχυρό εργαλείο για τη διαχείριση έργων και το Aspose.Tasks για .NET παρέχει απρόσκοπτη ενοποίηση για εργασία με αρχεία MS Project μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία διαμόρφωσης των επιλογών του MS Project XLSX χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
### 1. Aspose.Tasks για .NET Εγκατεστημένο
 Βεβαιωθείτε ότι έχετε εγκατεστημένο το Aspose.Tasks για .NET στο περιβάλλον ανάπτυξης σας. Εάν όχι, μπορείτε να το κατεβάσετε από το[Σελίδα λήψης Aspose.Tasks για .NET](https://releases.aspose.com/tasks/net/).
### 2. Βασική κατανόηση της C# και του .NET Framework
Μαζί με αυτό το σεμινάριο απαιτείται εξοικείωση με τη γλώσσα προγραμματισμού C# και το πλαίσιο .NET.
### 3. Αρχείο Microsoft Project
Έχετε έτοιμο ένα αρχείο Microsoft Project (MPP) που θέλετε να διαμορφώσετε και να αποθηκεύσετε ως αρχείο XLSX.

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Βήμα 1: Φορτώστε το έργο
```csharp
var project = new Project("YourProjectFile.mpp");
```
Φορτώστε το αρχείο Microsoft Project που θέλετε να διαμορφώσετε.
## Βήμα 2: Ορισμός XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Δημιουργήστε ένα παράδειγμα του`XlsxOptions` για να διαμορφώσετε τις ρυθμίσεις για αποθήκευση ως XLSX.
## Βήμα 3: Προσθήκη στηλών γραφήματος Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Προσθέστε τις επιθυμητές στήλες γραφήματος Gantt στις επιλογές.
## Βήμα 4: Προσθήκη στηλών προβολής πόρων
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Συμπεριλάβετε τις επιθυμητές στήλες για την προβολή πόρων στις επιλογές.
## Βήμα 5: Προσθήκη στηλών Προβολής Εργασίας
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Προσθέστε τις επιθυμητές στήλες για την προβολή ανάθεσης στις επιλογές.
## Βήμα 6: Ορισμός κωδικοποίησης
```csharp
options.Encoding = Encoding.Unicode;
```
Ορίστε την κωδικοποίηση για το αρχείο εξόδου.
## Βήμα 7: Αποθηκεύστε το έργο ως XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Αποθηκεύστε το έργο με τις διαμορφωμένες επιλογές ως αρχείο XLSX.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαμορφώνουμε τις επιλογές του MS Project XLSX χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να προσαρμόσετε τη μορφή εξόδου σύμφωνα με τις απαιτήσεις σας, βελτιώνοντας την ευελιξία και τη χρηστικότητα της ροής εργασιών διαχείρισης του έργου σας.
## Συχνές ερωτήσεις

### Ε: Μπορώ να διαμορφώσω διαφορετικές στήλες για το γράφημα Gantt, την προβολή πόρων και την προβολή ανάθεσης ξεχωριστά;

Α: Ναι, μπορείτε να προσαρμόσετε στήλες ανεξάρτητα για κάθε προβολή χρησιμοποιώντας το Aspose.Tasks για .NET.

### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση πριν από την αγορά του Aspose.Tasks για .NET;

 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από το[Σελίδα εκδόσεων Aspose.Tasks για .NET](https://releases.aspose.com/).

### Ε: Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα ή έχω ερωτήσεις κατά την εφαρμογή;

 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για βοήθεια από την κοινότητα και την ομάδα υποστήριξης της Aspose.

### Ε: Μπορώ να δημιουργήσω αρχεία XLSX με το Aspose.Tasks για .NET σε πλατφόρμες εκτός των Windows;

Α: Το Aspose.Tasks για .NET έχει σχεδιαστεί κυρίως για πλατφόρμες Windows, αλλά μπορείτε να εξερευνήσετε επιλογές συμβατότητας για άλλες πλατφόρμες.

### Ε: Υπάρχουν διαθέσιμες προσωρινές επιλογές άδειας για δοκιμαστικούς σκοπούς;

 Α: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια από το[Σελίδα προσωρινής άδειας Aspose.Tasks](https://purchase.aspose.com/temporary-license/).