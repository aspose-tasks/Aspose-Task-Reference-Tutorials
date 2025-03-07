---
title: Χρήση αλγόριθμου δέντρου στο Aspose.Tasks
linktitle: Χρήση αλγόριθμου δέντρου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε αποτελεσματικά τις ιεραρχίες εργασιών στα έργα σας .NET χρησιμοποιώντας τον δενδροειδή αλγόριθμο Aspose.Tasks.
weight: 13
url: /el/net/advanced-concepts/tree-algorithm/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Χρήση αλγόριθμου δέντρου στο Aspose.Tasks

## Εισαγωγή

Το Aspose.Tasks για .NET παρέχει ισχυρές λειτουργίες για εργασία με εργασίες διαχείρισης έργου, πόρους και χρονοδιαγράμματα. Ένα τέτοιο χαρακτηριστικό είναι ο αλγόριθμος δέντρου, ο οποίος επιτρέπει στους χρήστες να χειρίζονται αποτελεσματικά τις ιεραρχίες εργασιών. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να χρησιμοποιήσετε τον αλγόριθμο δέντρου στο Aspose.Tasks για το .NET για τη συλλογή κοινών εργασιών και την ενημέρωση των τιμών εργασίας μέσα σε ένα έργο.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση της C#: Απαραίτητη η εξοικείωση με τη γλώσσα προγραμματισμού C# μαζί με τα παραδείγματα.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας C#, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να εργαστείτε με τις λειτουργίες Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:

## Βήμα 1: Φόρτωση αρχείου έργου

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Φορτώστε το αρχείο του έργου στη μνήμη χρησιμοποιώντας το`Project` τάξη.

## Βήμα 2: Ορισμός ιεραρχίας εργασιών

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Καθορίστε την ιεραρχία εργασιών προσθέτοντας γονικές και θυγατρικές εργασίες.

## Βήμα 3: Ορίστε τις ιδιότητες εργασίας

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Ορίστε ιδιότητες όπως ημερομηνία έναρξης, διάρκεια και ημερομηνία λήξης για εργασίες.

## Βήμα 4: Προσθήκη πόρων

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Προσθέστε πόρους στο έργο και αναθέστε τους σε εργασίες όπως απαιτείται.

## Βήμα 5: Εφαρμογή αλγόριθμου δέντρου

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Αρχικοποιήστε το`WorkAccumulator` τάξη και εφαρμόστε τον αλγόριθμο δέντρου για να συγκεντρώσετε κοινή εργασία.

## Βήμα 6: Ενημερώστε το Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Ενημερώστε τις τιμές εργασίας για εργασίες με βάση τις πληροφορίες που συγκεντρώθηκαν.

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε τον αλγόριθμο δέντρου στο Aspose.Tasks για .NET για να χειριζόμαστε αποτελεσματικά τις ιεραρχίες εργασιών. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να διαχειριστείτε αποτελεσματικά εργασίες και πόρους στα έργα σας.

## Συχνές ερωτήσεις

### Ε1: Τι είναι το Aspose.Tasks για .NET;

A1: Το Aspose.Tasks για .NET είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία Microsoft Project μέσω προγραμματισμού χρησιμοποιώντας C#.

### Ε2: Μπορώ να κατεβάσω μια δωρεάν δοκιμή του Aspose.Tasks για .NET;

 A2: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής του Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/).

### Ε3: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks για .NET;

 A3: Μπορείτε να βρείτε την τεκμηρίωση για το Aspose.Tasks για .NET[εδώ](https://reference.aspose.com/tasks/net/).

### Ε4: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για .NET;

 A4: Για υποστήριξη σχετικά με το Aspose.Tasks για .NET, μπορείτε να επισκεφτείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).

### Ε5: Υπάρχει διαθέσιμη προσωρινή άδεια για δοκιμαστικούς σκοπούς;

 A5: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια για σκοπούς δοκιμής από[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
