---
title: Διαχειριστείτε τις τιμές περίληψης έργου MS με το Aspose.Tasks
linktitle: Συλλογή των τιμών περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε τις τιμές περιγράμματος σε αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Βήμα προς βήμα σεμινάριο με παραδείγματα κώδικα.
type: docs
weight: 17
url: /el/net/outline-code-page-settings/outline-value-collection/
---
## Εισαγωγή
Το Aspose.Tasks για .NET παρέχει ένα ολοκληρωμένο σύνολο δυνατοτήτων για αλληλεπίδραση με αρχεία Microsoft Project. Ένα τέτοιο χαρακτηριστικό είναι η δυνατότητα διαχείρισης τιμών περιγράμματος μέσα σε ένα έργο. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να συλλέγουμε και να χειριζόμαστε τιμές περιγράμματος χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Aspose.Tasks για .NET: Μπορείτε να κάνετε λήψη της βιβλιοθήκης από[εδώ](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε εγκατεστημένο ένα κατάλληλο IDE, όπως το Visual Studio.
3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.
## Εισαγωγή χώρων ονομάτων
Στο αρχείο κώδικα C#, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση σε κλάσεις και μεθόδους Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα:
## Βήμα 1: Φορτώστε ένα αρχείο έργου
 Αρχικά, αρχικοποιήστε ένα`Project` αντικείμενο φορτώνοντας ένα υπάρχον αρχείο Microsoft Project:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Βήμα 2: Διαγράψτε τις υπάρχουσες τιμές περίγραμμα
Στη συνέχεια, διαγράψτε τυχόν υπάρχουσες τιμές περιγράμματος από το έργο:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Βήμα 3: Ορισμός Νέου Κώδικα Περιγράμματος
Τώρα, ορίστε έναν νέο κωδικό περιγράμματος με περιγραφή και τιμή:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Βήμα 4: Ενημερώστε την τιμή περίγραμμα
Ενημερώστε την τιμή του κωδικού περίγραμμα:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Βήμα 5: Επαναλάβετε τις τιμές περίγραμμα
Επαναλάβετε τις τιμές περιγράμματος και εκτυπώστε τις λεπτομέρειες τους:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Βήμα 6: Χειρισμός τιμών περιγράμματος
Εκτελέστε λειτουργίες όπως αφαίρεση, εισαγωγή και αντιγραφή τιμών περιγράμματος όπως απαιτείται:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εργαζόμαστε με τιμές περιγράμματος σε αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας τα παρεχόμενα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τις τιμές περιγράμματος στα έργα σας, επιτρέποντας μεγαλύτερο έλεγχο και ευελιξία.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χειριστώ πολλούς κωδικούς περιγράμματος ταυτόχρονα;
Α: Ναι, μπορείτε να ορίσετε και να χειριστείτε πολλούς κώδικες περιγράμματος σε ένα έργο χρησιμοποιώντας το Aspose.Tasks.
### Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP και XML.
### Ε: Πώς μπορώ να χειριστώ σφάλματα κατά την εργασία με τιμές περιγράμματος;
Α: Μπορείτε να εφαρμόσετε μηχανισμούς διαχείρισης σφαλμάτων, όπως μπλοκ try-catch για να διαχειριστείτε με χάρη τις εξαιρέσεις.
### Ε: Μπορώ να προσαρμόσω την εμφάνιση των τιμών περιγράμματος στο έργο μου;
Α: Ναι, το Aspose.Tasks παρέχει εκτεταμένα API για την προσαρμογή της εμφάνισης και της συμπεριφοράς των τιμών περίγραμμα σύμφωνα με τις απαιτήσεις σας.
### Ε: Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για υποστήριξη της κοινότητας και να εξερευνήσετε το[τεκμηρίωση](https://reference.aspose.com/tasks/net/) για λεπτομερείς πληροφορίες σχετικά με τα API και τις δυνατότητες.