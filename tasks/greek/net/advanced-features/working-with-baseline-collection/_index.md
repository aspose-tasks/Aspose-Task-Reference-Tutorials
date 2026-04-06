---
date: 2026-04-06
description: Μάθετε πώς να διαγράψετε όλα τα baseline και να διαχειριστείτε τις συλλογές
  baseline στο Aspose.Tasks για .NET με παραδείγματα κώδικα βήμα‑βήμα.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Διαγραφή όλων των Baselines με τη Συλλογή Baseline του Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Διαγραφή όλων των γραμμών βάσης με τη Συλλογή Baseline του Aspose.Tasks
url: /el/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαγραφή Όλων των Baselines με τη Συλλογή Baseline του Aspose.Tasks

## Εισαγωγή

Το Aspose.Tasks για .NET σάς επιτρέπει να χειρίζεστε αρχεία Microsoft Project απευθείας από τις .NET εφαρμογές σας. Μία από τις πιο ισχυρές δυνατότητες είναι η δυνατότητα **διαγραφής όλων των baselines** για έναν πόρο, η οποία είναι απαραίτητη όταν χρειάζεται να επαναφέρετε τα δεδομένα παρακολούθησης ενός έργου ή να ξεκινήσετε μια νέα περίοδο baseline. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — από τη φόρτωση ενός αρχείου έργου μέχρι την αφαίρεση κάθε baseline που είναι συνδεδεμένο με έναν συγκεκριμένο πόρο — χρησιμοποιώντας σαφείς, συνομιλιακές εξηγήσεις και έτοιμο κώδικα C#.

## Γρήγορες Απαντήσεις
- **Τι κάνει η “διαγραφή όλων των baselines”;** Αφαιρεί κάθε αποθηκευμένο αρχείο baseline για έναν επιλεγμένο πόρο, καθαρίζοντας τα ιστορικά δεδομένα κόστους και εργασίας.  
- **Γιατί θα το χρειαστώ;** Για να επαναφέρετε την παρακολούθηση μετά από μια σημαντική αλλαγή στο έργο ή όταν τα αρχικά baselines δεν είναι πλέον σχετικές.  
- **Ποια βιβλιοθήκη παρέχει αυτή τη δυνατότητα;** Aspose.Tasks για .NET.  
- **Χρειάζομαι άδεια;** Απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγική χρήση· διατίθεται δωρεάν δοκιμή.  
- **Είναι ο κώδικας συμβατός με .NET 6+;** Ναι, το API λειτουργεί με .NET Framework 4.5+, .NET Core 3.1+, και .NET 5/6.

## Τι είναι ένα Baseline και γιατί να διαγράψετε όλα τα Baselines;

Ένα baseline καταγράφει το αρχικό σχέδιο για κόστος, εργασία και χρονοδιάγραμμα σε ένα συγκεκριμένο χρονικό σημείο. Κατά τη διάρκεια ενός έργου μπορεί να δημιουργήσετε πολλά baselines (Baseline 1, Baseline 2, κ.λπ.) για να συγκρίνετε την πραγματική πρόοδο με διαφορετικά στιγμιότυπα προγραμματισμού. Ωστόσο, υπάρχουν σενάρια — όπως επαναπροσδιορισμός του έργου ή μια φρέσκια έναρξη — όπου η διατήρηση αυτών των ιστορικών baselines γίνεται μπερδεμένη. Η διαγραφή όλων των baselines σας δίνει ένα καθαρό ξεκίνημα, επιτρέποντάς σας να ορίσετε νέα baselines που αντανακλούν την τρέχουσα πραγματικότητα.

## Προαπαιτούμενα

Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. **Visual Studio** – οποιαδήποτε πρόσφατη έκδοση (Community, Professional ή Enterprise).  
2. **Aspose.Tasks για .NET** – κατεβάστε το από το [download link](https://releases.aspose.com/tasks/net/).  
3. **Βασικές γνώσεις C#** – θα πρέπει να είστε άνετοι με μεταβλητές, βρόχους και έξοδο κονσόλας.  
4. **Ένα αρχείο Microsoft Project** (`.mpp`) – ένα δείγμα αρχείου με όνομα *WorkWithBaselineCollection.mpp* θα χρησιμοποιηθεί στα παραδείγματα.

## Εισαγωγή Namespaces

Πρώτα, φέρτε τα απαραίτητα namespaces σε εμβέλεια ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις που θα χρησιμοποιήσουμε.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Βήμα 1: Φόρτωση του Αρχείου Project

Ξεκινάμε φορτώνοντας ένα υπάρχον αρχείο Project. Προσαρμόστε το `DataDir` ώστε να δείχνει στο φάκελο που περιέχει το αρχείο `.mpp` σας.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Βήμα 2: Λήψη του Στόχου Πόρου

Για επίδειξη, ανακτούμε τον πόρο με UID = 1. Σε πραγματικό σενάριο, θα εντοπίζατε τον πόρο με βάση το όνομα ή κάποιο άλλο αναγνωριστικό.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Βήμα 3: Εμφάνιση Υπάρχουσας Πληροφορίας Baseline

Πριν διαγράψετε οτιδήποτε, είναι χρήσιμο να δείτε ποια baselines είναι αυτή τη στιγμή συνδεδεμένα με τον πόρο. Αυτό σας δίνει σιγουριά ότι αφαιρείτε τα σωστά δεδομένα.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Βήμα 4: Επανάληψη σε Όλα τα Baselines

Εδώ επαναλαμβάνονται όλα τα baselines, εκτυπώνοντας βασικές μετρήσεις όπως κόστος, εργασία και κερδισμένη αξία (BCWP/BCWS). Αυτό το βήμα είναι προαιρετικό αλλά χρήσιμο για καταγραφή ή σκοπούς ελέγχου.

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

## Διαγραφή Όλων των Baselines

Τώρα εκτελούμε την κύρια ενέργεια: **διαγραφή όλων των baselines** για τον επιλεγμένο πόρο. Πρώτα αντιγράφουμε τη συλλογή σε μια λίστα για να αποφύγουμε την τροποποίηση της συλλογής κατά την επανάληψη, στη συνέχεια αφαιρούμε κάθε baseline ένα‑ένα.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Μετά την εκτέλεση αυτού του μπλοκ, το `resource.Baselines.Count` θα είναι `0`, επιβεβαιώνοντας ότι όλα τα αρχεία baseline έχουν διαγραφεί.

## Κοινά Προβλήματα και Συμβουλές

- **NullReferenceException** – Βεβαιωθείτε ότι το αρχείο project περιέχει πραγματικά τον πόρο που στοχεύετε· διαφορετικά το `GetByUid` θα επιστρέψει `null`.  
- **Licensing** – Χωρίς έγκυρη άδεια Aspose.Tasks θα δείτε υδατογράφημα στην έξοδο και περιορισμένη λειτουργικότητα.  
- **Performance** – Για πολύ μεγάλα έργα, σκεφτείτε την επανάληψη με `Parallel.ForEach` για να επιταχύνετε τη διαδικασία αφαίρεσης, αλλά θυμηθείτε ότι η υποκείμενη συλλογή δεν είναι ασφαλής για νήματα.

## Συχνές Ερωτήσεις

**Q: Μπορεί το Aspose.Tasks να διαχειριστεί μεγάλα αρχεία έργου;**  
A: Ναι, το Aspose.Tasks είναι βελτιστοποιημένο για απόδοση και μπορεί να επεξεργαστεί αρχεία `.mpp` πολλαπλών gigabyte αποδοτικά.

**Q: Είναι η βιβλιοθήκη συμβατή με όλες τις εκδόσεις του Microsoft Project;**  
A: Το Aspose.Tasks υποστηρίζει το Project 2000 έως το Project 2024, καλύπτοντας τόσο τις παλαιότερες μορφές `.mpp` όσο και τα νεότερα αρχεία βασισμένα σε XML.

**Q: Μπορώ να προσαρμόσω τα baselines πριν τα διαγράψω;**  
A: Απολύτως. Μπορείτε να διαβάσετε ή να τροποποιήσετε οποιαδήποτε ιδιότητα του baseline (κόστος, εργασία, ημερομηνίες) πριν αποφασίσετε να το αφαιρέσετε.

**Q: Λειτουργεί το Aspose.Tasks σε πλατφόρμες cloud;**  
A: Ναι, το API εκτελείται σε οποιοδήποτε περιβάλλον συμβατό με .NET, συμπεριλαμβανομένων του Azure App Service, AWS Lambda (μέσω .NET Core) και των Docker containers.

**Q: Πού μπορώ να ζητήσω βοήθεια από την κοινότητα;**  
A: Επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για να συνδεθείτε με άλλους προγραμματιστές και το προσωπικό της Aspose.

## Συμπέρασμα

Σε αυτόν τον οδηγό δείξαμε πώς να **διαγράψετε όλα τα baselines** από έναν πόρο χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας τον κώδικα βήμα‑βήμα, μπορείτε να επαναφέρετε τα δεδομένα baseline, να διατηρήσετε την παρακολούθηση του έργου σας καθαρή και να προετοιμάσετε το χρονοδιάγραμμα για έναν φρέσκο κύκλο προγραμματισμού. Μη διστάσετε να πειραματιστείτε με τη δημιουργία νέων baselines μετά τη διαγραφή για να δείτε πώς η βιβλιοθήκη ενημερώνει το αρχείο του έργου.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}