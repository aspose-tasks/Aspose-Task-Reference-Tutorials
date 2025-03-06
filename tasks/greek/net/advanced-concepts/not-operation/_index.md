---
title: Εργασία με NOT Operation στο Aspose.Tasks
linktitle: Εργασία με NOT Operation στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χρησιμοποιείτε τη λειτουργία NOT στο Aspose.Tasks για .NET για να φιλτράρετε αποτελεσματικά τις εργασίες. Βελτιώστε τις δυνατότητες διαχείρισης του έργου σας τώρα.
weight: 20
url: /el/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εργασία με NOT Operation στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χρησιμοποιήσετε τη λειτουργία NOT στο Aspose.Tasks για .NET. Η λειτουργία NOT μας επιτρέπει να αντιστρέψουμε μια κατάσταση φίλτρου, επιτρέποντάς μας να επιλέξουμε στοιχεία που δεν πληρούν ένα καθορισμένο κριτήριο.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. Visual Studio: Χρειάζεστε μια λειτουργική εγκατάσταση του Visual Studio για να ακολουθήσετε μαζί με τα παραδείγματα κώδικα.
2.  Aspose.Tasks για .NET: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks για .NET από τη[δικτυακός τόπος](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι χρήσιμη για την κατανόηση των παραδειγμάτων κώδικα.

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισάγουμε τους απαραίτητους χώρους ονομάτων για τον κώδικά μας:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: Ρύθμιση έργου και εργασιών

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Ξεκινάμε φορτώνοντας ένα αρχείο έργου με το όνομα "Project2.mpp" χρησιμοποιώντας το`Project` τάξη που παρέχεται από το Aspose.Tasks. Βεβαιωθείτε ότι το αρχείο του έργου υπάρχει στον καθορισμένο κατάλογο.

## Βήμα 2: Συλλέξτε Εργασίες Έργου

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Εδώ, δημιουργούμε ένα`ChildTasksCollector` αντικείμενο συγκέντρωσης όλων των εργασιών εντός του έργου. Στη συνέχεια χρησιμοποιούμε`TaskUtils.Apply` μέθοδος διέλευσης στην ιεραρχία εργασιών του έργου και συλλογής όλων των θυγατρικών εργασιών.

## Βήμα 3: Καθορισμός συνθήκης φίλτρου

```csharp
var filter = new NullCondition();
```

 Ορίζουμε μια συνθήκη φίλτρου χρησιμοποιώντας μια προσαρμοσμένη κλάση με το όνομα`NullCondition`. Αυτή η συνθήκη επιλέγει εργασίες που έχουν μηδενική τιμή.

## Βήμα 4: Εφαρμόστε τη λειτουργία NOT

```csharp
var condition = new Not<Task>(filter);
```

 Εφαρμόζουμε τη λειτουργία NOT στην κατάσταση φίλτρου χρησιμοποιώντας το`Not<T>`τάξη που παρέχεται από το Aspose.Tasks. Αυτό θα αντιστρέψει την κατάσταση του φίλτρου, επιλέγοντας εργασίες που δεν έχουν μηδενική τιμή.

## Βήμα 5: Φιλτράρισμα εργασιών

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Φιλτράρουμε τις συλλεγμένες εργασίες με βάση την εφαρμοζόμενη συνθήκη χρησιμοποιώντας ένα προσαρμοσμένο`Filter` μέθοδος. Αυτή η μέθοδος λαμβάνει μια αναρίθμητη συλλογή εργασιών και μια συνθήκη φίλτρου ως παραμέτρους εισόδου και επιστρέφει μια λίστα εργασιών που ικανοποιούν τη συνθήκη.

## Βήμα 6: Επεξεργασία φιλτραρισμένων εργασιών

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Εργαστείτε με άλλα ακίνητα...
}
```

Τέλος, επαναλαμβάνουμε τις φιλτραρισμένες εργασίες και εκτελούμε τις επιθυμητές λειτουργίες. Σε αυτό το παράδειγμα, απλώς εκτυπώνουμε τα ονόματα των εργασιών στην κονσόλα.

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δουλεύουμε με τη λειτουργία NOT στο Aspose.Tasks για .NET. Αντιστρέφοντας τις συνθήκες του φίλτρου, μπορούμε να επιλέξουμε επιλεκτικά στοιχεία που δεν πληρούν καθορισμένα κριτήρια, ενισχύοντας την ευελιξία μας στον χειρισμό εργασιών εντός έργων.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλα πλαίσια .NET;

Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορα πλαίσια .NET, συμπεριλαμβανομένων των .NET Core, .NET Standard και .NET Framework.

### Ε2: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;

 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από το[δικτυακός τόπος](https://releases.aspose.com/).

### Ε3: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;

 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για τυχόν απορίες υποστήριξης ή τεχνική βοήθεια.

### Ε4: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks;

 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια από το[σελίδα αγοράς](https://purchase.aspose.com/temporary-license/).

### Ε5: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks;

 Α: Μπορείτε να αποκτήσετε πρόσβαση στην πλήρη τεκμηρίωση στο[Σελίδα τεκμηρίωσης Aspose.Tasks](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
