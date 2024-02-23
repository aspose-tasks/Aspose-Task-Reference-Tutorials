---
title: Συλλογή Περιόδων Διαθεσιμότητας στο Aspose.Tasks
linktitle: Συλλογή Περιόδων Διαθεσιμότητας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τις περιόδους διαθεσιμότητας για πόρους στο Aspose.Tasks για .NET. Αυτός ο οδηγός βήμα προς βήμα σας καθοδηγεί στην προσθήκη, ενημέρωση και κατάργηση περιόδων διαθεσιμότητας, διασφαλίζοντας αποτελεσματικό σχεδιασμό πόρων έργου.
type: docs
weight: 18
url: /el/net/advanced-features/availability-period-collection/
---
## Εισαγωγή

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να εργαστούμε με τη συλλογή περιόδου διαθεσιμότητας ενός πόρου στο Aspose.Tasks για .NET. Η διαχείριση των περιόδων διαθεσιμότητας είναι ζωτικής σημασίας για τη διαχείριση έργου, επιτρέποντάς μας να προσδιορίσουμε πότε είναι διαθέσιμοι πόροι για εργασίες εντός ενός έργου.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική Κατανόηση: Εξοικείωση με το C# και το .NET Framework.

## Εισαγωγή χώρων ονομάτων

Αρχικά, πρέπει να εισαγάγουμε τους απαραίτητους χώρους ονομάτων στο έργο μας:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Ας αναλύσουμε τον κώδικα του παραδείγματος σε πολλά βήματα και ας κατανοήσουμε κάθε μέρος:

## Βήμα 1: Αρχικοποιήστε το έργο και τον πόρο

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Εδώ, φορτώνουμε ένα αρχείο έργου και λαμβάνουμε έναν συγκεκριμένο πόρο με το αναγνωριστικό του.

## Βήμα 2: Διαγραφή υφιστάμενων περιόδων διαθεσιμότητας

```csharp
resource.AvailabilityPeriods.Clear();
```

Εκκαθαρίζουμε τυχόν υπάρχουσες περιόδους διαθεσιμότητας που σχετίζονται με τον πόρο.

## Βήμα 3: Προσθήκη περιόδων διαθεσιμότητας

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Επαναλαμβάνουμε μια συλλογή περιόδων διαθεσιμότητας και τις προσθέτουμε στον πόρο.

## Βήμα 4: Εισαγάγετε μια νέα περίοδο διαθεσιμότητας

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Δημιουργούμε μια νέα περίοδο διαθεσιμότητας για το έτος 2013 και την εισάγουμε στη συλλογή.

## Βήμα 5: Εμφάνιση περιόδων διαθεσιμότητας

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Εκτυπώνουμε τον αριθμό και τις λεπτομέρειες κάθε περιόδου διαθεσιμότητας που σχετίζεται με τον πόρο.

## Βήμα 6: Αντιγράψτε τις περιόδους διαθεσιμότητας σε άλλο πόρο

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Αντιγράφουμε τις περιόδους διαθεσιμότητας από έναν πόρο σε άλλο.

## Βήμα 7: Ενημέρωση και κατάργηση περιόδων διαθεσιμότητας

```csharp
// Ενημερώστε τις διαθέσιμες μονάδες για μια συγκεκριμένη περίοδο
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Αφαιρέστε μια συγκεκριμένη περίοδο
otherResource.AvailabilityPeriods.Remove(period2013);
```

Ενημερώνουμε τις διαθέσιμες μονάδες για μια περίοδο και αφαιρούμε συγκεκριμένες περιόδους από τη συλλογή.

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δουλεύουμε με συλλογές περιόδου διαθεσιμότητας στο Aspose.Tasks για .NET. Η διαχείριση της διαθεσιμότητας πόρων είναι απαραίτητη για τον αποτελεσματικό σχεδιασμό και την εκτέλεση του έργου.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να προσθέσω προσαρμοσμένα πεδία στις περιόδους διαθεσιμότητας;

A1: Όχι, οι περίοδοι διαθεσιμότητας στο Aspose.Tasks για .NET δεν υποστηρίζουν προσαρμοσμένα πεδία.

### Ε2: Οι περίοδοι διαθεσιμότητας συνδέονται με συγκεκριμένες εργασίες;

A2: Όχι, οι περίοδοι διαθεσιμότητας σχετίζονται με πόρους και καθορίζουν πότε είναι διαθέσιμες για εργασίες γενικά.

### Ε3: Μπορώ να εισάγω περιόδους διαθεσιμότητας από εξωτερικές πηγές;

A3: Ναι, μπορείτε να εισαγάγετε περιόδους διαθεσιμότητας από διάφορες πηγές δεδομένων χρησιμοποιώντας το Aspose.Tasks για .NET API.

### Ε4: Πώς χειρίζομαι τις επικαλυπτόμενες περιόδους διαθεσιμότητας;

A4: Το Aspose.Tasks για .NET δεν παρέχει ενσωματωμένους μηχανισμούς για το χειρισμό επικαλυπτόμενων περιόδων. Ίσως χρειαστεί να εφαρμόσετε προσαρμοσμένη λογική για να διαχειριστείτε τέτοια σενάρια.

### Ε5: Υπάρχει όριο στον αριθμό των περιόδων διαθεσιμότητας που μπορεί να έχει ένας πόρος;

A5: Δεν υπάρχει προκαθορισμένο όριο στον αριθμό των περιόδων διαθεσιμότητας που μπορεί να έχει ένας πόρος, αλλά η απόδοση μπορεί να υποβαθμιστεί με μεγάλο αριθμό περιόδων.