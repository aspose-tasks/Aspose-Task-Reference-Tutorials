---
title: Συλλογή MS Project of Outline Codes στο Aspose.Tasks
linktitle: Συλλογή κωδικών περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να συλλέγετε κωδικούς περίληψης του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Αυτό το περιεκτικό σεμινάριο παρέχει οδηγίες βήμα προς βήμα.
weight: 11
url: /el/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Συλλογή MS Project of Outline Codes στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να συλλέγουμε κωδικούς περίληψης του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Θα αναλύσουμε τη διαδικασία σε οδηγίες βήμα προς βήμα για να διασφαλίσουμε τη σαφήνεια και την κατανόηση.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Visual Studio: Εγκαταστήστε το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση του προγραμματισμού C#: Η εξοικείωση με την C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Αρχικά, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στη λειτουργικότητα Aspose.Tasks στο έργο σας C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
 Ξεκινήστε φορτώνοντας το αρχείο Microsoft Project χρησιμοποιώντας το`Project` τάξη.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Βήμα 2: Συλλέξτε κωδικούς περιγράμματος
Δημιουργήστε έναν συλλέκτη για να συγκεντρώσετε τους κωδικούς περιγράμματος από τις εργασίες του έργου.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Βήμα 3: Επανάληψη μέσω εργασιών και κωδικών περιλήψεων
Επαναλάβετε τις συλλεγμένες εργασίες και τους κωδικούς περιλήψεων, εκτυπώνοντας τα στοιχεία τους.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Βήμα 4: Προσθέστε Προσαρμοσμένο Ορισμό Κώδικα Περιγράμματος
Προσθέστε έναν προσαρμοσμένο ορισμό κώδικα περίγραμμα στο έργο.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Βήμα 5: Δημιουργήστε και εισαγάγετε κώδικα περίγραμμα
Δημιουργήστε έναν κωδικό περίγραμμα και εισαγάγετε τον σε μια εργασία.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Βήμα 6: Χειρισμός κωδικών περιγράμματος
Χειριστείτε τους κωδικούς περιγράμματος όπως απαιτείται, όπως εισαγωγή, αφαίρεση ή διαγραφή.
```csharp
// Παράδειγμα χειραγώγησης
// ...
// Εισαγάγετε τον κωδικό με το 2 στη σωστή θέση
task.OutlineCodes.Insert(2, code2);
// Ελέγξτε αν έχει εισαχθεί ο κωδικός
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να συλλέγουμε κωδικούς περίληψης του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τους κώδικες περιγράμματος στα έργα σας, βελτιώνοντας την οργάνωση και τη σαφήνεια.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλες γλώσσες προγραμματισμού;
Α: Ναι, το Aspose.Tasks για .NET στοχεύει κυρίως την πλατφόρμα .NET, αλλά παρέχει επίσης υποστήριξη για άλλες γλώσσες προγραμματισμού μέσω του Aspose.Tasks for Cloud.
### Ε: Υπάρχουν περιορισμοί στο μέγεθος των αρχείων Project που μπορεί να χειριστεί το Aspose.Tasks για .NET;
Α: Το Aspose.Tasks για .NET μπορεί να χειριστεί μεγάλα αρχεία έργου αποτελεσματικά, αλλά η απόδοση μπορεί να διαφέρει ανάλογα με την πολυπλοκότητα και το μέγεθος του αρχείου.
### Ε: Είναι το Aspose.Tasks για .NET συμβατό με τις πιο πρόσφατες εκδόσεις του Microsoft Project;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των πιο πρόσφατων.
### Ε: Μπορώ να προσαρμόσω τη μορφή εξόδου όταν εργάζομαι με το Aspose.Tasks για .NET;
Α: Απολύτως, το Aspose.Tasks για .NET παρέχει εκτενείς επιλογές για την προσαρμογή της μορφής εξόδου σύμφωνα με τις απαιτήσεις σας.
### Ε: Πού μπορώ να βρω πρόσθετη υποστήριξη ή πόρους για το Aspose.Tasks για .NET;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία σχετικά με το Aspose.Tasks για .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
