---
title: Προσαρμόστε τις Εβδομάδες Εργασίας στο Aspose.Tasks
linktitle: Συλλογή εβδομάδων εργασίας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να προσαρμόζετε τις εβδομάδες εργασίας στο Aspose.Tasks για .NET. Οδηγός βήμα προς βήμα για τη δημιουργία εξατομικευμένων ημερολογίων έργων. Κατεβάστε τώρα!
weight: 17
url: /el/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσαρμόστε τις Εβδομάδες Εργασίας στο Aspose.Tasks

## Εισαγωγή
Καλώς ήρθατε στο σεμινάριο μας για τη δημιουργία μιας προσαρμοσμένης εβδομάδας εργασίας χρησιμοποιώντας το Aspose.Tasks για .NET! Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε στη διαδικασία καθορισμού μιας εξατομικευμένης εβδομάδας εργασίας για ένα ημερολόγιο στο έργο σας. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές να εργάζονται αποτελεσματικά με έγγραφα του Microsoft Project στις εφαρμογές τους .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στον υπολογιστή σας.
2.  Aspose.Tasks για .NET: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασικές γνώσεις C#: Εξοικειωθείτε με τα βασικά της γλώσσας προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Βήμα 1: Δημιουργήστε ένα έργο και ένα ημερολόγιο
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Βήμα 2: Καθορίστε μια προσαρμοσμένη εβδομάδα εργασίας
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Βήμα 3: Ορισμός εργάσιμων ημερών
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Βήμα 4: Εμφάνιση πληροφοριών εβδομάδων εργασίας
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Αυτός ο περιεκτικός οδηγός σάς δίνει τη δυνατότητα να δημιουργείτε και να διαχειρίζεστε αποτελεσματικά προσαρμοσμένες εβδομάδες εργασίας χρησιμοποιώντας το Aspose.Tasks για .NET.
## συμπέρασμα
Συμπερασματικά, το Aspose.Tasks για .NET παρέχει μια ισχυρή λύση για το χειρισμό ημερολογίων έργων με προσαρμοσμένες εβδομάδες εργασίας. Ακολουθώντας αυτό το σεμινάριο, έχετε μάθει πώς να δημιουργείτε και να εμφανίζετε πληροφορίες σχετικά με προσαρμοσμένες εβδομάδες εργασίας στο έργο σας.
## Συχνές ερωτήσεις
### Μπορώ να έχω πολλές προσαρμοσμένες εβδομάδες εργασίας σε ένα μόνο έργο;
Ναι, μπορείτε να προσθέσετε πολλές προσαρμοσμένες εβδομάδες εργασίας σε ένα ημερολόγιο έργου.
### Πώς μπορώ να τροποποιήσω τις υπάρχουσες εβδομάδες εργασίας;
 Χρησιμοποιήστε τα παρεχόμενα`WorkWeek`ιδιότητες και μεθόδους για την τροποποίηση των υπαρχουσών εβδομάδων εργασίας.
### Είναι το Aspose.Tasks συμβατό με .NET Core;
Ναι, το Aspose.Tasks υποστηρίζει .NET Core.
### Μπορώ να εξαγάγω το έργο με προσαρμοσμένες εβδομάδες εργασίας σε μορφή αρχείου Microsoft Project;
Οπωσδήποτε, το Aspose.Tasks σάς επιτρέπει να αποθηκεύσετε το έργο σας σε διάφορες μορφές, συμπεριλαμβανομένου του Microsoft Project.
### Πού μπορώ να αναζητήσω υποστήριξη για ερωτήματα που σχετίζονται με το Aspose.Tasks;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε υποστήριξη ή βοήθεια.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
