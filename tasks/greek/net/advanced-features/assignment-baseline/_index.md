---
date: 2026-03-19
description: Μάθετε πώς να ορίζετε τη βάση του έργου και να διαχειρίζεστε αποτελεσματικά
  τις βάσεις ανάθεσης με το Aspose.Tasks για .NET, εξασφαλίζοντας ακριβή παρακολούθηση
  της προόδου του έργου.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ορισμός Βάσης Έργου – Διαχείριση Βάσης Ανάθεσης στο Aspose.Tasks
url: /el/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Βάσης Έργου – Διαχείριση Βάσης Ανάθεσης στο Aspose.Tasks

## Εισαγωγή

Κατά την εργασία σε έργα διαχείρισης, ο **ορισμός μιας βάσης έργου** είναι απαραίτητος για τη μέτρηση της πραγματικής προόδου σε σχέση με το αρχικό σχέδιο. Το Aspose.Tasks για .NET όχι μόνο σας επιτρέπει να **ορίσετε μια βάση έργου**, αλλά επίσης παρέχει πλήρη έλεγχο πάνω στις βάσεις ανάθεσης, επιτρέποντας ακριβή παρακολούθηση της απόδοσης. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — φόρτωση ενός έργου, ορισμός βάσης, ανάγνωση δεδομένων βάσης ανάθεσης και σύγκριση βάσεων — ώστε να μπορείτε να παρακολουθείτε τα έργα σας με σιγουριά.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “ορισμός βάσης έργου”;** Καταγράφει τα αρχικά δεδομένα χρονοδιαγράμματος και κόστους για μετέπειτα σύγκριση με την πραγματική απόδοση.  
- **Ποια μέθοδος API ορίζει μια βάση;** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Απαιτούνται ξεχωριστές κλήσεις για τις βάσεις ανάθεσης;** Όχι, αποθηκεύονται αυτόματα όταν ορίζετε μια βάση έργου.  
- **Ποιες μορφές υποστηρίζονται;** MPP, XML, MPX και άλλες μέσω Aspose.Tasks.  
- **Απαιτείται άδεια για παραγωγική χρήση;** Ναι, απαιτείται εμπορική άδεια για χρήση εκτός δοκιμαστικής περιόδου.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού C#.  
- Visual Studio (οποιαδήποτε πρόσφατη έκδοση).  
- Βιβλιοθήκη Aspose.Tasks για .NET προστιθέμενη στο έργο σας. Μπορείτε να τη κατεβάσετε από [εδώ](https://releases.aspose.com/tasks/net/).  
- Πρόσβαση σε αρχείο έργου σε μορφή MPP (π.χ., `AssignmentBaseline2007.mpp`).

## Εισαγωγή Namespaces

Προσθέστε τα απαιτούμενα namespaces στην κορυφή του αρχείου C# ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις του Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Βήμα 1: Φόρτωση Έργου και Ορισμός Βάσης Έργου

Πρώτα, φορτώστε το υπάρχον αρχείο MPP και στη συνέχεια καλέστε `SetBaseline` για να **ορίσετε τη βάση έργου** για ολόκληρο το έργο.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Βήμα 2: Ανάγνωση Πληροφοριών Βάσης Ανάθεσης

Αφού οριστεί η βάση, κάθε ανάθεση πόρου περιέχει τις δικές της εγγραφές βάσης. Ο βρόχος παρακάτω εξάγει και εκτυπώνει αυτές τις λεπτομέρειες, συμπεριλαμβανομένων των ημερομηνιών έναρξης/λήξης, κόστους, εργασίας και τυχόν δεδομένων χρονικής φάσης.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Βήμα 3: Σύγκριση Βάσεων Ανάθεσης

Μπορείτε να συγκρίνετε βάσεις διαφορετικών αναθέσεων χρησιμοποιώντας τους ενσωματωμένους τελεστές ισότητας και σύγκρισης. Αυτό είναι χρήσιμο όταν χρειάζεται να εντοπίσετε μετατοπίσεις χρονοδιαγράμματος ή υπερβάσεις κόστους μεταξύ εργασιών.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί Συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **Τα δεδομένα βάσης εμφανίζονται κενά** | Το αρχείο έργου ανοίχθηκε σε λειτουργία μόνο για ανάγνωση ή η βάση δεν ορίστηκε ποτέ. | Καλέστε `project.SetBaseline(BaselineType.Baseline)` πριν διαβάσετε τις βάσεις ανάθεσης. |
| **`NullReferenceException` στο `TimephasedData`** | Δεν περιέχουν όλες οι βάσεις εγγραφές χρονικής φάσης. | Πάντα ελέγχετε `baseline.TimephasedData != null` (όπως φαίνεται στον κώδικα). |
| **Λανθασμένη ανάκτηση UID** | Οι τιμές UID διαφέρουν μεταξύ εκδόσεων αρχείων. | Χρησιμοποιήστε `ResourceAssignments.GetByUid` με το σωστό UID ή επαναλάβετε για να βρείτε την ανάθεση που χρειάζεστε. |

## Συχνές Ερωτήσεις

**Ε: Μπορεί το Aspose.Tasks να διαχειριστεί πολλαπλές βάσεις για μία ενιαία ανάθεση;**  
Α: Ναι, το Aspose.Tasks υποστηρίζει πολλαπλές βάσεις για κάθε ανάθεση, επιτρέποντας ολοκληρωμένη παρακολούθηση της προόδου του έργου στο χρόνο.

**Ε: Είναι το Aspose.Tasks συμβατό με διάφορες μορφές αρχείων έργου εκτός του MPP;**  
Α: Ναι, το Aspose.Tasks υποστηρίζει ευρύ φάσμα μορφών αρχείων έργου, συμπεριλαμβανομένων XML, MPX και MPP, εξασφαλίζοντας συμβατότητα με διάφορα εργαλεία διαχείρισης έργων.

**Ε: Μπορώ να τροποποιήσω προγραμματιστικά τις πληροφορίες βάσης χρησιμοποιώντας το Aspose.Tasks;**  
Α: Απόλυτα, το Aspose.Tasks παρέχει εκτενείς API για δυναμική τροποποίηση των πληροφοριών βάσης σύμφωνα με τις απαιτήσεις του έργου, προσφέροντας ευελιξία και έλεγχο στις διαδικασίες διαχείρισης.

**Ε: Παρέχει το Aspose.Tasks τεκμηρίωση και πόρους υποστήριξης για προγραμματιστές;**  
Α: Ναι, οι προγραμματιστές έχουν πρόσβαση σε πλήρη τεκμηρίωση, tutorials και φόρουμ στην ιστοσελίδα του Aspose.Tasks, διευκολύνοντας την ομαλή ενσωμάτωση και την επίλυση προβλημάτων.

**Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση του Aspose.Tasks για .NET;**  
Α: Ναι, οι προγραμματιστές μπορούν να αποκτήσουν δωρεάν δοκιμαστική έκδοση του Aspose.Tasks για .NET από [εδώ](https://releases.aspose.com/), ώστε να αξιολογήσουν τις δυνατότητες πριν αποφασίσουν για αγορά.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-03-19  
**Δοκιμασμένο Με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

---