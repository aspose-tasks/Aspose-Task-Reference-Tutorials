---
title: Τύποι πόρων στο Aspose.Tasks
linktitle: Τύποι πόρων στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να εργάζεστε με διαφορετικούς τύπους πόρων στο Aspose.Tasks για .NET, συμπεριλαμβανομένων πόρων εργασίας, υλικών και κόστους, μέσα από ένα βήμα προς βήμα εκμάθηση.
weight: 14
url: /el/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Τύποι πόρων στο Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks for .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project μέσω προγραμματισμού. Είτε διαχειρίζεστε εργασίες, πόρους ή χρονοδιαγράμματα, το Aspose.Tasks απλοποιεί τη διαδικασία παρέχοντας ένα ολοκληρωμένο σύνολο API. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στους διαφορετικούς τύπους πόρων που μπορείτε να χρησιμοποιήσετε στα έργα σας χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Visual Studio: Εγκαταστήστε το Visual Studio, ένα ισχυρό ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) για ανάπτυξη .NET.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασικές γνώσεις C#: Εξοικειωθείτε με τη C#, τη γλώσσα προγραμματισμού που χρησιμοποιείται για την ανάπτυξη .NET.

## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για πρόσβαση στις λειτουργίες του Aspose.Tasks για .NET:
```csharp
    
```

## Βήμα 1: Δημιουργήστε μια νέα παρουσία έργου
```csharp
var project = new Project();
```
Αυτή η γραμμή προετοιμάζει ένα νέο αντικείμενο Project, το οποίο χρησιμεύει ως κοντέινερ για όλα τα δεδομένα και τις λειτουργίες που σχετίζονται με το έργο.
## Βήμα 2: Προσθέστε έναν πόρο εργασίας
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Εδώ, δημιουργούμε έναν νέο πόρο εργασίας με το όνομα "Work resource" και καθορίζουμε τον τύπο του ως ResourceType.Work.
## Βήμα 3: Προσθέστε έναν πόρο υλικού
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Αυτό το βήμα προσθέτει έναν πόρο υλικού που ονομάζεται "Material Resource" με τον τύπο του να έχει οριστεί σε ResourceType.Material. Επιπλέον, καθορίζουμε την ετικέτα υλικού ως "kg" για να υποδείξουμε τη μονάδα μέτρησης.
## Βήμα 4: Προσθέστε έναν πόρο κόστους
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Τέλος, προσθέτουμε έναν πόρο κόστους με το όνομα "Πόρος κόστους" και ορίζουμε τον τύπο του ως ResourceType.Cost. Επιπλέον, ορίσαμε την τιμή κόστους σε 59,99, που αντιπροσωπεύει τη χρηματική αξία που σχετίζεται με αυτόν τον πόρο.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εργασίας με διαφορετικούς τύπους πόρων στο Aspose.Tasks για .NET, συμπεριλαμβανομένων πόρων εργασίας, υλικού και κόστους. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να διαχειριστείτε αποτελεσματικά τους πόρους στα έργα σας μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλες μορφές λογισμικού διαχείρισης έργου;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές, συμπεριλαμβανομένων των Microsoft Project (MPP), Primavera P6 και άλλων.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω τεχνική υποστήριξη για το Aspose.Tasks για .NET;
 Α: Μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15) για τεχνική βοήθεια.
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Το Aspose.Tasks για .NET παρέχει τεκμηρίωση για αναφορά;
 Α: Ναι, μπορείτε να βρείτε την τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
