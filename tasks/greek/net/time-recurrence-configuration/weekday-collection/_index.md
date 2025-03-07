---
title: Mastering Weekdays στο Aspose.Tasks
linktitle: Συλλογή εργάσιμων ημερών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ανακαλύψτε τη δύναμη του Aspose.Tasks για το .NET στην αβίαστη διαχείριση των καθημερινών. Προσαρμόστε τις εργάσιμες ημέρες, αφαιρέστε τα Σαββατοκύριακα και δημιουργήστε εξειδικευμένα ημερολόγια με ευκολία.
weight: 11
url: /el/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Weekdays στο Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks for .NET είναι μια ισχυρή βιβλιοθήκη που διευκολύνει τον αποτελεσματικό χειρισμό των δεδομένων διαχείρισης έργου. Σε αυτό το σεμινάριο, θα εξερευνήσουμε τη συλλογή των καθημερινών στο Aspose.Tasks, δίνοντάς σας τη δυνατότητα να προσαρμόσετε τις εργάσιμες ημέρες, να αφαιρέσετε τα Σαββατοκύριακα και να δημιουργήσετε εξειδικευμένα ημερολόγια για να ανταποκρίνονται στις απαιτήσεις του έργου σας. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος, αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία εργασίας με τις καθημερινές στο Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από το[Σελίδα λήψης Aspose.Tasks για .NET](https://releases.aspose.com/tasks/net/).
- Εξοικείωση με τη γλώσσα προγραμματισμού C#.
- Ενσωματωμένο περιβάλλον ανάπτυξης (IDE) όπως το Visual Studio.
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Βήμα 1: Δημιουργήστε μια παρουσία έργου
Εκκινήστε ένα νέο έργο Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Βήμα 2: Πρόσβαση στο Ημερολόγιο
Ανακτήστε το ημερολόγιο του έργου:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Βήμα 3: Προσαρμόστε τις καθημερινές
Διαγράψτε τις υπάρχουσες καθημερινές και ορίστε τις προεπιλεγμένες εργάσιμες ημέρες:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Προσθέστε και άλλες καθημερινές με παρόμοιο τρόπο...
```
## Βήμα 4: Προσθήκη ωρών εργασίας
Προσθήκη ωρών εργασίας για συγκεκριμένες καθημερινές:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Βήμα 5: Εμφάνιση πληροφοριών ημερολογίου
Εξαγωγή λεπτομερειών ημερολογίου στην κονσόλα:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Εμφάνιση κάθε καθημερινής και ωρών εργασίας...
```
## Βήμα 6: Καταργήστε τα Σαββατοκύριακα
Αφαιρέστε το Σάββατο και την Κυριακή από τις καθημερινές:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Βήμα 7: Εμφάνιση ενημερωμένων ωρών εργασίας
Έξοδος ενημερωμένων ωρών εργασίας μετά την κατάργηση των Σαββατοκύριακων:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Εμφάνιση κάθε ενημερωμένης ημέρας και ωρών εργασίας...
```
## Βήμα 8: Δημιουργήστε ένα 24ωρο ημερολόγιο
Δημιουργήστε ένα ημερολόγιο 24 ωρών και αντιγράψτε τις καθημερινές:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τις ισχυρές δυνατότητες του Aspose.Tasks για .NET στη διαχείριση των καθημερινών στα ημερολόγια έργων. Από την προσαρμογή των εργάσιμων ημερών έως τη δημιουργία εξειδικευμένων ημερολογίων 24 ωρών, το Aspose.Tasks απλοποιεί τη διαδικασία, προσφέροντας ευελιξία και έλεγχο στη διαχείριση έργων.
## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλες γλώσσες προγραμματισμού;
Α: Το Aspose.Tasks υποστηρίζει κυρίως γλώσσες .NET, αλλά προσφέρει επίσης εκδόσεις για Java.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από το[Σελίδα εκδόσεων Aspose.Tasks](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για .NET;
 Α: Επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη ή σκεφτείτε να αγοράσετε ένα σχέδιο υποστήριξης.
### Ε: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks για .NET;
 Α: Ανατρέξτε στο[Aspose.Tasks για τεκμηρίωση .NET](https://reference.aspose.com/tasks/net/) για αναλυτικές πληροφορίες.
### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για .NET;
 Α: Μπορείτε να αποκτήσετε μια προσωρινή άδεια από το[σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
