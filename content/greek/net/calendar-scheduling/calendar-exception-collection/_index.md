---
title: Συλλογή εξαιρέσεων ημερολογίου στο Aspose.Tasks
linktitle: Συλλογή εξαιρέσεων ημερολογίου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε αποτελεσματικά τις εξαιρέσεις ημερολογίου στα έργα σας .NET χρησιμοποιώντας το Aspose.Tasks, διασφαλίζοντας ακριβή προγραμματισμό και διαχείριση πόρων.
type: docs
weight: 13
url: /el/net/calendar-scheduling/calendar-exception-collection/
---
## Εισαγωγή

Στη διαχείριση έργου, ο ακριβής προγραμματισμός είναι ζωτικής σημασίας για την επιτυχία. Ωστόσο, τα σενάρια του πραγματικού κόσμου απαιτούν συχνά αποκλίσεις από τα τυπικά χρονοδιαγράμματα λόγω αργιών, ειδικών εκδηλώσεων ή άλλων παραγόντων. Το Aspose.Tasks για .NET παρέχει μια ισχυρή λύση για τη διαχείριση τέτοιων εξαιρέσεων μέσω της δυνατότητας συλλογής εξαιρέσεων ημερολογίου. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χρήσης αυτής της λειτουργικότητας βήμα προς βήμα.

## Προαπαιτούμενα

Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
2. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα βοηθήσει στην κατανόηση των παραδειγμάτων.
3. Περιβάλλον ανάπτυξης: Ρυθμίστε το περιβάλλον ανάπτυξης που προτιμάτε, όπως το Visual Studio ή το JetBrains Rider.

## Εισαγωγή χώρων ονομάτων

Πριν ξεκινήσετε να εργάζεστε με το Aspose.Tasks για .NET, πρέπει να εισαγάγετε τους απαιτούμενους χώρους ονομάτων στο έργο σας. Αυτό το βήμα σάς δίνει τη δυνατότητα πρόσβασης στις κλάσεις και τις μεθόδους που είναι απαραίτητες για τη διαχείριση εξαιρέσεων ημερολογίου.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Τώρα, ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα:

## Βήμα 1: Φόρτωση έργου και ανάκτηση ημερολογίου

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Σε αυτό το βήμα, φορτώνουμε ένα αρχείο έργου και ανακτούμε το επιθυμητό ημερολόγιο από το UID του.

## Βήμα 2: Διαγράψτε τις υπάρχουσες εξαιρέσεις και ορίστε το τυπικό ημερολόγιο

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Αυτό το βήμα διαγράφει τυχόν υπάρχουσες εξαιρέσεις από το ημερολόγιο και το ορίζει σε μια τυπική διαμόρφωση.

## Βήμα 3: Ορισμός και προσθήκη εξαίρεσης χρόνου εργασίας

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Αυτό το βήμα ορίζει μια εξαίρεση χρόνου εργασίας με συγκεκριμένες ημερομηνίες έναρξης και λήξης, μαζί με ώρες εργασίας εντός αυτών των ημερομηνιών, και την προσθέτει στο ημερολόγιο.

## Βήμα 4: Ορισμός και προσθήκη εξαιρέσεων μη εργάσιμου χρόνου

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Προσθέστε περισσότερες εξαιρέσεις εάν χρειάζεται

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Αυτό το βήμα ορίζει εξαιρέσεις μη εργάσιμου χρόνου, όπως αργίες, και τις προσθέτει στο ημερολόγιο.

## Βήμα 5: Εμφάνιση εξαιρέσεων ημερολογίου

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Αυτό το βήμα εμφανίζει τις προστιθέμενες εξαιρέσεις ημερολογίου μαζί με τις λεπτομέρειες τους.

## Βήμα 6: Καταργήστε όλες τις εξαιρέσεις

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Τέλος, αυτό το βήμα καταργεί όλες τις εξαιρέσεις από το ημερολόγιο.

## συμπέρασμα

Η διαχείριση εξαιρέσεων ημερολογίου είναι ζωτικής σημασίας για τον ακριβή προγραμματισμό του έργου. Το Aspose.Tasks για .NET απλοποιεί αυτήν την εργασία παρέχοντας ένα ολοκληρωμένο σύνολο δυνατοτήτων, συμπεριλαμβανομένης της συλλογής εξαιρέσεων ημερολογίου. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά διάφορα σενάρια προγραμματισμού στα έργα σας.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να προσθέσω πολλές εξαιρέσεις σε ένα μόνο ημερολόγιο;

 A1: Ναι, μπορείτε να προσθέσετε πολλές εξαιρέσεις σε ένα ημερολόγιο χρησιμοποιώντας το`AddRange` μέθοδος.

### Ε2: Πώς μπορώ να χειριστώ τις επαναλαμβανόμενες εξαιρέσεις, όπως οι εβδομαδιαίες διακοπές;

A2: Μπορείτε να υπολογίσετε μέσω προγραμματισμού επαναλαμβανόμενες εξαιρέσεις και να τις προσθέσετε στο ημερολόγιο χρησιμοποιώντας προσαρμοσμένη λογική.

### Ε3: Είναι δυνατή η εισαγωγή εξαιρέσεων ημερολογίου από εξωτερικές πηγές;

A3: Ναι, μπορείτε να διαβάσετε εξαιρέσεις ημερολογίου από εξωτερικές πηγές όπως βάσεις δεδομένων ή αρχεία CSV και να τις ενσωματώσετε στο έργο σας.

### Ε4: Τι συμβαίνει εάν υπάρχουν επικαλυπτόμενες εξαιρέσεις στο ημερολόγιο;

A4: Το Aspose.Tasks για .NET σάς επιτρέπει να χειρίζεστε επικαλυπτόμενες εξαιρέσεις ορίζοντας προτεραιότητες ή επιλύοντας διενέξεις με βάση τις απαιτήσεις του έργου σας.

### Ε5: Μπορώ να προσαρμόσω τις ώρες εργασίας για κάθε ημέρα εντός μιας εξαίρεσης;

A5: Ναι, μπορείτε να καθορίσετε προσαρμοσμένους χρόνους εργασίας για μεμονωμένες ημέρες εντός μιας εξαίρεσης για να καλύψετε συγκεκριμένες ανάγκες προγραμματισμού.