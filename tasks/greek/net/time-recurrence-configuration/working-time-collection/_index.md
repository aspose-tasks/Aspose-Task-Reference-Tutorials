---
title: Mastering Working Times στο Aspose.Tasks
linktitle: Συλλογή ωρών εργασίας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε τη δύναμη του Aspose.Tasks για το .NET στην αποτελεσματική διαχείριση των χρονοδιαγραμμάτων έργων. Προσαρμόστε τα ημερολόγια, ορίστε ώρες εργασίας και απλοποιήστε τα έργα σας με ευκολία.
weight: 14
url: /el/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Working Times στο Aspose.Tasks

## Εισαγωγή
Ψάχνετε να κατακτήσετε την τέχνη της διαχείρισης του χρόνου εργασίας στο Aspose.Tasks για .NET; Μην ψάχνετε άλλο! Σε αυτόν τον οδηγό βήμα προς βήμα, θα εμβαθύνουμε στις περιπλοκές της συλλογής του χρόνου εργασίας χρησιμοποιώντας το Aspose.Tasks, δίνοντάς σας τη δυνατότητα να χειρίζεστε αποτελεσματικά προσαρμοσμένα ημερολόγια και να εξορθολογίζετε τα χρονοδιαγράμματα του έργου σας.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το ταξίδι, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Aspose.Tasks for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for .NET από το[Σελίδα έκδοσης Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Περιβάλλον εργασίας: Ρυθμίστε ένα κατάλληλο περιβάλλον ανάπτυξης, κατά προτίμηση χρησιμοποιώντας ένα IDE συμβατό με .NET.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στις λειτουργίες Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Τώρα, ας αναλύσουμε το σεμινάριο σε πολλά βήματα, διασφαλίζοντας μια ομαλή εμπειρία εκμάθησης.
## Βήμα 1: Δημιουργήστε ένα προσαρμοσμένο ημερολόγιο
Ξεκινήστε δημιουργώντας ένα νέο έργο και προσθέτοντας ένα προσαρμοσμένο ημερολόγιο σε αυτό:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Βήμα 2: Καθορισμός εργάσιμων ημερών
Ρύθμιση προεπιλεγμένων εργάσιμων ημερών από Δευτέρα έως Παρασκευή:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Βήμα 3: Διαμορφώστε τις ώρες εργασίας του Σαββάτου
Καθορίστε τις ώρες εργασίας για τα Σάββατα:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Βήμα 4: Εκτύπωση περιόδων εργασίας του Σαββάτου
Εκτυπώστε τις διαμορφωμένες ώρες εργασίας για το Σάββατο:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Βήμα 5: Διαμορφώστε τις ώρες εργασίας της Κυριακής
Καθορίστε τις ώρες εργασίας για τις Κυριακές:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Βήμα 6: Εκτύπωση κυριακάτικων εργάσιμων περιόδων
Εκτυπώστε τις διαμορφωμένες ώρες εργασίας για την Κυριακή:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Βήμα 7: Προσθέστε προσαρμοσμένες ημέρες στο Ημερολόγιο
Συμπεριλάβετε το διαμορφωμένο Σάββατο και Κυριακή στο ημερολόγιο:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Βήμα 8: Διασχίστε τους χρόνους εργασίας
Διασχίστε τις ώρες εργασίας και εμφανίστε τις για κάθε μέρα στο ημερολόγιο:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Τώρα που έχετε πλοηγηθεί με επιτυχία στα βήματα, είστε εξοπλισμένοι για να αξιοποιήσετε τη δύναμη του Aspose.Tasks για το .NET στην αποτελεσματική διαχείριση των χρόνων εργασίας.
## συμπέρασμα
Η γνώση της συλλογής των χρόνων εργασίας στο Aspose.Tasks σάς δίνει τη δυνατότητα να προσαρμόσετε τα ημερολόγια έργων, διασφαλίζοντας ακριβή προγραμματισμό και αποτελεσματική χρήση των πόρων. Βουτήξτε στα έργα σας με αυτοπεποίθηση, οπλισμένοι με τη γνώση που αποκτήθηκε από αυτόν τον περιεκτικό οδηγό.
## Συχνές Ερωτήσεις
### Είναι το Aspose.Tasks κατάλληλο για διαχείριση έργων μεγάλης κλίμακας;
Ναι, το Aspose.Tasks έχει σχεδιαστεί για να χειρίζεται έργα διαφορετικών μεγεθών, παρέχοντας ισχυρές δυνατότητες για αποτελεσματική διαχείριση έργων.
### Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες .NET;
Σίγουρα! Το Aspose.Tasks ενσωματώνεται απρόσκοπτα με άλλες βιβλιοθήκες .NET, ενισχύοντας την ευελιξία και τη συμβατότητά του.
### Πόσο συχνά ενημερώνεται το Aspose.Tasks;
 Το Aspose.Tasks ενημερώνεται τακτικά για να ενσωματώνει νέες δυνατότητες, βελτιώσεις και βελτιώσεις συμβατότητας. Ελεγξε το[σελίδα έκδοσης](https://releases.aspose.com/tasks/net/) για τις τελευταίες ενημερώσεις.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Ναι, μπορείτε να εξερευνήσετε το Aspose.Tasks με μια δωρεάν δοκιμή μεταβαίνοντας στη διεύθυνση[αυτός ο σύνδεσμος](https://releases.aspose.com/).
### Πού μπορώ να αναζητήσω υποστήριξη για το Aspose.Tasks;
 Για οποιαδήποτε απορία ή βοήθεια, επισκεφθείτε το[Φόρουμ υποστήριξης Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
