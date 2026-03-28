---
date: 2026-03-24
description: Μάθετε πώς να ορίσετε τη λειτουργία υπολογισμού στο Aspose.Tasks για
  .NET, καλύπτοντας τη λειτουργία αυτόματου, χειροκίνητου υπολογισμού και τη λειτουργία
  χωρίς υπολογισμό για τη διαχείριση των εξαρτήσεων των εργασιών.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Πώς να ορίσετε τη λειτουργία υπολογισμού στο Aspose.Tasks για .NET
url: /el/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε τη λειτουργία υπολογισμού στο Aspose.Tasks για .NET

## Εισαγωγή

Το Aspose.Tasks for .NET είναι ένα ισχυρό API που σας επιτρέπει να εργάζεστε προγραμματιστικά με αρχεία Microsoft Project. Μία από τις πιο σημαντικές ρυθμίσεις που θα συναντήσετε είναι η **calculation mode**, η οποία ελέγχει πώς ενημερώνονται οι ημερομηνίες εργασιών και τα χρονοδιαγράμματα του έργου. Σε αυτό το tutorial θα μάθετε **how to set calculation** mode, θα εξερευνήσετε **automatic calculation mode**, **manual calculation mode**, και **none calculation mode**, και θα δείτε πώς αυτές οι επιλογές επηρεάζουν **manage task dependencies**, **create project start date**, και **link tasks finish‑start** relationships.

## Γρήγορες Απαντήσεις
- **Τι είναι η calculation mode;** Καθορίζει εάν οι ημερομηνίες εργασιών επανυπολογίζονται αυτόματα, χειροκίνητα ή καθόλου.  
- **Γιατί να χρησιμοποιήσετε manual calculation mode;** Για να έχετε πλήρη έλεγχο του πότε θα ανανεώνεται το χρονοδιάγραμμα, χρήσιμο σε μαζικές ενημερώσεις.  
- **Ποια λειτουργία είναι η προεπιλογή;** Automatic calculation mode, η οποία ενημερώνει τις ημερομηνίες αμέσως μετά τις αλλαγές.  
- **Μπορώ να αλλάξω τη λειτουργία κατά την εκτέλεση;** Ναι—απλώς ορίστε την ιδιότητα `CalculationMode` στο αντικείμενο `Project`.  
- **Χρειάζομαι άδεια;** Απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγική χρήση.

## Τι είναι το “how to set calculation” στο Aspose.Tasks;
Η ρύθμιση της λειτουργίας υπολογισμού είναι τόσο απλή όσο η ανάθεση μιας τιμής enum στην ιδιότητα `Project.CalculationMode`. Το enum παρέχει τρεις επιλογές: `Automatic`, `Manual` και `None`. Η επιλογή της κατάλληλης λειτουργίας εξαρτάται από τη ροή εργασίας σας—εάν θέλετε άμεσες ενημερώσεις, επεξεργασία παρτίδας ή πλήρη έλεγχο.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Visual Studio** – οποιαδήποτε πρόσφατη έκδοση (2019, 2022 ή νεότερη).  
2. **Aspose.Tasks for .NET** – κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – πρέπει να είστε άνετοι με τη δημιουργία εφαρμογών κονσόλας και τη χρήση πακέτων NuGet.

## Εισαγωγή Namespaces

Πριν αρχίσουμε να δουλεύουμε με το Aspose.Tasks for .NET, ας εισάγουμε τα απαραίτητα namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Πώς να ορίσετε τη λειτουργία υπολογισμού

Παρακάτω θα βρείτε παραδείγματα βήμα‑βήμα για κάθε λειτουργία υπολογισμού. Τα μπλοκ κώδικα παραμένουν αμετάβλητα από το αρχικό tutorial· οι επεξηγήσεις έχουν επεκταθεί για μεγαλύτερη σαφήνεια.

### Εφαρμογή Automatic Calculation Mode

Η αυτόματη λειτουργία επανυπολογίζει τις ημερομηνίες αμέσως κάθε φορά που τροποποιείτε εργασίες ή συνδέσεις.

#### Βήμα 1: Δημιουργήστε ένα νέο αντικείμενο Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Βήμα 2: Ορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Βήμα 3: Συνδέστε εργασίες (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Βήμα 4: Επαληθεύστε τις επανυπολογισμένες ημερομηνίες

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Εφαρμογή Manual Calculation Mode

Η χειροκίνητη λειτουργία απενεργοποιεί τις αυτόματες ενημερώσεις, δίνοντάς σας την ευκαιρία να επεξεργαστείτε αλλαγές σε παρτίδες πριν εξαναγκάσετε έναν επανυπολογισμό.

#### Βήμα 1: Δημιουργήστε ένα νέο αντικείμενο Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Βήμα 2: Ορίστε την ημερομηνία έναρξης του έργου και προσθέστε εργασίες

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Βήμα 3: Επαληθεύστε τις ιδιότητες της εργασίας

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Βήμα 4: Συνδέστε εργασίες και επαληθεύστε τις ημερομηνίες (χωρίς αυτόματη επανυπολογισμό)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Εφαρμογή None Calculation Mode

Η λειτουργία None απενεργοποιεί όλους τους εσωτερικούς υπολογισμούς. Χρησιμοποιήστε την όταν χρειάζεται μόνο ανάγνωση ή εξαγωγή δεδομένων χωρίς αλλαγές στο χρονοδιάγραμμα.

#### Βήμα 1: Δημιουργήστε ένα νέο αντικείμενο Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Βήμα 2: Προσθέστε μια νέα εργασία

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Βήμα 3: Επαληθεύστε τις ιδιότητες της εργασίας (χωρίς αυτόματα IDs)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Οι ημερομηνίες δεν ενημερώνονται μετά τη σύνδεση εργασιών | Το Project βρίσκεται σε **Manual** ή **None** mode | Ορίστε `project.CalculationMode = CalculationMode.Automatic` ή καλέστε `project.Calculate()` χειροκίνητα |
| Τα IDs των εργασιών παραμένουν στο 0 | Η χρήση **None** mode αποτρέπει τη δημιουργία ID | Αλλάξτε σε **Automatic** ή **Manual** mode, μετά επανυπολογίστε |
| Η σύνδεση αποτυγχάνει με `ArgumentException` | Η ημερομηνία έναρξης του προγόνου είναι μεταγενέστερη από του απογόνου όταν χρησιμοποιείται **Manual** mode χωρίς επανυπολογισμό | Βεβαιωθείτε ότι οι ημερομηνίες έναρξης είναι σωστές ή επανυπολογίστε μετά την προσθήκη συνδέσεων |

## Συχνές Ερωτήσεις

**Q1: Μπορώ να αλλάξω τη λειτουργία υπολογισμού δυναμικά κατά την εκτέλεση;**  
A1: Ναι, μπορείτε να τροποποιήσετε την ιδιότητα `CalculationMode` σε οποιοδήποτε σημείο του κώδικά σας και, εάν χρειάζεστε άμεση ενημέρωση, να καλέσετε `project.Calculate()`.

**Q2: Υποστηρίζει το Aspose.Tasks άλλα μορφότυπα αρχείων διαχείρισης έργων εκτός από το Microsoft Project;**  
A2: Το Aspose.Tasks εστιάζει κυρίως στα μορφότυπα Microsoft Project, αλλά υποστηρίζει επίσης Primavera P6 XML, Primavera DB, και Asta Powerproject XML.

**Q3: Είναι το Aspose.Tasks κατάλληλο για μικρής κλίμακας και επιχειρησιακού επιπέδου έργα;**  
A3: Απολύτως. Το API κλιμακώνεται από απλές λίστες εργασιών μέχρι πολύπλοκα, πολυ‑φάσης χρονοδιαγράμματα επιχειρήσεων.

**Q4: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες και πλαίσια .NET;**  
A4: Ναι, μπορείτε να συνδυάσετε το Aspose.Tasks με ASP.NET, WPF, Xamarin ή οποιαδήποτε άλλη τεχνολογία .NET για να δημιουργήσετε πλούσιες λύσεις διαχείρισης έργων.

**Q5: Υπάρχει κοινότητα ή κανάλι υποστήριξης διαθέσιμο για χρήστες του Aspose.Tasks;**  
A5: Ναι, μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για υποστήριξη κοινότητας και συζητήσεις.

---

**Τελευταία ενημέρωση:** 2026-03-24  
**Δοκιμάστηκε με:** Aspose.Tasks 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}