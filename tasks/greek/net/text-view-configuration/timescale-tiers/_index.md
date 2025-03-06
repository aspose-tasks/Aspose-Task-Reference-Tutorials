---
title: Διαμόρφωση βαθμίδων χρονικής κλίμακας γραφήματος Gantt στο Aspose.Tasks
linktitle: Διαμόρφωση βαθμίδων χρονικής κλίμακας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε το Aspose.Tasks για .NET για να διαμορφώσετε τα επίπεδα χρονικής κλίμακας στην προβολή γραφήματος Gantt για ακριβή απεικόνιση του χρονοδιαγράμματος του έργου. #Aspose.Tasks #MS Project
weight: 16
url: /el/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαμόρφωση βαθμίδων χρονικής κλίμακας γραφήματος Gantt στο Aspose.Tasks

## Εισαγωγή
Στο δυναμικό τοπίο της διαχείρισης έργου, η αποτελεσματική οπτικοποίηση είναι ζωτικής σημασίας για την κατανόηση των χρονοδιαγραμμάτων και των προθεσμιών. Το Aspose.Tasks για .NET παρέχει ένα ισχυρό σύνολο εργαλείων και σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να διαμορφώνουμε τα επίπεδα χρονικής κλίμακας για βέλτιστη αναπαράσταση στην προβολή γραφήματος Gantt. Ακολουθήστε αυτές τις οδηγίες βήμα προς βήμα για να βελτιώσετε την οπτικοποίηση του έργου σας.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
- Βασικές γνώσεις C# και .NET.
-  Εγκαταστάθηκε το Aspose.Tasks για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
- Ένα περιβάλλον ανάπτυξης που έχει δημιουργηθεί για την ανάπτυξη εφαρμογών .NET.
## Εισαγωγή χώρων ονομάτων
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Τώρα, ας αναλύσουμε κάθε βήμα του παραδείγματος που παρέχεται.
## Βήμα 1: Αρχικοποίηση έργου και προσθήκη συνδέσμων εργασιών
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Εδώ, δημιουργούμε ένα έργο και καθιερώνουμε συνδέσμους εργασιών μεταξύ "Εργασία 1" και "Εργασία 2".
## Βήμα 2: Διαμορφώστε την προβολή γραφήματος Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Αποκτήστε πρόσβαση στην προβολή γραφήματος Gantt για προσαρμογή.
## Βήμα 3: Συντονίστε τη μεσαία χρονική κλίμακα
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Προσαρμόστε τη μεσαία βαθμίδα χρονικής κλίμακας για εμφάνιση εβδομάδων με συγκεκριμένες ετικέτες και ευθυγράμμιση.
## Βήμα 4: Προσθήκη Top Timescale Tier
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Προσθέστε ένα κορυφαίο επίπεδο χρονικής κλίμακας για να αντιπροσωπεύσετε μήνες.
## Βήμα 5: Προσαρμόστε τις ημερομηνίες μεσαίας βαθμίδας
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Εξατομικεύστε τις ετικέτες μήνα για καλύτερη οπτικοποίηση.
## Βήμα 6: Ορισμός χρονικής κλίμακας έργου
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Καθορίστε το χρονοδιάγραμμα του έργου για να ελέγξετε το συνολικό χρονοδιάγραμμα.
## Βήμα 7: Αποθηκεύστε το έργο με προσαρμοσμένο χρονοδιάγραμμα
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Αποθηκεύστε το έργο με τις καθορισμένες ρυθμίσεις χρονικής κλίμακας.
## συμπέρασμα
Συμπερασματικά, η διαμόρφωση βαθμίδων χρονικής κλίμακας στο Aspose.Tasks για .NET επιτρέπει μια πιο προσαρμοσμένη και οπτικά ελκυστική αναπαράσταση των χρονοδιαγραμμάτων του έργου. Αυτά τα βήματα σάς δίνουν τη δυνατότητα να δημιουργήσετε μια προβολή Διαγράμματος Gantt που ανταποκρίνεται με ακρίβεια στις ανάγκες διαχείρισης του έργου σας.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες βιβλιοθήκες .NET;
Ναι, το Aspose.Tasks ενσωματώνεται απρόσκοπτα με άλλες βιβλιοθήκες .NET, προσφέροντας ευελιξία στη στοίβα ανάπτυξης.
### Είναι διαθέσιμη μια προσωρινή άδεια για σκοπούς δοκιμής;
 Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/) για αξιολόγηση.
### Υπάρχουν πρόσθετες επιλογές προσαρμογής για την προβολή γραφήματος Gantt;
Αναμφισβήτητα, το Aspose.Tasks παρέχει εκτενείς επιλογές προσαρμογής για την προβολή γραφήματος Gantt για να ταιριάζει σε διαφορετικές απαιτήσεις έργου.
### Μπορώ να αποδώσω χρονοδιαγράμματα σε διαφορετικές μορφές;
Σίγουρα, μπορείτε να εξερευνήσετε διάφορες μορφές και στυλ για την αναπαράσταση χρονοδιαγράμματος ώστε να ταιριάζει καλύτερα στο πλαίσιο του έργου σας.
### Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.Tasks;
 Ναι, επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη και συζητήσεις.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
