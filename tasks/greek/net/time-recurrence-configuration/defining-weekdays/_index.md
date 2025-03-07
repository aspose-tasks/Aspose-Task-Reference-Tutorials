---
title: Mastering Weekdays στο Aspose.Tasks για .NET
linktitle: Καθορισμός εργάσιμων ημερών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε τη δύναμη του ορισμού των καθημερινών στο Aspose.Tasks .NET. Ακολουθήστε το αναλυτικό μας σεμινάριο για να διαχειριστείτε αποτελεσματικά τα ημερολόγια έργων, να προσαρμόσετε τους χρόνους εργασίας και πολλά άλλα.
weight: 10
url: /el/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Weekdays στο Aspose.Tasks για .NET

## Εισαγωγή
Εάν βυθίζεστε στον κόσμο της διαχείρισης έργων χρησιμοποιώντας το Aspose.Tasks για .NET, η κατανόηση και ο χειρισμός των καθημερινών είναι μια κρίσιμη πτυχή. Η αποτελεσματική διαχείριση και προσαρμογή των καθημερινών στο ημερολόγιο του έργου σας μπορεί να επηρεάσει σημαντικά τα χρονοδιαγράμματα του έργου. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία καθορισμού των εργάσιμων ημερών χρησιμοποιώντας το Aspose.Tasks, παρέχοντας οδηγίες βήμα προς βήμα και παραδείγματα για καλύτερη σαφήνεια.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το ταξίδι, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική κατανόηση της γλώσσας προγραμματισμού C#.
-  Εγκαταστάθηκε το Aspose.Tasks για τη βιβλιοθήκη .NET. Αν όχι, κατεβάστε το από[εδώ](https://releases.aspose.com/tasks/net/).
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Ελέγξτε την ισότητα της εβδομάδας
```csharp
// Ο κατάλογος των εγγράφων σας
String DataDir = "Your Document Directory";
// Φόρτωση αρχείου έργου
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Πρόσβαση τις καθημερινές
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Ελέγξτε την ισότητα με βάση διάφορες ιδιότητες
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Κλωνοποιήστε μια εβδομάδα
```csharp
// Φόρτωση αρχείου έργου
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Δημιουργήστε ένα βαθύ αντίγραφο της καθημερινής ημέρας
var weekDay2 = weekDay1.Clone();
// Ιδιότητες εξόδου και των δύο εργάσιμων ημερών
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Λάβετε τον κωδικό κατακερματισμού μιας εβδομάδας
```csharp
// Φόρτωση αρχείου έργου
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Ιδιότητες εξόδου και των δύο εργάσιμων ημερών
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Δημιουργήστε ένα νέο ημερολόγιο με καθορισμένες εργάσιμες ημέρες
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
// Ορίστε ένα ημερολόγιο
var calendar = project.Calendars.Add("Calendar1");
// Προσθέστε εργάσιμες ημέρες και ημέρα εξαίρεσης
// Προσθέστε παρόμοιες δηλώσεις εξόδου για FromDate και ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Ορίστε ώρες εργασίας για την Παρασκευή
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Ορίστε την προεπιλεγμένη ώρα εργασίας για μια ημέρα
```csharp
// Δημιουργήστε ένα νέο έργο
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Προσθέστε προεπιλεγμένες ώρες εργασίας για Δευτέρα έως Παρασκευή
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Επαναλάβετε για Τρίτη, Τετάρτη, Πέμπτη και Παρασκευή
// Ορίστε μη εργάσιμες ημέρες για το Σάββατο και την Κυριακή
// Προσθέστε παρόμοιες δηλώσεις εξόδου για DayWorking, FromDate, ToDate και WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε βασικές πτυχές του καθορισμού των εργάσιμων ημερών στο Aspose.Tasks για .NET. Ο χειρισμός των καθημερινών είναι μια βασική δεξιότητα για την αποτελεσματική διαχείριση του έργου. Πειραματιστείτε με τα παρεχόμενα παραδείγματα, προσαρμόστε τα στις ανάγκες του έργου σας και ξεκλειδώστε το πλήρες δυναμικό του Aspose.Tasks.
## Συχνές ερωτήσεις
### Μπορώ να ορίσω προσαρμοσμένες ώρες εργασίας για κάθε μέρα;
Ναι, μπορείτε να ορίσετε προσαρμοσμένες ώρες εργασίας για συγκεκριμένες καθημερινές χρησιμοποιώντας τα παρεχόμενα παραδείγματα.
### Είναι δυνατή η προσθήκη πολλών ημερών εξαίρεσης στο ημερολόγιο;
Απολύτως. Τροποποιήστε τον κώδικα στο τέταρτο παράδειγμα για να συμπεριλάβετε επιπλέον ημέρες εξαίρεσης.
### Πώς μπορώ να αφαιρέσω μια συγκεκριμένη ημέρα της εβδομάδας από το ημερολόγιο;
Χρησιμοποιήστε τις κατάλληλες μεθόδους που παρέχονται από τη βιβλιοθήκη Aspose.Tasks για να αφαιρέσετε τις καθημερινές όπως απαιτείται.
### Οι αλλαγές που γίνονται στις καθημερινές είναι επίμονες στο αρχείο του έργου;
Ναι, τυχόν τροποποιήσεις στις καθημερινές αντικατοπτρίζονται στο αρχείο του έργου όταν αποθηκεύονται.
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
Το Aspose.Tasks υποστηρίζει διάφορες γλώσσες προγραμματισμού, αλλά τα παραδείγματα εδώ είναι ειδικά για .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
