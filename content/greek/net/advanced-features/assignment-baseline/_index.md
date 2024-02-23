---
title: Διαχείριση της γραμμής βάσης εργασιών στο Aspose.Tasks
linktitle: Διαχείριση της γραμμής βάσης εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις γραμμές βάσης ανάθεσης με το Aspose.Tasks για .NET, διασφαλίζοντας ακριβή παρακολούθηση της προόδου και της απόδοσης του έργου.
type: docs
weight: 14
url: /el/net/advanced-features/assignment-baseline/
---
## Εισαγωγή

Όταν εργάζεστε σε εργασίες διαχείρισης έργου, η διαχείριση των βασικών γραμμών ανάθεσης είναι ζωτικής σημασίας για την ακριβή παρακολούθηση της προόδου. Το Aspose.Tasks για .NET παρέχει ένα ολοκληρωμένο σύνολο εργαλείων για τον αποτελεσματικό χειρισμό των βασικών γραμμών ανάθεσης. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία διαχείρισης των βασικών γραμμών ανάθεσης βήμα προς βήμα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις γλώσσας προγραμματισμού C#.
- Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
- Η βιβλιοθήκη Aspose.Tasks για .NET προστέθηκε στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
- Πρόσβαση σε αρχείο έργου σε μορφή MPP.

## Εισαγωγή χώρων ονομάτων

Για να ξεκινήσετε να εργάζεστε με το Aspose.Tasks, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας C#. Προσθέστε τους ακόλουθους χώρους ονομάτων στην αρχή του αρχείου C#:

```csharp
using Aspose.Tasks;
using System;


```

## Βήμα 1: Φόρτωση έργου και ορισμός γραμμής βάσης

 Αρχικά, φορτώστε το αρχείο του έργου χρησιμοποιώντας το`Project` τάξη από το Aspose.Tasks. Στη συνέχεια, ορίστε τον τύπο γραμμής βάσης για το έργο χρησιμοποιώντας το`SetBaseline` μέθοδος.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Βήμα 2: Διαβάστε τις πληροφορίες βασικής γραμμής εργασίας

Επαναλάβετε σε κάθε ανάθεση πόρων στο έργο και ανακτήστε βασικές πληροφορίες για κάθε ανάθεση.

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

## Βήμα 3: Ελέγξτε την ισότητα γραμμής βάσης

Συγκρίνετε βασικές πληροφορίες για διαφορετικές εργασίες χρησιμοποιώντας διάφορες μεθόδους σύγκρισης που παρέχονται από το Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Ελέγξτε την ισότητα της γραμμής βάσης
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Ελέγξτε τη σύγκριση της γραμμής βάσης
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Εμφάνιση κωδικών κατακερματισμού γραμμής βάσης
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## συμπέρασμα

Η διαχείριση των βασικών γραμμών ανάθεσης είναι αναπόσπαστο κομμάτι της διαχείρισης έργου, επιτρέποντας την ακριβή παρακολούθηση της προόδου και της απόδοσης. Με το Aspose.Tasks για .NET, ο χειρισμός των βασικών γραμμών ανάθεσης γίνεται εξορθολογισμένος και αποτελεσματικός, παρέχοντας στους προγραμματιστές ισχυρά εργαλεία για τη βελτίωση των ροών εργασιών διαχείρισης έργων.

## Συχνές ερωτήσεις

### Ε1: Μπορεί το Aspose.Tasks να χειριστεί πολλές γραμμές βάσης για μία μόνο εργασία;

A1: Ναι, το Aspose.Tasks υποστηρίζει πολλαπλές γραμμές βάσης για κάθε εργασία, επιτρέποντας την πλήρη παρακολούθηση της προόδου του έργου με την πάροδο του χρόνου.

### Ε2: Είναι το Aspose.Tasks συμβατό με διάφορες μορφές αρχείων έργου εκτός από το MPP;

A2: Ναι, το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων έργου, συμπεριλαμβανομένων των XML, MPX και MPP, διασφαλίζοντας τη συμβατότητα με διάφορα εργαλεία διαχείρισης έργου.

### Ε3: Μπορώ να τροποποιήσω τις πληροφορίες βασικής γραμμής μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks;

A3: Απολύτως, το Aspose.Tasks παρέχει εκτεταμένα API για την δυναμική τροποποίηση των βασικών πληροφοριών σύμφωνα με τις απαιτήσεις του έργου, προσφέροντας ευελιξία και έλεγχο στις διαδικασίες διαχείρισης έργου.

### Ε4: Το Aspose.Tasks προσφέρει τεκμηρίωση και πόρους υποστήριξης για προγραμματιστές;

A4: Ναι, οι προγραμματιστές μπορούν να έχουν πρόσβαση σε ολοκληρωμένη τεκμηρίωση, σεμινάρια και φόρουμ στον ιστότοπο Aspose.Tasks, διευκολύνοντας την ομαλή ενσωμάτωση και την αντιμετώπιση προβλημάτων.

### Ε5: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;

 A5: Ναι, οι προγραμματιστές μπορούν να αποκτήσουν μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/), επιτρέποντάς τους να αξιολογήσουν τα χαρακτηριστικά και τις δυνατότητές του πριν λάβουν μια απόφαση αγοράς.