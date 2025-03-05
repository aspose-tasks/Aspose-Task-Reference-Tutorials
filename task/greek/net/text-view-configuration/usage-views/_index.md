---
title: Διαμόρφωση προβολών χρήσης στο Aspose.Tasks
linktitle: Διαμόρφωση προβολών χρήσης στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε να διαμορφώνετε τις προβολές χρήσης εργασιών στο Aspose.Tasks για .NET. Βελτιώστε την οπτικοποίηση του έργου με λεπτομερή βήματα. Κατεβάστε τη βιβλιοθήκη τώρα!
type: docs
weight: 17
url: /el/net/text-view-configuration/usage-views/
---
## Εισαγωγή
Εάν είστε προγραμματιστής .NET που θέλει να βελτιώσει τις δυνατότητες διαχείρισης του έργου σας, το Aspose.Tasks είναι ένα ισχυρό εργαλείο που σας επιτρέπει να χειρίζεστε τα αρχεία του Microsoft Project χωρίς κόπο. Σε αυτό το σεμινάριο, θα επικεντρωθούμε στη διαμόρφωση των προβολών χρήσης χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθήστε για να αποκτήσετε πληροφορίες σχετικά με την απόδοση προβολών χρήσης εργασιών με λεπτομέρειες για καλύτερη οπτικοποίηση του έργου.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Aspose.Tasks Library: Βεβαιωθείτε ότι έχετε ενσωματωμένη τη βιβλιοθήκη Aspose.Tasks στο έργο σας .NET. Εάν όχι, μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/) και ακολουθήστε τις οδηγίες εγκατάστασης.
- Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο όπου αποθηκεύονται τα έγγραφα του έργου σας. Αντικαταστήστε το "Ο Κατάλογος Εγγράφων σας" στα αποσπάσματα κώδικα με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.
## Εισαγωγή χώρων ονομάτων
Στο παρεχόμενο απόσπασμα κώδικα, θα παρατηρήσετε τη χρήση ορισμένων χώρων ονομάτων. Φροντίστε να τα συμπεριλάβετε στο έργο σας για απρόσκοπτη ενσωμάτωση:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## Βήμα 1: Απόδοση Προβολή χρήσης εργασιών με λεπτομέρειες
Ας ξεκινήσουμε αποδίδοντας μια προβολή χρήσης εργασιών με λεπτομέρειες. Ακολουθήστε αυτά τα βήματα:
## Βήμα 1.1: Φόρτωση έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Βήμα 1.2: Λάβετε την προβολή
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Βήμα 1.3: Προσαρμογή ρυθμίσεων προβολής
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Βήμα 1.4: Αποθήκευση έργου ως PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Βήμα 2: Εμφάνιση στήλης κεφαλίδας λεπτομερειών
Σε αυτό το βήμα, θα τροποποιήσουμε τις ρυθμίσεις προβολής για να εμφανίσουμε τη στήλη κεφαλίδας λεπτομερειών και να αποθηκεύσουμε το έργο ως PDF:
## Βήμα 2.1: Εμφάνιση στήλης κεφαλίδας λεπτομερειών
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Βήμα 2.2: Επαναλάβετε την κεφαλίδα λεπτομερειών σε όλες τις σειρές
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Βήμα 2.3: Αποθήκευση έργου ως PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## συμπέρασμα
Συγχαρητήρια! Διαμορφώσατε με επιτυχία τις προβολές χρήσης στο Aspose.Tasks. Αυτό το σεμινάριο παρέχει τη βάση για αποτελεσματική διαχείριση και οπτικοποίηση έργου χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks.

### Συχνές ερωτήσεις
### Ε: Πού μπορώ να βρω την τεκμηρίωση του Aspose.Tasks;
 Η πλήρης τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tasks/net/).
### Ε: Πώς μπορώ να κατεβάσω το Aspose.Tasks για .NET;
 Κατεβάστε τη βιβλιοθήκη[εδώ](https://releases.aspose.com/tasks/net/).
### Ε: Πού μπορώ να αγοράσω το Aspose.Tasks;
 Μπορείτε να αγοράσετε το Aspose.Tasks[εδώ](https://purchase.aspose.com/buy).
### Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, εξερευνήστε τη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Χρειάζεστε υποστήριξη ή έχετε ερωτήσεις;
 Επισκεφτείτε το φόρουμ υποστήριξης[εδώ](https://forum.aspose.com/c/tasks/15).