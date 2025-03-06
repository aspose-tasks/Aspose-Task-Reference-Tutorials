---
title: Διαχείριση της συλλογής ημερολογίου στο Aspose.Tasks
linktitle: Διαχείριση της συλλογής ημερολογίου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις συλλογές ημερολογίων στο Aspose.Tasks για .NET. Δημιουργήστε, τροποποιήστε και χειριστείτε ημερολόγια με ευκολία.
weight: 11
url: /el/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση της συλλογής ημερολογίου στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο διαχείρισης συλλογών ημερολογίου στο Aspose.Tasks για .NET. Τα ημερολόγια διαδραματίζουν κρίσιμο ρόλο στη διαχείριση έργων, καθορίζοντας εργάσιμες ημέρες, αργίες και εξαιρέσεις. Το Aspose.Tasks παρέχει ισχυρή λειτουργικότητα για τον χειρισμό ημερολογίων στα έργα σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. Visual Studio: Εγκαταστήστε το Visual Studio ή οποιοδήποτε άλλο συμβατό IDE για ανάπτυξη .NET.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για εργασία με το Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Δημιουργία Νέου Ημερολογίου

###  Βήμα 1: Αρχικοποιήστε ένα νέο`Project` object.
```csharp
var project = new Project();
```

### Βήμα 2: Προσθέστε ημερολόγια στη συλλογή ημερολογίων του έργου.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Βήμα 3: Επαναλάβετε τα ημερολόγια και εμφανίστε τα ονόματά τους.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Αντικατάσταση ημερολογίου με νέο ημερολόγιο

### Βήμα 1: Φορτώστε ένα υπάρχον έργο.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Καταργήστε το υπάρχον ημερολόγιο (αν υπάρχει).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Βήμα 3: Προσθέστε ένα νέο ημερολόγιο.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Λήψη ημερολογίου με όνομα ή αναγνωριστικό

### Βήμα 1: Φορτώστε το έργο.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Ανάκτηση ημερολογίων με όνομα ή UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Βήμα 3: Εμφάνιση λεπτομερειών ημερολογίου.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Επανάληψη πάνω από ημερολόγια

### Βήμα 1: Φορτώστε το έργο.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Ανακτήστε το πλήθος των ημερολογίων.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Βήμα 3: Επαναλάβετε τη συλλογή ημερολογίου και τα εμφανιζόμενα ονόματα.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Δημιουργία τυπικού ημερολογίου

### Βήμα 1: Αρχικοποιήστε ένα νέο έργο.
```csharp
var project = new Project();
```

### Βήμα 2: Ορίστε ένα νέο ημερολόγιο και κάντε το τυπικό.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Βήμα 3: Αποθηκεύστε το έργο.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## συμπέρασμα

Η διαχείριση συλλογών ημερολογίων στο Aspose.Tasks για .NET είναι απαραίτητη για την αποτελεσματική διαχείριση έργου. Με τις παρεχόμενες λειτουργίες, μπορείτε να δημιουργήσετε, να τροποποιήσετε και να χειριστείτε αποτελεσματικά ημερολόγια σύμφωνα με τις απαιτήσεις του έργου σας.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να δημιουργήσω προσαρμοσμένες εργάσιμες ημέρες στο Aspose.Tasks;

A1: Ναι, μπορείτε να δημιουργήσετε προσαρμοσμένες εργάσιμες ημέρες προσθέτοντας εξαιρέσεις στα ημερολόγια.

### Ε2: Είναι δυνατή η εισαγωγή ημερολογίων από αρχεία Microsoft Project;

A2: Απολύτως, το Aspose.Tasks υποστηρίζει την εισαγωγή ημερολογίων από αρχεία Microsoft Project.

### Ε3: Πώς μπορώ να αφαιρέσω ένα συγκεκριμένο ημερολόγιο από ένα έργο;

 A3: Μπορείτε να αφαιρέσετε ένα ημερολόγιο παίρνοντας το από τη συλλογή και, στη συνέχεια, καλώντας το`Remove` μέθοδος.

### Ε4: Το Aspose.Tasks υποστηρίζει την εξαγωγή ημερολογίων σε διαφορετικές μορφές;

A4: Ναι, το Aspose.Tasks επιτρέπει την εξαγωγή ημερολογίων σε διάφορες μορφές όπως XML, MPP κ.λπ.

### Ε5: Μπορώ να προσαρμόσω τις ώρες εργασίας για συγκεκριμένες ημέρες σε ένα ημερολόγιο;

A5: Σίγουρα, μπορείτε να ορίσετε τις ώρες εργασίας για μεμονωμένες ημέρες χρησιμοποιώντας εξαιρέσεις στο ημερολόγιο.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
