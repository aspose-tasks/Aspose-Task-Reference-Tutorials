---
title: Τύπος υπολογισμού στο Aspose.Tasks
linktitle: Τύπος υπολογισμού στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να προσαρμόζετε τους υπολογισμούς αξίας σε έργα .NET με τον τύπο υπολογισμού στη βιβλιοθήκη Aspose.Tasks.
weight: 30
url: /el/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Τύπος υπολογισμού στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τη δυνατότητα Τύπος υπολογισμού στο Aspose.Tasks για .NET. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές .NET να εργάζονται με αρχεία Microsoft Project χωρίς να χρειάζεται να είναι εγκατεστημένο το Microsoft Project στα συστήματά τους. Ο τύπος υπολογισμού μας επιτρέπει να ορίσουμε πώς υπολογίζονται οι τιμές για εργασίες και εργασίες σύνοψης σε ένα έργο.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Βασικές γνώσεις C# και .NET Framework.
2. Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
3.  Εγκαταστάθηκε το Aspose.Tasks για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
4.  Πρόσβαση στην τεκμηρίωση Aspose.Tasks για .NET για αναφορά, διαθέσιμη[εδώ](https://reference.aspose.com/tasks/net/).

## Εισαγωγή χώρων ονομάτων

Πριν βουτήξετε στο παράδειγμα, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων:

```csharp
using Aspose.Tasks;
using System;


```

## Βήμα 1: Δημιουργήστε ένα νέο έργο

Αρχικά, ας δημιουργήσουμε ένα νέο αντικείμενο έργου:

```csharp
var project = new Project();
```

## Βήμα 2: Προσθέστε μια εργασία

Τώρα, ας προσθέσουμε μια εργασία στο έργο μας:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Βήμα 3: Καθορίστε τον τύπο υπολογισμού για ένα εκτεταμένο χαρακτηριστικό

Θα δημιουργήσουμε έναν εκτεταμένο ορισμό χαρακτηριστικών με τον Τύπο Υπολογισμού να έχει οριστεί σε Τύπο:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Βήμα 4: Καθορίστε τον τύπο υπολογισμού για τις γραμμές σύνοψης

Στη συνέχεια, θα δημιουργήσουμε έναν άλλο εκτεταμένο ορισμό χαρακτηριστικών όπου οι τιμές για συνοπτικές εργασίες υπολογίζονται χρησιμοποιώντας τον τύπο συνάθροισης μέσου όρου:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εργασίας με τον τύπο υπολογισμού στο Aspose.Tasks για .NET. Ορίζοντας τύπους υπολογισμού για εκτεταμένα χαρακτηριστικά, μπορούμε να προσαρμόσουμε τον τρόπο υπολογισμού των τιμών για εργασίες και συνοπτικές εργασίες σε ένα έργο, παρέχοντας μεγαλύτερη ευελιξία και έλεγχο.

## Συχνές ερωτήσεις

### Ε1: Τι είναι ο τύπος υπολογισμού στο Aspose.Tasks;

A1: Ο τύπος υπολογισμού στο Aspose.Tasks καθορίζει τον τρόπο με τον οποίο υπολογίζονται οι τιμές για εργασίες και εργασίες σύνοψης σε ένα έργο, προσφέροντας επιλογές όπως Τύπος και Συνάθροιση.

### Ε2: Πώς ορίζω τον Τύπο υπολογισμού για ένα εκτεταμένο χαρακτηριστικό;

A2: Μπορείτε να ορίσετε τον τύπο υπολογισμού για ένα εκτεταμένο χαρακτηριστικό ορίζοντας ανάλογα την ιδιότητά του CalculationType.

### Ε3: Μπορώ να προσαρμόσω τον Τύπο υπολογισμού για σειρές σύνοψης σε ένα έργο;

A3: Ναι, το Aspose.Tasks σάς επιτρέπει να καθορίσετε τον Τύπο υπολογισμού για σειρές σύνοψης, δίνοντάς σας τη δυνατότητα να προσαρμόσετε τους υπολογισμούς τιμών με βάση τις απαιτήσεις σας.

### Ε4: Υπάρχουν διαφορετικοί τύποι συνάθροισης διαθέσιμοι για υπολογισμούς συνοπτικών εργασιών;

A4: Ναι, το Aspose.Tasks παρέχει διάφορους τύπους συνάθροισης, όπως Μέσος όρος, Άθροισμα και Μέτρηση για τον υπολογισμό των τιμών των εργασιών σύνοψης.

### Ε5: Πού μπορώ να βρω περισσότερους πόρους στο Aspose.Tasks για .NET;

 A5: Μπορείτε να εξερευνήσετε την τεκμηρίωση και τα φόρουμ υποστήριξης κοινότητας που είναι διαθέσιμα στο[Aspose.Tasks για .NET](https://reference.aspose.com/tasks/net/) για ολοκληρωμένη καθοδήγηση και βοήθεια.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
