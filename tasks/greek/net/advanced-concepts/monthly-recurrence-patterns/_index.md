---
title: Χειρισμός μοτίβων μηνιαίας επανάληψης στο Aspose.Tasks
linktitle: Χειρισμός μοτίβων μηνιαίας επανάληψης στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε τα μοτίβα μηνιαίας επανάληψης στο Aspose.Tasks για .NET με αυτό το βήμα προς βήμα εκμάθηση.
weight: 18
url: /el/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Χειρισμός μοτίβων μηνιαίας επανάληψης στο Aspose.Tasks

## Εισαγωγή

Το Aspose.Tasks for .NET είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία του Microsoft Project μέσω προγραμματισμού. Μία από τις βασικές λειτουργίες που προσφέρει είναι η ικανότητα να χειρίζονται επαναλαμβανόμενες εργασίες αποτελεσματικά. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στον τρόπο εργασίας με μοτίβα μηνιαίας επανάληψης χρησιμοποιώντας το Aspose.Tasks, βήμα προς βήμα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει τις ακόλουθες προϋποθέσεις:

## Εισαγωγή χώρων ονομάτων

Πρώτα, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στο έργο σας .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Τώρα, ας αναλύσουμε τη διαδικασία χειρισμού μηνιαίων μοτίβων επανάληψης σε πολλά βήματα:

## Βήμα 1: Αρχικοποιήστε το έργο

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Βήμα 2: Ορίστε τις επαναλαμβανόμενες παραμέτρους εργασιών

Καθορίστε τις παραμέτρους για την επαναλαμβανόμενη εργασία, συμπεριλαμβανομένου του ονόματος εργασίας, της διάρκειας και του μοτίβου επανάληψης:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Βήμα 3: Προσθήκη παραμέτρων στο έργο

```csharp
project.RootTask.Children.Add(parameters);
```

## Βήμα 4: Αποθηκεύστε το έργο

Αποθηκεύστε το τροποποιημένο έργο με την επαναλαμβανόμενη εργασία:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## συμπέρασμα

Ο χειρισμός μηνιαίων μοτίβων επανάληψης στο Aspose.Tasks για .NET είναι απλός και αποτελεσματικός. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε εύκολα να δημιουργήσετε επαναλαμβανόμενες εργασίες με συγκεκριμένα μηνιαία διαστήματα και εύρη επαναλήψεων.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις των αρχείων Microsoft Project;

A1: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων MPP, MPT, XML και MPX.

### Ε2: Μπορώ να προσαρμόσω περαιτέρω το μοτίβο επανάληψης;

A2: Ναι, το Aspose.Tasks παρέχει εκτενείς επιλογές για την προσαρμογή των μοτίβων επανάληψης, συμπεριλαμβανομένων ημερήσιων, εβδομαδιαίων, μηνιαίων και ετήσιων.

### Ε3: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;

 A3: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Tasks από τον ιστότοπο[εδώ](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;

 A4: Μπορείτε να ζητήσετε βοήθεια και να συμμετάσχετε σε συζητήσεις σχετικά με το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).

### Ε5: Πού μπορώ να αγοράσω άδεια χρήσης για το Aspose.Tasks;

 A5: Μπορείτε να αγοράσετε μια άδεια χρήσης για το Aspose.Tasks από τον ιστότοπο[εδώ](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
