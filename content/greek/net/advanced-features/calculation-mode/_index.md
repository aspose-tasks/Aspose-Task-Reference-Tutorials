---
title: Λειτουργία υπολογισμού στο Aspose.Tasks
linktitle: Λειτουργία υπολογισμού στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις λειτουργίες υπολογισμού στο Aspose.Tasks για .NET για να βελτιστοποιήσετε τον προγραμματισμό έργων και τις εξαρτήσεις εργασιών.
type: docs
weight: 29
url: /el/net/advanced-features/calculation-mode/
---
## Εισαγωγή

Το Aspose.Tasks for .NET είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project μέσω προγραμματισμού στις εφαρμογές τους .NET. Μια κρίσιμη πτυχή της εργασίας με αρχεία έργου είναι η διαχείριση των τρόπων υπολογισμού, οι οποίοι υπαγορεύουν τον τρόπο υπολογισμού και ενημέρωσης των εργασιών και των χρονοδιαγραμμάτων έργων. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στις διάφορες λειτουργίες υπολογισμού που υποστηρίζονται από το Aspose.Tasks για .NET και θα δείξουμε πώς να τις χρησιμοποιείτε αποτελεσματικά.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση του προγραμματισμού C#: Εξοικειωθείτε με τις έννοιες προγραμματισμού C#.

## Εισαγωγή χώρων ονομάτων

Πριν ξεκινήσουμε να εργαζόμαστε με το Aspose.Tasks για .NET, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων:

```csharp
using Aspose.Tasks;
using System;


```

## Εφαρμογή της λειτουργίας αυτόματου υπολογισμού

### Βήμα 1: Δημιουργήστε μια νέα παρουσία έργου

 Αρχικοποιήστε ένα νέο`Project` αντικείμενο και ορίστε το`CalculationMode` ιδιοκτησία σε`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Βήμα 2: Ορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες

Καθορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες σε αυτό.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Βήμα 3: Σύνδεση εργασιών

Δημιουργήστε εξαρτήσεις μεταξύ των εργασιών.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Βήμα 4: Επαληθεύστε τις ημερομηνίες που υπολογίστηκαν εκ νέου

Ελέγξτε εάν οι ημερομηνίες έχουν επανυπολογιστεί αυτόματα.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Προσθέστε περισσότερες επαληθεύσεις όπως απαιτείται
```

## Εφαρμογή της λειτουργίας χειροκίνητου υπολογισμού

### Βήμα 1: Δημιουργήστε μια νέα παρουσία έργου

 Αρχικοποιήστε ένα νέο`Project` αντικείμενο και ορίστε το`CalculationMode` ιδιοκτησία σε`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Βήμα 2: Ορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες

Καθορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες σε αυτό.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Βήμα 3: Επαληθεύστε τις ιδιότητες της εργασίας

Ελέγξτε εάν οι ιδιότητες εργασίας έχουν ρυθμιστεί σωστά στη χειροκίνητη λειτουργία.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Προσθέστε περισσότερες επαληθεύσεις όπως απαιτείται
```

### Βήμα 4: Συνδέστε εργασίες και επαληθεύστε ημερομηνίες

Συνδέστε τις εργασίες μεταξύ τους και ελέγξτε εάν οι ημερομηνίες τους δεν έχουν υπολογιστεί εκ νέου.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Εφαρμογή της λειτουργίας υπολογισμού "Κανένα".

### Βήμα 1: Δημιουργήστε μια νέα παρουσία έργου

 Αρχικοποιήστε ένα νέο`Project` αντικείμενο και ορίστε το`CalculationMode` ιδιοκτησία σε`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Βήμα 2: Προσθέστε μια νέα εργασία

Προσθέστε μια νέα εργασία στο έργο.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Βήμα 3: Επαληθεύστε τις ιδιότητες της εργασίας

Ελέγξτε εάν οι ιδιότητες της εργασίας δεν υπολογίζονται αυτόματα.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Προσθέστε περισσότερες επαληθεύσεις όπως απαιτείται
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τις λειτουργίες υπολογισμού που είναι διαθέσιμες στο Aspose.Tasks για .NET και μάθαμε πώς να τις εφαρμόζουμε σε πρακτικά σενάρια. Είτε χρειάζεστε αυτόματη, μη αυτόματη ή καθόλου λειτουργία υπολογισμού, το Aspose.Tasks παρέχει την ευελιξία που ταιριάζει στις απαιτήσεις του έργου σας.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να αλλάξω τη λειτουργία υπολογισμού δυναμικά κατά τη διάρκεια του χρόνου εκτέλεσης;

A1: Ναι, μπορείτε να αλλάξετε τη λειτουργία υπολογισμού ενός έργου σε οποιοδήποτε σημείο κατά τη διάρκεια του χρόνου εκτέλεσης, τροποποιώντας το`CalculationMode` ιδιοκτησία.

### Ε2: Το Aspose.Tasks υποστηρίζει άλλες μορφές αρχείων διαχείρισης έργου εκτός από το Microsoft Project;

A2: Το Aspose.Tasks εστιάζει κυρίως σε μορφές αρχείων Microsoft Project, αλλά υποστηρίζει επίσης άλλες μορφές όπως Primavera P6 XML, Primavera DB και Asta Powerproject XML.

### Ε3: Είναι το Aspose.Tasks κατάλληλο τόσο για έργα μικρής κλίμακας όσο και για έργα σε επίπεδο επιχείρησης;

Α3: Απολύτως! Το Aspose.Tasks έχει σχεδιαστεί για να καλύψει τις ανάγκες τόσο μικρής κλίμακας όσο και έργων σε επίπεδο επιχείρησης με τις ολοκληρωμένες δυνατότητες και τα ισχυρά API του.

### Ε4: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες και πλαίσια .NET;

A4: Ναι, μπορείτε να ενσωματώσετε απρόσκοπτα το Aspose.Tasks με άλλες βιβλιοθήκες και πλαίσια .NET για να βελτιώσετε τη λειτουργικότητα των εφαρμογών σας.

### Ε5: Υπάρχει κάποιο φόρουμ κοινότητας ή κανάλι υποστήριξης διαθέσιμο για τους χρήστες του Aspose.Tasks;

 A5: Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη και συζητήσεις.