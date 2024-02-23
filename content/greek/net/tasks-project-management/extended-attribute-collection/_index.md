---
title: Διαχείριση της συλλογής χαρακτηριστικών του έργου MS στο Aspose.Tasks
linktitle: Διαχείριση εκτεταμένης συλλογής χαρακτηριστικών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τα εκτεταμένα χαρακτηριστικά του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Χειριστείτε απρόσκοπτα τα χαρακτηριστικά εργασιών με βήμα προς βήμα καθοδήγηση.
type: docs
weight: 12
url: /el/net/tasks-project-management/extended-attribute-collection/
---
## Εισαγωγή
Θέλετε να διαχειριστείτε αποτελεσματικά τα εκτεταμένα χαρακτηριστικά του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET; Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα. Ας βουτήξουμε!
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Visual Studio: Εγκαταστήστε το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασικές γνώσεις C#: Εξοικειωθείτε με τα βασικά της γλώσσας προγραμματισμού C#.

## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Βήμα 1: Φόρτωση αρχείου έργου
Αρχικά, φορτώστε το αρχείο MS Project χρησιμοποιώντας το ακόλουθο απόσπασμα κώδικα:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Βήμα 2: Πρόσβαση στο Task and Extended Attributes
Πρόσβαση σε μια συγκεκριμένη εργασία και τα εκτεταμένα χαρακτηριστικά της:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Βήμα 3: Διαγραφή εκτεταμένων χαρακτηριστικών
Διαγράψτε τα υπάρχοντα εκτεταμένα χαρακτηριστικά εάν χρειάζεται:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Βήμα 4: Δημιουργήστε εκτεταμένους ορισμούς χαρακτηριστικών
Δημιουργήστε ορισμούς για νέα εκτεταμένα χαρακτηριστικά:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Βήμα 5: Επαναλάβετε τα εκτεταμένα χαρακτηριστικά εργασίας
Επανάληψη σε εκτεταμένα χαρακτηριστικά εργασίας:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Βήμα 6: Προσθήκη εκτεταμένων χαρακτηριστικών
Προσθέστε νέα εκτεταμένα χαρακτηριστικά στην εργασία:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Βήμα 7: Εργαστείτε με Extended Attributes
Εκτελέστε λειτουργίες σε εκτεταμένα χαρακτηριστικά όπως απαιτείται.
## Βήμα 8: Καταργήστε τα Extended Attributes
Κατάργηση εκτεταμένων χαρακτηριστικών κατά ευρετήριο ή υπό όρους:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Βήμα 9: Αντιγράψτε τα χαρακτηριστικά σε άλλη εργασία
Αντιγραφή χαρακτηριστικών σε άλλη εργασία στο ίδιο ή διαφορετικό έργο:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## συμπέρασμα
Η διαχείριση των εκτεταμένων συλλογών χαρακτηριστικών του MS Project γίνεται απρόσκοπτη με το Aspose.Tasks για .NET. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά εκτεταμένα χαρακτηριστικά, ενισχύοντας τις δυνατότητες διαχείρισης του έργου σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χειριστώ εκτεταμένα χαρακτηριστικά σε πολλά έργα;
Α: Ναι, μπορείτε να αντιγράψετε εκτεταμένα χαρακτηριστικά μεταξύ εργασιών σε διαφορετικά έργα χρησιμοποιώντας το Aspose.Tasks για .NET.
### Ε: Υπάρχουν περιορισμοί στον αριθμό των εκτεταμένων χαρακτηριστικών ανά εργασία;
Α: Το Aspose.Tasks για .NET δεν επιβάλλει εγγενείς περιορισμούς στον αριθμό των εκτεταμένων χαρακτηριστικών ανά εργασία.
### Ε: Μπορώ να δημιουργήσω προσαρμοσμένα εκτεταμένα πεδία χαρακτηριστικών;
Α: Απολύτως! Το Aspose.Tasks για .NET σάς επιτρέπει να ορίσετε προσαρμοσμένα εκτεταμένα πεδία χαρακτηριστικών προσαρμοσμένα στις απαιτήσεις του έργου σας.
### Ε: Το Aspose.Tasks για .NET υποστηρίζει ανάγνωση και εγγραφή σε αρχεία MS Project διαφόρων εκδόσεων;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει μορφές αρχείων MS Project σε διαφορετικές εκδόσεις.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).