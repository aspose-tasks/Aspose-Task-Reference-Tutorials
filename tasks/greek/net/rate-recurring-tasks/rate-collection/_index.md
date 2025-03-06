---
title: Master MS Project Rates with Aspose.Tasks
linktitle: Συλλογή τιμών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τιμές σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Βήμα προς βήμα μάθημα για αποτελεσματική διαχείριση πόρων.
weight: 11
url: /el/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master MS Project Rates with Aspose.Tasks

## Εισαγωγή
Καλώς ήρθατε στο σεμινάριο μας σχετικά με τη διαχείριση των χρεώσεων στο MS Project χρησιμοποιώντας το Aspose.Tasks για .NET! Σε αυτόν τον οδηγό, θα σας καθοδηγήσουμε στη διαδικασία εργασίας με τα ποσοστά στα αρχεία του MS Project χρησιμοποιώντας το Aspose.Tasks. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε με την ανάπτυξη .NET, αυτό το σεμινάριο θα σας παρέχει οδηγίες βήμα προς βήμα για να χειριστείτε αποτελεσματικά τις τιμές στα έργα σας.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστάθηκε το Visual Studio
Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας. Μπορείτε να το κατεβάσετε από τον ιστότοπο εάν δεν το έχετε κάνει ήδη.
### 2. Aspose.Tasks για .NET
 Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks για .NET από το[δικτυακός τόπος](https://releases.aspose.com/tasks/net/).
### 3. Βασικές γνώσεις C# και .NET
Εξοικειωθείτε με τη γλώσσα προγραμματισμού C# και τα βασικά του πλαισίου .NET για να κατανοήσετε καλύτερα τα παραδείγματα κώδικα που παρέχονται σε αυτό το σεμινάριο.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τις λειτουργίες Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:
## Βήμα 1: Φορτώστε ένα αρχείο MS Project
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Εδώ, δημιουργούμε ένα νέο`Project` αντικείμενο με τη φόρτωση ενός υπάρχοντος αρχείου MS Project.
## Βήμα 2: Προσθέστε έναν πόρο και ορίστε εργασία και τιμές
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Προσθέτουμε έναν νέο πόρο στο έργο, ορίζουμε τον τύπο του ως εργασία, ποσό εργασίας και τυπική τιμή.
## Βήμα 3: Προσθήκη ποσοστών στον πόρο
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Προσθέτουμε τιμές στον πόρο καθορίζοντας τις ημερομηνίες έναρξης και λήξης, την τυπική τιμή και τη μορφή τιμής.
## Βήμα 4: Εκτύπωση πληροφοριών τιμών
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Αυτό το βήμα εκτυπώνει πληροφορίες σχετικά με τις τιμές που σχετίζονται με τον πόρο.
## Βήμα 5: Ενημερώστε μια τιμή
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Ενημερώνουμε την ημερομηνία λήξης μιας συγκεκριμένης τιμής.
## Βήμα 6: Κατάργηση τιμών
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Αυτό το βήμα καταργεί όλες τις τιμές ενός συγκεκριμένου τύπου.
## Βήμα 7: Επαναλάβετε τα υπόλοιπα ποσοστά
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Τέλος, επαναλαμβάνουμε τα υπόλοιπα ποσοστά μετά την αφαίρεση.
## συμπέρασμα
Εν κατακλείδι, αυτό το σεμινάριο σάς παρείχε έναν ολοκληρωμένο οδηγό σχετικά με τη διαχείριση των ρυθμών σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας τις οδηγίες βήμα προς βήμα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά τις τιμές στα έργα σας, διασφαλίζοντας την ακριβή διαχείριση των πόρων.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλο λογισμικό διαχείρισης έργου;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει την ενοποίηση με διάφορα λογισμικά διαχείρισης έργων, συμπεριλαμβανομένων των MS Project, Primavera και άλλων.
### Ε: Είναι το Aspose.Tasks για .NET συμβατό με διαφορετικές εκδόσεις αρχείων MS Project;
Α: Απολύτως, το Aspose.Tasks για .NET υποστηρίζει την εργασία με αρχεία MS Project διαφορετικών εκδόσεων, διασφαλίζοντας ευελιξία και συμβατότητα.
### Ε: Το Aspose.Tasks για .NET προσφέρει τεκμηρίωση και υποστήριξη;
 Α: Ναι, μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσβαση σε φόρουμ υποστήριξης στο Aspose.Tasks[δικτυακός τόπος](https://reference.aspose.com/tasks/net/).
### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks για .NET πριν το αγοράσω;
Α: Ναι, μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή του Aspose.Tasks για το .NET για να αξιολογήσετε τις δυνατότητες και τη συμβατότητά του με τις απαιτήσεις σας.
### Ε: Πώς μπορώ να αγοράσω μια άδεια χρήσης για το Aspose.Tasks για .NET;
 Α: Μπορείτε να αγοράσετε μια άδεια χρήσης για το Aspose.Tasks για .NET από το[δικτυακός τόπος](https://purchase.aspose.com/temporary-license/)το οποίο παρέχει ευέλικτες επιλογές αδειοδότησης που ταιριάζουν στις ανάγκες σας.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
