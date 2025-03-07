---
title: Mastering Data Project με το Aspose.Tasks
linktitle: Εργασία με δεδομένα έργου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε τα δεδομένα του Microsoft Project χρησιμοποιώντας το Aspose.Tasks στο .NET. Δημιουργήστε εργασίες, προσθέστε πόρους και αποθηκεύστε έργα με ευκολία.
weight: 16
url: /el/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Data Project με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε τον τρόπο εργασίας με τα δεδομένα του Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για .NET. Το Aspose.Tasks παρέχει ισχυρές δυνατότητες για τον χειρισμό αρχείων έργου, όπως δημιουργία εργασιών, προσθήκη πόρων, ρύθμιση ιδιοτήτων και αποθήκευση έργων σε διάφορες μορφές.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Εγκατάσταση της βιβλιοθήκης Aspose.Tasks: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks από[εδώ](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης .NET.
3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Πριν εργαστείτε με το Aspose.Tasks, εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Βήμα 1: Αρχικοποίηση αντικειμένου έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Αυτή η γραμμή αρχικοποιεί μια νέα παρουσία του`Project` κλάση, η οποία αντιπροσωπεύει ένα αρχείο Microsoft Project.
## Βήμα 2: Ορισμός ιδιοτήτων έργου
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Αυτές οι γραμμές δείχνουν πώς να ορίσετε ιδιότητες του έργου, όπως τη μορφή εργασίας και τη λειτουργία δημιουργίας εργασιών.
## Βήμα 3: Προσθήκη εργασιών
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Εδώ, μια νέα εργασία με το όνομα "Εργασία 1" προστίθεται στη βασική εργασία του έργου.
## Βήμα 4: Ρύθμιση ιδιοτήτων εργασίας
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Αυτές οι γραμμές ορίζουν την ημερομηνία έναρξης, τη διάρκεια και την ημερομηνία λήξης για την "Εργασία 1".
## Βήμα 5: Προσθήκη πόρων
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Αυτό το μέρος δείχνει πώς να προσθέσετε έναν πόρο εργασίας στο έργο.
## Βήμα 6: Εκχώρηση πόρων σε εργασίες
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Αυτές οι γραμμές δείχνουν πώς να αντιστοιχίσετε τον πόρο εργασίας που προστέθηκε προηγουμένως στην "Εργασία 1" με συγκεκριμένες ημερομηνίες έναρξης, εργασίας και λήξης.
## Βήμα 7: Αποθήκευση έργου
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Τέλος, το έργο αποθηκεύεται σε μορφή αρχείου Microsoft Project XML.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εργαζόμαστε με δεδομένα του Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks στο .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να χειριστείτε αρχεία έργου, να προσθέσετε εργασίες, πόρους, να εκχωρήσετε πόρους σε εργασίες και να αποθηκεύσετε έργα σε διάφορες μορφές.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks να χειριστεί πολύπλοκες δομές έργου;
Α: Ναι, το Aspose.Tasks παρέχει ολοκληρωμένη υποστήριξη για πολύπλοκες δομές έργων, επιτρέποντάς σας να διαχειρίζεστε αποτελεσματικά εργασίες, πόρους και αναθέσεις.
### Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα εκδόσεων του Microsoft Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.
### Ε: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες .NET;
Α: Απολύτως, το Aspose.Tasks ενσωματώνεται άψογα με άλλες βιβλιοθήκες .NET, παρέχοντας ευελιξία στα αναπτυξιακά σας έργα.
### Ε: Το Aspose.Tasks προσφέρει υποστήριξη για αλγόριθμους προγραμματισμού έργων;
Α: Ναι, το Aspose.Tasks περιλαμβάνει προηγμένους αλγόριθμους προγραμματισμού για να σας βοηθήσει να βελτιστοποιήσετε τα χρονοδιαγράμματα του έργου και τη χρήση των πόρων.
### Ε: Υπάρχει κάποιο φόρουμ κοινότητας για χρήστες Aspose.Tasks;
 Α: Ναι, μπορείτε να βρείτε χρήσιμους πόρους και να αλληλεπιδράσετε με άλλους χρήστες του Aspose.Tasks στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
