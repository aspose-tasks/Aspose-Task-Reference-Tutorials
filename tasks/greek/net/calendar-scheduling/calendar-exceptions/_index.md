---
title: Χειρισμός εξαιρέσεων ημερολογίου στο Aspose.Tasks
linktitle: Χειρισμός εξαιρέσεων ημερολογίου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τις εξαιρέσεις ημερολογίου στο Aspose.Tasks για .NET με οδηγίες βήμα προς βήμα και παραδείγματα.
weight: 12
url: /el/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Χειρισμός εξαιρέσεων ημερολογίου στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο διαχείρισης εξαιρέσεων ημερολογίου στο Aspose.Tasks χρησιμοποιώντας το πλαίσιο .NET. Οι εξαιρέσεις ημερολογίου μας επιτρέπουν να ορίζουμε ειδικές ημερομηνίες ή περιόδους σε ένα ημερολόγιο έργου όπου το κανονικό πρόγραμμα εργασίας αλλάζει, όπως αργίες ή προσωρινά κλεισίματα. Θα καλύψουμε διάφορες μεθόδους για τον χειρισμό εξαιρέσεων ημερολογίου βήμα προς βήμα, χρησιμοποιώντας το Aspose.Tasks για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις γλώσσας προγραμματισμού C#.
- Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
- Η βιβλιοθήκη Aspose.Tasks για .NET προστέθηκε στο έργο σας.

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισάγουμε τους απαραίτητους χώρους ονομάτων για το έργο μας:

```csharp
using Aspose.Tasks;
using System;


```

## Βήμα 1: Διαγραφή εξαίρεσης ημερολογίου

Για να διαγράψετε μια εξαίρεση ημερολογίου, ακολουθήστε τα εξής βήματα:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Εμφάνιση πληροφοριών ημερολογίου
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Καταργήστε την πρώτη εξαίρεση
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Βήμα 2: Λήψη χρόνου εργασίας μιας εξαίρεσης ημερολογίου

Για να ανακτήσετε τον χρόνο εργασίας μιας εξαίρεσης ημερολογίου, ακολουθήστε τα εξής βήματα:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Εμφάνιση πληροφοριών ημερολογίου και εξαιρέσεων
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Λάβετε τον χρόνο εργασίας και δείτε λεπτομέρειες
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Βήμα 3: Καθορισμός εξαιρέσεων ημερολογίου

Για να προσθέσετε ή να αφαιρέσετε εξαιρέσεις ημερολογίου, ακολουθήστε τα εξής βήματα:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Δημιουργήστε μια νέα εξαίρεση ημερολογίου
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Ορισμός λεπτομερειών εξαίρεσης
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Ελέγξτε εάν μια ημερομηνία αποτελεί εξαίρεση
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Προσθέστε την εξαίρεση στο ημερολόγιο
    calendar.Exceptions.Add(exception);

    // Καταργήστε μια εξαίρεση εάν υπάρχει
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Προσθέστε μια νέα εξαίρεση
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Εξαιρέσεις εκτύπωσης
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## συμπέρασμα

Σε αυτό το άρθρο, καλύψαμε διάφορες πτυχές του χειρισμού εξαιρέσεων ημερολογίου στο Aspose.Tasks για .NET. Ακολουθώντας τα παρεχόμενα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τις εξαιρέσεις στα χρονοδιαγράμματα του έργου σας, διασφαλίζοντας την ακριβή αναπαράσταση των ωρών εργασίας και των ειδικών εκδηλώσεων.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να προσθέσω πολλές εξαιρέσεις σε ένα μόνο ημερολόγιο;

A1: Ναι, μπορείτε να προσθέσετε πολλές εξαιρέσεις σε ένα ημερολόγιο για να χωρέσουν διάφορες ειδικές ημερομηνίες ή περιόδους.

### Ε2: Πώς μπορώ να ελέγξω εάν μια συγκεκριμένη ημερομηνία αποτελεί εξαίρεση;

 A2: Μπορείτε να χρησιμοποιήσετε το`CheckException()` μέθοδος επαλήθευσης εάν μια συγκεκριμένη ημερομηνία εμπίπτει σε εξαίρεση.

### Ε3: Είναι δυνατή η κατάργηση μιας υπάρχουσας εξαίρεσης από ένα ημερολόγιο;

 A3: Ναι, μπορείτε να καταργήσετε εξαιρέσεις μεταβαίνοντας στο`Exceptions` συλλογή του ημερολογίου και χρήση του`Remove()` μέθοδος.

### Ε4: Ποιοι τύποι εξαιρέσεων ημερολογίου υποστηρίζονται;

A4: Το Aspose.Tasks υποστηρίζει διάφορους τύπους εξαιρέσεων, συμπεριλαμβανομένων ημερήσιων, εβδομαδιαίων, μηνιαίων και ετήσιων εξαιρέσεων, παρέχοντας ευελιξία στον καθορισμό κανόνων εξαίρεσης.

### Ε5: Μπορώ να προσαρμόσω τις ώρες εργασίας για συγκεκριμένες ημερομηνίες εξαίρεσης;

A5: Ναι, μπορείτε να ορίσετε προσαρμοσμένους χρόνους εργασίας για μεμονωμένες ημερομηνίες εξαίρεσης χρησιμοποιώντας τις κατάλληλες μεθόδους που παρέχονται από το Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
