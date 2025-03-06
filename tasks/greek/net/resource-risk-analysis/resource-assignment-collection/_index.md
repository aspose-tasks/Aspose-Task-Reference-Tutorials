---
title: Συλλογή εργασιών πόρων στο Aspose.Tasks
linktitle: Συλλογή εργασιών πόρων στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τις αναθέσεις πόρων στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Βήμα προς βήμα σεμινάριο με παραδείγματα κώδικα.
weight: 12
url: /el/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Συλλογή εργασιών πόρων στο Aspose.Tasks

## Εισαγωγή
Καλώς ήρθατε σε αυτό το ολοκληρωμένο σεμινάριο σχετικά με τη διαχείριση αναθέσεων πόρων στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία βήμα προς βήμα, διασφαλίζοντας ότι έχετε πλήρη κατανόηση του πώς να χειρίζεστε αποτελεσματικά τις αναθέσεις πόρων. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο οδηγός θα σας καθοδηγήσει σε όλα όσα χρειάζεται να γνωρίζετε.
## Προαπαιτούμενα
Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες ρυθμίσεις:
1.  Εγκατεστημένο Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Tasks για .NET στο περιβάλλον ανάπτυξης σας. Εάν όχι, μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Βασική γνώση C#: Αυτό το σεμινάριο προϋποθέτει ότι έχετε βασική κατανόηση της γλώσσας προγραμματισμού C#.
3. Αρχείο Microsoft Project: Έχετε έτοιμο ένα αρχείο Microsoft Project για δοκιμαστικούς σκοπούς. Εάν δεν έχετε, μπορείτε να δημιουργήσετε ένα δείγμα αρχείου.

## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισάγουμε τους απαραίτητους χώρους ονομάτων:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
Ξεκινήστε φορτώνοντας το αρχείο Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Βήμα 2: Προσθήκη Εργασίας και Πόρων
Τώρα, ας προσθέσουμε μια εργασία και έναν πόρο στο έργο:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Βήμα 3: Εκχώρηση πόρου στην εργασία
Στη συνέχεια, θα εκχωρήσουμε τον πόρο στην εργασία:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Βήμα 4: Εργασία με διαφορετικούς τύπους εργασιών
Μπορείτε επίσης να εργαστείτε με εργασίες που αφορούν μονάδες ή κόστη:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Ορίστε ιδιότητες για αναθέσεις με μονάδες και κόστη με παρόμοιο τρόπο όπως φαίνεται στο Βήμα 3
```
## Βήμα 5: Εκτύπωση εργασιών
Εκτυπώστε τις εργασίες για το έργο:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Εκτύπωση λεπτομερειών ανάθεσης
}
```
## Βήμα 6: Ανάκτηση ανάθεσης από το UID
Μπορείτε να ανακτήσετε εργασίες ανά UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Βήμα 7: Ελέγξτε την κατάσταση μόνο για ανάγνωση
Επαληθεύστε εάν η συλλογή ανάθεσης πόρων είναι μόνο για ανάγνωση:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Βήμα 8: Μετατρέψτε τη συλλογή σε Λίστα και Επανάληψη
Μετατρέψτε τη συλλογή σε λίστα και επαναλάβετε την:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει πώς να διαχειρίζεστε τις αναθέσεις πόρων στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε αποτελεσματικά εργασίες και πόρους, κάνοντας τη διαχείριση έργου παιχνιδάκι.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση πριν από την αγορά του Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα κατά τη χρήση του Aspose.Tasks για .NET;
 Α: Μπορείτε να αναζητήσετε υποστήριξη από το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Μπορώ να χρησιμοποιήσω προσωρινές άδειες χρήσης για το Aspose.Tasks για .NET;
 Α: Ναι, διατίθενται προσωρινές άδειες για σκοπούς αξιολόγησης. Μπορείτε να πάρετε ένα από[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να αγοράσω μια πλήρη άδεια χρήσης για το Aspose.Tasks για .NET;
 Α: Μπορείτε να αγοράσετε μια πλήρη άδεια χρήσης από το ηλεκτρονικό κατάστημα Aspose[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
