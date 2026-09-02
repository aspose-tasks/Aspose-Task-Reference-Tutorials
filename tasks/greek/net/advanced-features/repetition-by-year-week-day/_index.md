---
date: 2026-04-03
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Tasks για να προσθέσετε επαναλαμβανόμενη
  εργασία σε έργο και να αποθηκεύσετε το έργο ως MPP. Αυτός ο οδηγός δείχνει τη λειτουργία
  «Επανάληψη ανά Έτος, Εβδομάδα, Ημέρα» βήμα‑βήμα.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Επανάληψη ανά Έτος, Εβδομάδα, Ημέρα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Πώς να χρησιμοποιήσετε το Aspose.Tasks – Επανάληψη ανά Έτος Εβδομάδα Ημέρα
url: /el/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Επανάληψη ανά Έτος Εβδομάδα Ημέρα στο Aspose.Tasks

## Εισαγωγή

Όταν χρειάζεστε **how to use Aspose.Tasks** για τη διαχείριση σύνθετων επαναλαμβανόμενων χρονοδιαγραμμάτων, η βιβλιοθήκη σας παρέχει λεπτομερή έλεγχο των ετήσιων προτύπων. Σε αυτό το tutorial θα περάσουμε από τη δημιουργία μιας εργασίας που επαναλαμβάνεται σε μια συγκεκριμένη ημέρα της εβδομάδας ενός συγκεκριμένου μήνα, καλύπτοντας πολλαπλά έτη. Στο τέλος θα μπορείτε να **add recurring task project** καταχωρήσεις και **save project as MPP** με λίγες γραμμές C#.

## Γρήγορες Απαντήσεις
- **What does “Repetition by Year Week Day” mean?** Επαναλαμβάνει μια εργασία σε μια επιλεγμένη ημέρα της εβδομάδας (π.χ., την πρώτη Κυριακή) ενός συγκεκριμένου μήνα κάθε χρόνο.  
- **Which .NET versions are supported?** Όλες οι σύγχρονες εκδόσεις του .NET Framework και .NET Core/5/6.  
- **Do I need a license to run the code?** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Can I change the recurrence range?** Ναι – μπορείτε να ορίσετε ημερομηνία έναρξης, λήξης ή έναν σταθερό αριθμό επαναλήψεων.  
- **Is the output an MPP file?** Απόλυτα – το έργο αποθηκεύεται ως αρχείο MPP έτοιμο για το Microsoft Project.

## Τι είναι η λειτουργία “Repetition by Year Week Day”;
Η λειτουργία σας επιτρέπει να ορίσετε μια ετήσια επανάληψη που στοχεύει μια συγκεκριμένη **day of the week** (π.χ., Sunday) και μια **position** μέσα στον μήνα (πρώτη, δεύτερη, τελευταία κ.λπ.). Αυτό είναι ιδανικό για εργασίες όπως τριμηνιαίες αξιολογήσεις, ετήσιους ελέγχους ή οποιοδήποτε γεγονός που ακολουθεί έναν ρυθμό βασισμένο στο ημερολόγιο.

## Γιατί να χρησιμοποιήσετε Aspose.Tasks για επαναλαμβανόμενες εργασίες;
- **Precision** – Πλήρης έλεγχος πάνω στους μήνες, τις ημέρες της εβδομάδας και τις διατεταγμένες θέσεις.  
- **Compatibility** – Δημιουργεί εγγενή αρχεία MPP που ανοίγουν άψογα στο Microsoft Project.  
- **No COM interop** – Καθαρό .NET API, χωρίς ανάγκη εγκατάστασης Office.  
- **Scalability** – Λειτουργεί για μικρά έργα και χρονοδιαγράμματα επιπέδου επιχείρησης.

## Προαπαιτούμενα

Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. **Basic .NET knowledge** – Εξοικείωση με C# και αντικειμενοστραφείς έννοιες.  
2. **Aspose.Tasks for .NET** – Κατεβάστε το από το [download link](https://releases.aspose.com/tasks/net/) και προσθέστε το DLL στο έργο σας.  
3. **Access to the official docs** – Η [documentation](https://reference.aspose.com/tasks/net/) περιέχει εκτενείς λεπτομέρειες για όλες τις κλάσεις.  
4. **A development IDE** – Visual Studio, Rider ή οποιονδήποτε συμβατό .NET επεξεργαστή.

Τώρα που είστε έτοιμοι, ας δούμε την υλοποίηση.

## Πώς να χρησιμοποιήσετε Aspose.Tasks για επαναλαμβανόμενες εργασίες

### Εισαγωγή Απαραίτητων Ονομάτων Χώρου

Πρώτα, φέρετε τα απαιτούμενα ονόματα χώρου στο πεδίο ορατότητας ώστε να μπορείτε να εργάζεστε με έργα, εργασίες και επιλογές αποθήκευσης.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Βήμα 1: Αρχικοποίηση Έργου και Παραμέτρων Εργασίας

Δημιουργήστε ένα νέο αντικείμενο `Project`, στη συνέχεια ορίστε ένα αντικείμενο `RecurringTaskParameters` που περιγράφει το πρότυπο επανάληψης.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Προσαρμόστε το `Month`, `WeekDay` και `Position` ώστε να ταιριάζουν με το πραγματικό σας πρόγραμμα.

### Βήμα 2: Προσθήκη Παραμέτρων στο Έργο

Εισάγετε τον ορισμό της επαναλαμβανόμενης εργασίας στη ρίζα του έργου.

```csharp
project.RootTask.Children.Add(parameters);
```

### Βήμα 3: Αποθήκευση Έργου ως MPP

Τέλος, αποθηκεύστε το έργο σε αρχείο MPP ώστε να μπορεί να ανοιχθεί στο Microsoft Project ή σε οποιονδήποτε συμβατό προβολέα.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Αυτό δείχνει **save project as mpp** σε μία μόνο γραμμή κώδικα.

## Συχνά Προβλήματα και Λύσεις

| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|---------|--------------|-----|
| Δεν εμφανίζονται εργασίες μετά το άνοιγμα του αρχείου MPP | Οι ημερομηνίες εύρους επανάληψης είναι εκτός του ημερολογίου του έργου | Επαληθεύστε ότι οι ημερομηνίες `Start` και `Finish` εμπίπτουν στον χρόνο εργασίας του έργου |
| Εξαίρεση `ArgumentNullException` στο `Add` | `parameters` είναι null ή δεν έχει αρχικοποιηθεί πλήρως | Βεβαιωθείτε ότι όλες οι απαιτούμενες ιδιότητες (TaskName, Duration, RecurrencePattern) έχουν οριστεί |
| Επιλέχθηκε λάθος ημέρα της εβδομάδας | Ασυμφωνία τιμής enum `WeekDay` | Χρησιμοποιήστε `DayOfWeek.Monday` … `DayOfWeek.Sunday` ανάλογα με τις ανάγκες |

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσαρμόσω το πρότυπο επανάληψης πέρα από το παραδείγμα που παρέχεται;**  
A: Ναι, το Aspose.Tasks σας επιτρέπει να συνδυάσετε `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, ή ακόμη και προσαρμοσμένα αντικείμενα `RecurrenceRange` για να ταιριάξουν σε οποιοδήποτε χρονοδιάγραμμα.

**Q: Είναι το Aspose.Tasks για .NET συμβατό με άλλο λογισμικό διαχείρισης έργων;**  
A: Απόλυτα – η βιβλιοθήκη διαβάζει και γράφει μορφές MPP, XML και Primavera, επιτρέποντας ομαλή ανταλλαγή δεδομένων.

**Q: Πώς μπορώ να διαχειριστώ εξαιρέσεις ή τροποποιήσεις σε επαναλαμβανόμενες εργασίες;**  
A: Χρησιμοποιήστε την κλάση `ExceptionTask` για να δημιουργήσετε παρακάμψεις για συγκεκριμένες εμφανίσεις, ή επεξεργαστείτε το `RecurringTaskParameters` και αποθηκεύστε ξανά το έργο.

**Q: Υποστηρίζει το Aspose.Tasks λύσεις βασισμένες στο cloud;**  
A: Ναι, μπορείτε να εκτελέσετε το API σε Azure Functions, AWS Lambda ή οποιαδήποτε υπηρεσία cloud συμβατή με .NET.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Tasks για .NET από το [website](https://releases.aspose.com/), επιτρέποντάς σας να εξερευνήσετε τις δυνατότητές του πριν λάβετε απόφαση αγοράς.

**Q: Πώς μπορώ να προσθέσω μια επαναλαμβανόμενη εργασία σε υπάρχον έργο χωρίς να αντικαταστήσω άλλα δεδομένα;**  
A: Φορτώστε το υπάρχον έργο με `new Project("Existing.mpp")`, προσθέστε το `RecurringTaskParameters` στο `RootTask.Children`, και στη συνέχεια `Save` το αρχείο.

## Συμπέρασμα

Με την εξοικείωση με **how to use Aspose.Tasks** για το σενάριο **Repetition by Year Week Day**, αποκτάτε τη δυνατότητα να **add recurring task project** καταχωρήσεις που ευθυγραμμίζονται τέλεια με τα πραγματικά ημερολόγια και **save project as MPP** για απρόσκοπτη συνεργασία. Ενσωματώστε αυτά τα αποσπάσματα στις δικές σας λύσεις για να βελτιώσετε την ακρίβεια του χρονοπρογραμματισμού και να μειώσετε την χειροκίνητη εργασία.

---

**Τελευταία Ενημέρωση:** 2026-04-03  
**Δοκιμή Με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}