---
title: Οδηγός προσαρμογής στυλ κειμένου πίνακα στο Aspose.Tasks
linktitle: Διαμόρφωση στυλ κειμένου πίνακα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Βελτιώστε την οπτικοποίηση έργου με το Aspose.Tasks για .NET. Μάθετε να διαμορφώνετε τα στυλ κειμένου πίνακα βήμα προς βήμα. Ενισχύστε την αποτελεσματικότητα και την παρουσίαση.
type: docs
weight: 14
url: /el/net/task-table-management/table-text-styles/
---
## Εισαγωγή
Στον κόσμο της διαχείρισης έργων, η αποτελεσματική απεικόνιση των εργασιών είναι ζωτικής σημασίας για την επιτυχία. Το Aspose.Tasks για .NET παρέχει μια ισχυρή λύση για την προσαρμογή στυλ κειμένου πίνακα, επιτρέποντάς σας να προσαρμόσετε την εμφάνιση των στοιχείων κειμένου στο έργο σας. Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε στη διαδικασία διαμόρφωσης στυλ κειμένου πίνακα χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
- Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκατεστημένη την πιο πρόσφατη έκδοση του Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
- Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο για τα έγγραφά σας. Αντικαταστήστε τον "Ο Κατάλογος Εγγράφων σας" στον κώδικα με την πραγματική διαδρομή.
-  Valid Aspose License: Αυτό το παράδειγμα απαιτεί μια έγκυρη άδεια Aspose. Μπορείτε να αγοράσετε μια πλήρη άδεια[εδώ](https://purchase.aspose.com/buy) ή αποκτήστε προσωρινή άδεια 30 ημερών[εδώ](https://purchase.aspose.com/temporary-license/).
## Εισαγωγή χώρων ονομάτων
Πριν ξεκινήσετε την κωδικοποίηση, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τις λειτουργίες του Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Τώρα, ας αναλύσουμε το παράδειγμα σε πολλά βήματα:
## Βήμα 1: Φόρτωση έργου και ορισμός ιδιοτήτων έργου
```csharp
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.NewTasksAreManual, false);
```
## Βήμα 2: Αποκτήστε πρόσβαση στην προβολή γραφήματος Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
## Βήμα 3: Προσαρμόστε το στυλ κειμένου του ονόματος εργασίας
```csharp
var style1 = new TableTextStyle(1);
style1.Field = Field.TaskName;
style1.Font = new FontDescriptor("Impact", 12F, FontStyles.Bold | FontStyles.Italic);
view.TableTextStyles.Add(style1);
```
## Βήμα 4: Προσαρμόστε το στυλ κειμένου διάρκειας εργασίας
```csharp
var style2 = new TableTextStyle(2);
style2.Field = Field.TaskDurationText;
style2.Font = new FontDescriptor("Impact", 16F, FontStyles.Underline);
view.TableTextStyles.Add(style2);
```
## Βήμα 5: Αποθηκεύστε το έργο με προσαρμοσμένα στυλ
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(DataDir + "WorkWithTableTextStyle_out.mpp", options);
```
## Βήμα 6: Χειριστείτε την εξαίρεση άδειας χρήσης
```csharp
catch (NotSupportedException ex)
{
    Console.WriteLine(
        ex.Message
        + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [Aspose](http://www.aspose.com/purchase/default.aspx).");
}
```
## συμπέρασμα
Η προσαρμογή στυλ κειμένου πίνακα στο Aspose.Tasks για .NET παρέχει έναν ευέλικτο και αποτελεσματικό τρόπο για να βελτιώσετε την οπτική αναπαράσταση του έργου σας. Με μερικά απλά βήματα, μπορείτε να δημιουργήσετε μια πιο προσαρμοσμένη και αποτελεσματική εμπειρία διαχείρισης έργου.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET χωρίς άδεια χρήσης;
 Όχι, απαιτείται έγκυρη άδεια Aspose για αυτήν τη λειτουργία. Μπορείτε να αποκτήσετε άδεια[εδώ](https://purchase.aspose.com/buy) ή πάρτε μια προσωρινή άδεια 30 ημερών[εδώ](https://purchase.aspose.com/temporary-license/).
### Πώς μπορώ να ενημερώσω το στυλ γραμματοσειράς για άλλα χαρακτηριστικά εργασιών;
 Απλώς δημιουργήστε επιπλέον`TableTextStyle` περιπτώσεις, καθορίζοντας το επιθυμητό πεδίο και τις ρυθμίσεις γραμματοσειράς.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;
 Ναι, μπορείτε να κάνετε λήψη της δοκιμαστικής έκδοσης[εδώ](https://releases.aspose.com/).
### Υπάρχουν άλλες επιλογές οπτικοποίησης που παρέχονται από το Aspose.Tasks;
Ναι, το Aspose.Tasks προσφέρει διάφορες δυνατότητες οπτικοποίησης για την κάλυψη διαφορετικών αναγκών διαχείρισης έργου.
### Μπορώ να προσαρμόσω στυλ για συγκεκριμένους τύπους εργασιών;
Οπωσδήποτε, μπορείτε να επεκτείνετε την προσαρμογή σε διαφορετικούς τύπους εργασιών προσαρμόζοντας ανάλογα το πεδίο και τις ρυθμίσεις γραμματοσειράς.