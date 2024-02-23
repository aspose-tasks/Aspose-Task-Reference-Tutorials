---
title: Διαχείριση της συλλογής τύπων ημέρας στο Aspose.Tasks
linktitle: Διαχείριση της συλλογής τύπων ημέρας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις συλλογές τύπων ημέρας στο Aspose.Tasks για .NET. Δημιουργήστε, τροποποιήστε και χειριστείτε τις εξαιρέσεις ημερολογίου με ευκολία.
type: docs
weight: 28
url: /el/net/calendar-scheduling/day-type-collection/
---
## Εισαγωγή

 Το Aspose.Tasks για .NET παρέχει ισχυρή λειτουργικότητα για τη διαχείριση συλλογών τύπων ημέρας, ζωτικής σημασίας για τον καθορισμό εβδομαδιαίων εξαιρέσεων ημερολογίου σε εφαρμογές διαχείρισης έργων. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χρησιμοποιήσετε το`DayTypeCollection` τάξη αποτελεσματικά. 

## Προαπαιτούμενα

Πριν προχωρήσουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασικές γνώσεις C#: Εξοικείωση με τη γλώσσα προγραμματισμού C# και τις έννοιες .NET Framework.

## Εισαγωγή χώρων ονομάτων

Για να ξεκινήσετε, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας C#:

```csharp
using Aspose.Tasks;
using System;


```

Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα:

## Βήμα 1: Φόρτωση έργου και πρόσβαση στο Ημερολόγιο

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Αυτό το βήμα αρχικοποιεί μια νέα παρουσία έργου και ανακτά το ημερολόγιο από το UID του.

## Βήμα 2: Επανάληψη μέσω εξαιρέσεων ημερολογίου

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Εδώ, επαναλαμβάνουμε κάθε εξαίρεση ημερολογίου και εκτυπώνουμε το όνομά της και τους σχετικούς τύπους ημερών.

## Βήμα 3: Τροποποίηση εξαιρέσεων ημερολογίου

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Αυτό το βήμα δείχνει πώς μπορείτε να τροποποιήσετε τις εξαιρέσεις ημερολογίου προσθέτοντας, αφαιρώντας ή ενημερώνοντας τύπους ημερών.

## Βήμα 4: Δημιουργία και χειρισμός νέων εξαιρέσεων ημερολογίου

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Σε αυτό το τελευταίο βήμα, δημιουργούμε νέες εξαιρέσεις ημερολογίου και τις χειριζόμαστε προσθέτοντας και αντιγράφοντας τύπους ημερών.

## συμπέρασμα

 Συμπερασματικά, η διαχείριση συλλογών τύπων ημέρας στο Aspose.Tasks για .NET είναι απαραίτητη για τον καθορισμό και την τροποποίηση εβδομαδιαίων εξαιρέσεων ημερολογίου σε εφαρμογές διαχείρισης έργων. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε να χρησιμοποιήσετε αποτελεσματικά το`DayTypeCollection` κλάση για να χειριστεί διάφορες λειτουργίες ημερολογίου.

## Συχνές ερωτήσεις

### Ε1: Μπορεί το Aspose.Tasks για .NET να χρησιμοποιηθεί για τη δημιουργία γραφημάτων Gantt μέσω προγραμματισμού;

A1: Ναι, το Aspose.Tasks για .NET παρέχει API για τη δημιουργία και τον χειρισμό γραφημάτων Gantt σε εφαρμογές .NET.

### Ε2: Είναι το Aspose.Tasks για .NET συμβατό τόσο με .NET Core όσο και με .NET Framework;

A2: Ναι, το Aspose.Tasks για .NET υποστηρίζει τόσο .NET Core όσο και .NET Framework.

### Ε3: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για .NET;

 A3: Μπορείτε να λάβετε υποστήριξη μεταβαίνοντας στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) όπου μπορείτε να κάνετε ερωτήσεις και να αλληλεπιδράτε με άλλους χρήστες.

### Ε4: Το Aspose.Tasks για .NET προσφέρει δωρεάν δοκιμή;

 A4: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/).

### Ε5: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για .NET;

 A5: Ναι, οι προσωρινές άδειες είναι διαθέσιμες για αγορά από το[Aspose ιστότοπο](https://purchase.aspose.com/temporary-license/).