---
date: 2026-04-13
description: Μάθετε πώς να ορίζετε τις ώρες εργασίας και να διαχειρίζεστε συλλογές
  ημερολογίων στο Aspose.Tasks για .NET. Εισάγετε ημερολόγια του Microsoft Project,
  αφαιρέστε το ημερολόγιο του έργου και ανακτήστε το ημερολόγιο με το όνομα εύκολα.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Διαχείριση Συλλογής Ημερολογίων στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ορισμός ωρών εργασίας στη συλλογή ημερολογίων Aspose.Tasks
url: /el/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός ωρών εργασίας στη συλλογή ημερολογίων Aspose.Tasks

Σε αυτό το σεμινάριο, θα μάθετε πώς να **ορίσετε ώρες εργασίας** και να διαχειριστείτε τις συλλογές ημερολογίων χρησιμοποιώντας το Aspose.Tasks για .NET. Τα ημερολόγια ορίζουν τις εργάσιμες ημέρες, τις αργίες και τις εξαιρέσεις, έτσι η εξοικείωση με αυτά σας επιτρέπει να ελέγχετε με ακρίβεια τα χρονοδιαγράμματα των έργων. Θα σας δείξουμε επίσης πώς να εισάγετε ημερολόγια από το Microsoft Project, να αφαιρέσετε ένα ημερολόγιο από ένα έργο και να λάβετε ένα ημερολόγιο με βάση το όνομα.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για τα ημερολόγια;** `Project.Calendars` collection.
- **Πώς ορίζω ώρες εργασίας;** Δημιουργήστε ή τροποποιήστε ένα αντικείμενο `Calendar` και ορίστε το `WorkingTime` του.
- **Μπορώ να εισάγω ημερολόγια από το Microsoft Project;** Ναι – φορτώστε ένα αρχείο MPP και αποκτήστε πρόσβαση στα ημερολόγια του.
- **Πώς να αφαιρέσετε ένα ημερολόγιο από ένα έργο;** Χρησιμοποιήστε `Project.Calendars.Remove(calendar)`.
- **Πώς να ανακτήσετε ένα ημερολόγιο με βάση το όνομα;** Καλέστε `Project.Calendars.GetByName("YourCalendar")`.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. Visual Studio: Εγκαταστήστε το Visual Studio ή οποιοδήποτε άλλο συμβατό IDE για ανάπτυξη .NET.  
2. Aspose.Tasks for .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks for .NET από [here](https://releases.aspose.com/tasks/net/).  
3. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή ονομάτων χώρων (Namespaces)

Αρχικά, ας εισάγουμε τους απαραίτητους χώρους ονομάτων για να εργαστούμε με το Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Δημιουργία νέου ημερολογίου

### Βήμα 1: Αρχικοποίηση ενός νέου αντικειμένου `Project`.

```csharp
var project = new Project();
```

### Βήμα 2: Προσθήκη ημερολογίων στη συλλογή ημερολογίων του έργου.

```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Βήμα 3: Επανάληψη μέσω των ημερολογίων και εμφάνιση των ονομάτων τους.

```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Πώς να ορίσετε ώρες εργασίας για ένα ημερολόγιο;

Για να **ορίσετε ώρες εργασίας**, τροποποιείτε τη συλλογή `WorkingTime` ενός `Calendar`.  
Για παράδειγμα, μπορείτε να ορίσετε μια τυπική εργάσιμη ημέρα 9 π.μ.–5 μ.μ. ή να προσθέσετε προσαρμοσμένες εξαιρέσεις.  
Ο κώδικας για αυτό είναι ίδιος με τα παραδείγματα που εμφανίζονται αργότερα όταν δημιουργούμε ένα τυπικό ημερολόγιο.

## Αντικατάσταση ενός ημερολογίου με νέο ημερολόγιο

### Βήμα 1: Φόρτωση υπάρχοντος έργου.

```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Αφαίρεση του υπάρχοντος ημερολογίου (αν υπάρχει).  
Αυτό δείχνει το σενάριο **αφαίρεσης ημερολογίου από το έργο**.

```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Βήμα 3: Προσθήκη νέου ημερολογίου.

```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Λήψη ημερολογίου με βάση το όνομα ή το ID

### Βήμα 1: Φόρτωση του έργου.

```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Ανάκτηση ημερολογίων με βάση το όνομα ή το UID.  
Αυτό απεικονίζει τη λειτουργία **λήψης ημερολογίου με όνομα**.

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

## Επανάληψη μέσω των ημερολογίων

### Βήμα 1: Φόρτωση του έργου.

```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Βήμα 2: Ανάκτηση του αριθμού των ημερολογίων.

```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Βήμα 3: Επανάληψη στη συλλογή ημερολογίων και εμφάνιση των ονομάτων.

```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Δημιουργία τυπικού ημερολογίου

### Βήμα 1: Αρχικοποίηση νέου έργου.

```csharp
var project = new Project();
```

### Βήμα 2: Ορισμός νέου ημερολογίου και καθιστώντας το τυπικό.

```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Βήμα 3: Αποθήκευση του έργου.

```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Συχνά Προβλήματα και Λύσεις

- **Το ημερολόγιο δεν βρέθηκε κατά τη χρήση του `GetByName`** – Βεβαιωθείτε ότι το ακριβές όνομα ταιριάζει με την περίπτωση που χρησιμοποιήθηκε όταν προστέθηκε το ημερολόγιο.  
- **Οι ώρες εργασίας δεν εφαρμόζονται** – Μετά τον ορισμό του `WorkingTime`, θυμηθείτε να αποθηκεύσετε το έργο· διαφορετικά οι αλλαγές παραμένουν μόνο στη μνήμη.  
- **Η εισαγωγή ημερολογίων από αρχείο MPP αποτυγχάνει** – Επαληθεύστε ότι το αρχείο προέλευσης είναι έγκυρο αρχείο Microsoft Project και ότι έχετε δικαιώματα ανάγνωσης.

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να δημιουργήσω προσαρμοσμένες εργάσιμες ημέρες στο Aspose.Tasks;

Α1: Ναι, μπορείτε να δημιουργήσετε προσαρμοσμένες εργάσιμες ημέρες προσθέτοντας εξαιρέσεις στα ημερολόγια.

### Ε2: Είναι δυνατόν να εισάγετε ημερολόγια από αρχεία Microsoft Project;

Α2: Απόλυτα, το Aspose.Tasks υποστηρίζει την εισαγωγή ημερολογίων από αρχεία Microsoft Project.

### Ε3: Πώς μπορώ να αφαιρέσω ένα συγκεκριμένο ημερολόγιο από ένα έργο;

Α3: Μπορείτε να αφαιρέσετε ένα ημερολόγιο λαμβάνοντάς το από τη συλλογή και στη συνέχεια καλώντας τη μέθοδο `Remove`.

### Ε4: Το Aspose.Tasks υποστηρίζει την εξαγωγή ημερολογίων σε διαφορετικές μορφές;

Α4: Ναι, το Aspose.Tasks επιτρέπει την εξαγωγή ημερολογίων σε διάφορες μορφές όπως XML, MPP κ.λπ.

### Ε5: Μπορώ να προσαρμόσω τις ώρες εργασίας για συγκεκριμένες ημέρες σε ένα ημερολόγιο;

Α5: Φυσικά, μπορείτε να ορίσετε ώρες εργασίας για μεμονωμένες ημέρες χρησιμοποιώντας εξαιρέσεις στο ημερολόγιο.

## Συχνές Ερωτήσεις

**Ε: Ποιος είναι ο καλύτερος τρόπος για να ορίσετε ημερολόγιο βάρδιας 24 ωρών;**  
Α: Δημιουργήστε ένα νέο ημερολόγιο, καθαρίστε τις υπάρχουσες καταχωρήσεις `WorkingTime` και προσθέστε ένα ενιαίο εύρος `WorkingTime` από 00:00 έως 24:00 για κάθε εργάσιμη ημέρα.

**Ε: Μπορώ να αντιγράψω ένα ημερολόγιο από ένα έργο σε άλλο;**  
Α: Ναι—εξάγετε το ημερολόγιο σε XML χρησιμοποιώντας το `project.Save` και στη συνέχεια εισάγετε το σε άλλο έργο με `new Project(xmlPath)`.

**Ε: Πώς μπορώ προγραμματιστικά να εισάγω ημερολόγια από το Microsoft Project;**  
Α: Φορτώστε το αρχείο MPP με `new Project("source.mpp")`; τα ημερολόγια γίνονται διαθέσιμα μέσω του `project.Calendars`.

**Ε: Υπάρχει όριο στον αριθμό των ημερολογίων σε ένα έργο;**  
Α: Στην πράξη όχι· η συλλογή μπορεί να περιέχει όσα ημερολόγια επιτρέπει η μνήμη, αλλά διατηρήστε τη λίστα διαχειρίσιμη για απόδοση.

**Ε: Οι αλλαγές σε ένα ημερολόγιο ενημερώνουν αυτόματα τις εργασίες που το χρησιμοποιούν;**  
Α: Ναι—οι εργασίες που συνδέονται με ένα ημερολόγιο αντικατοπτρίζουν τις ενημερωμένες ώρες εργασίας μετά την αποθήκευση του έργου.

---

**Τελευταία ενημέρωση:** 2026-04-13  
**Δοκιμή με:** Aspose.Tasks 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}