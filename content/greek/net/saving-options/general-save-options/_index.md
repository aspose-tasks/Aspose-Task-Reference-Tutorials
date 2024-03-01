---
title: Mastering MS Project Save Options for Aspose.Tasks
linktitle: Γενικές επιλογές αποθήκευσης για το Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε να αποθηκεύετε αποτελεσματικά αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε τις επιλογές εξόδου χωρίς κόπο για τα έργα σας.
type: docs
weight: 17
url: /el/net/saving-options/general-save-options/
---
## Εισαγωγή
Το Aspose.Tasks για .NET προσφέρει ισχυρές δυνατότητες για τον προγραμματισμό των αρχείων του Microsoft Project. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στις περιπλοκές της αποθήκευσης αρχείων MS Project χρησιμοποιώντας διάφορες επιλογές που παρέχονται από το Aspose.Tasks. Συγκεκριμένα, θα εστιάσουμε στις γενικές επιλογές αποθήκευσης που είναι διαθέσιμες για το Aspose.Tasks, επιτρέποντάς σας να προσαρμόσετε το αποτέλεσμα στις συγκεκριμένες απαιτήσεις σας.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Εγκατάσταση του Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από το[σύνδεσμος λήψης](https://releases.aspose.com/tasks/net/).
2. Βασική κατανόηση του .NET Framework: Η εξοικείωση με τις έννοιες προγραμματισμού .NET είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Πριν βουτήξετε στον κώδικα, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Βήμα 1: Φορτώστε το Αρχείο Έργου
Αρχικά, πρέπει να φορτώσετε το αρχείο MS Project χρησιμοποιώντας το Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Βήμα 2: Ορίστε τις επιλογές αποθήκευσης
 Καθορίστε τις επιλογές αποθήκευσης σύμφωνα με τις απαιτήσεις σας. Σε αυτό το παράδειγμα, χρησιμοποιούμε`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Βήμα 3: Προσαρμογή στηλών προβολής
Μπορείτε να προσαρμόσετε στήλες προβολής, όπως γράφημα Gantt, προβολή πόρων και προβολή ανάθεσης. Δείτε πώς μπορείτε να προσθέσετε στήλες σε καθεμία:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Βήμα 4: Αποθηκεύστε το έργο με Επιλογές
Τέλος, αποθηκεύστε το έργο με τις καθορισμένες επιλογές:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## συμπέρασμα
Η εξοικείωση με τις γενικές επιλογές αποθήκευσης του MS Project με το Aspose.Tasks για .NET σάς δίνει τη δυνατότητα να προσαρμόσετε αποτελεσματικά τη μορφή εξόδου σύμφωνα με τις ανάγκες του έργου σας.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων MS Project;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.
### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks πριν από την αγορά;
 Α: Ναι, μπορείτε να εξερευνήσετε το Aspose.Tasks με διαθέσιμη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks;
 Α: Μπορείτε να βρείτε αναλυτική τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/), παρέχοντας ολοκληρωμένη καθοδήγηση σχετικά με τη χρήση των δυνατοτήτων Aspose.Tasks.
### Ε: Πώς μπορώ να αποκτήσω προσωρινές άδειες για το Aspose.Tasks;
 Α: Διατίθενται προσωρινές άδειες για σκοπούς αξιολόγησης[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να αναζητήσω υποστήριξη για ερωτήματα που σχετίζονται με το Aspose.Tasks;
 Α: Μπορείτε να εγγραφείτε στο φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15)για να λάβετε βοήθεια από ειδικούς και συναδέλφους προγραμματιστές.