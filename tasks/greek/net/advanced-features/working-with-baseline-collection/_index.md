---
title: Εργασία με Baseline Collection στο Aspose.Tasks
linktitle: Εργασία με Baseline Collection στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις γραμμές βάσης στο Aspose.Tasks για .NET. Ακολουθήστε το περιεκτικό μας σεμινάριο για καθοδήγηση βήμα προς βήμα.
type: docs
weight: 20
url: /el/net/advanced-features/working-with-baseline-collection/
---
## Εισαγωγή

Το Aspose.Tasks για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project στις εφαρμογές τους .NET απρόσκοπτα. Μεταξύ των πολλών χαρακτηριστικών του, παρέχει ισχυρή υποστήριξη για τη διαχείριση των βασικών γραμμών εντός έργων. Οι γραμμές βάσης είναι απαραίτητες για τη διαχείριση του έργου, καθώς σας επιτρέπουν να συγκρίνετε το αρχικό σχέδιο έργου με την τρέχουσα κατάσταση, επιτρέποντας καλύτερη παρακολούθηση και ανάλυση της προόδου του έργου.

## Προαπαιτούμενα

Πριν ξεκινήσουμε την εργασία με συλλογές βασικής γραμμής στο Aspose.Tasks, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Visual Studio: Εγκαταστήστε το Visual Studio IDE στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks για .NET από τη[σύνδεσμος λήψης](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση της C#: Εξοικειωθείτε με τη γλώσσα προγραμματισμού C#.
4. Αρχείο Microsoft Project: Έχετε ένα αρχείο Microsoft Project (.mpp) έτοιμο για δοκιμαστικούς σκοπούς.

## Εισαγωγή χώρων ονομάτων

Για να ξεκινήσετε να εργάζεστε με συλλογές γραμμής βάσης στο Aspose.Tasks, πρέπει να εισαγάγετε τους ακόλουθους χώρους ονομάτων:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:

## Βήμα 1: Φόρτωση αρχείου έργου

Αρχικά, φορτώστε το αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Βήμα 2: Λήψη πόρων

Στη συνέχεια, ανακτήστε τον επιθυμητό πόρο από το έργο:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Βήμα 3: Εμφάνιση πληροφοριών γραμμής βάσης

Τώρα, εμφανίστε πληροφορίες σχετικά με τις γραμμές βάσης που σχετίζονται με τον πόρο:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Βήμα 4: Επανάληψη μέσω γραμμών βάσης

Επαναλάβετε σε κάθε γραμμή βάσης που σχετίζεται με τον πόρο και εκτυπώστε τις σχετικές πληροφορίες:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Βήμα 5: Καταργήστε τις γραμμές βάσης

Διαγράψτε όλες τις γραμμές βάσης που σχετίζονται με τον πόρο:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εργασίας με συλλογές βασικής γραμμής στο Aspose.Tasks για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να διαχειριστείτε εύκολα τις γραμμές βάσης στις εφαρμογές σας .NET, επιτρέποντας την αποτελεσματική παρακολούθηση και ανάλυση έργων.

## Συχνές ερωτήσεις

### Ε1: Μπορεί το Aspose.Tasks να χειριστεί μεγάλα αρχεία έργου;

A1: Ναι, το Aspose.Tasks είναι βελτιστοποιημένο για να χειρίζεται αποτελεσματικά μεγάλα αρχεία έργων, διασφαλίζοντας ομαλή απόδοση.

### Ε2: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;

A2: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις του Microsoft Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.

### Ε3: Μπορώ να προσαρμόσω τις γραμμές βάσης στο Aspose.Tasks;

A3: Ναι, μπορείτε να προσαρμόσετε τις γραμμές βάσης σύμφωνα με τις απαιτήσεις του έργου σας χρησιμοποιώντας το Aspose.Tasks για .NET.

### Ε4: Το Aspose.Tasks προσφέρει υποστήριξη για πλατφόρμες cloud;

A4: Ναι, το Aspose.Tasks παρέχει υποστήριξη για ενοποίηση με δημοφιλείς πλατφόρμες cloud, προσφέροντας ευελιξία στην ανάπτυξη.

### Ε5: Υπάρχει ένα φόρουμ κοινότητας για τους χρήστες του Aspose.Tasks να αναζητούν βοήθεια και να μοιράζονται γνώσεις;

 A5: Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) να συνεργαστείτε με την κοινότητα και να λάβετε βοήθεια από ειδικούς.