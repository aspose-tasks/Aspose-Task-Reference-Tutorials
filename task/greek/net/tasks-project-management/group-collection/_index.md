---
title: Διαχείριση Συλλογών Έργων στο Aspose.Tasks
linktitle: Διαχείριση της συλλογής ομάδας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις συλλογές MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας.
type: docs
weight: 26
url: /el/net/tasks-project-management/group-collection/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο διαχείρισης συλλογών ομαδικών MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Η διαχείριση των συλλογών ομάδων είναι ζωτικής σημασίας για την οργάνωση και τον χειρισμό εργασιών και πόρων αποτελεσματικά στο πλαίσιο του έργου σας.
## Προαπαιτούμενα
Πριν προχωρήσετε σε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for .NET από το[σύνδεσμος λήψης](https://releases.aspose.com/tasks/net/).
2. Βασικές γνώσεις C#: Εξοικειωθείτε με τα βασικά στοιχεία της γλώσσας προγραμματισμού C# καθώς αυτό το σεμινάριο περιλαμβάνει κωδικοποίηση σε C#.
3. Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης, όπως το Visual Studio ή οποιοδήποτε άλλο IDE που υποστηρίζει την ανάπτυξη .NET.

## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για να δουλέψουμε με τις λειτουργίες Aspose.Tasks στον κώδικα C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Βήμα 1: Φορτώστε το έργο
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Αυτό το βήμα περιλαμβάνει τη φόρτωση του αρχείου MS Project στο αντικείμενο έργου Aspose.Tasks, επιτρέποντάς μας να εκτελέσουμε λειτουργίες σε αυτό.
## Βήμα 2: Επαναλάβετε τις ομάδες εργασιών
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Εδώ, επαναλαμβάνουμε τις ομάδες εργασιών εντός του έργου, εκτυπώνοντας λεπτομέρειες όπως ευρετήριο, όνομα και ορατότητα στο μενού για κάθε ομάδα.
## Βήμα 3: Επαναλάβετε τις ομάδες πόρων
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Ομοίως, αυτό το βήμα επαναλαμβάνεται σε ομάδες πόρων, εμφανίζοντας το ευρετήριο, το όνομα και την ορατότητά τους στο μενού.
## Βήμα 4: Εκκαθάριση και αντιγραφή ομάδων σε άλλο έργο
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Διαγράψτε τις ομάδες άλλων έργων
otherProject.TaskGroups.Clear();
// Αντιγράψτε ομάδες σε άλλο έργο
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Εδώ, διαγράφουμε τις ομάδες ενός άλλου έργου και, στη συνέχεια, αντιγράφουμε ομάδες από το αρχικό έργο σε αυτό.
## Βήμα 5: Προσθέστε μια προσαρμοσμένη ομάδα εργασιών
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Σε αυτό το βήμα, δημιουργούμε μια προσαρμοσμένη ομάδα εργασιών και την προσθέτουμε στο άλλο έργο εάν δεν υπάρχει ήδη.
## Βήμα 6: Κατάργηση όλων των ομάδων
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Τέλος, αφαιρούμε όλες τις ομάδες από το άλλο έργο.

## συμπέρασμα
Η διαχείριση των συλλογών MS Project ομάδας στο Aspose.Tasks για .NET είναι απαραίτητη για την αποτελεσματική οργάνωση και χειρισμό των δεδομένων έργου. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά ομάδες εργασιών και πόρων στα έργα σας, βελτιώνοντας τη συνολική διαχείριση του έργου.
## Συχνές ερωτήσεις
### Είναι το Aspose.Tasks για .NET συμβατό με όλες τις εκδόσεις του MS Project;
Το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των 2003, 2007, 2010, 2013, 2016 και 2019.
### Μπορώ να προσαρμόσω τις ιδιότητες ομάδας χρησιμοποιώντας το Aspose.Tasks για .NET;
Ναι, μπορείτε να προσαρμόσετε τις ιδιότητες της ομάδας, όπως το όνομα και την ορατότητα, χρησιμοποιώντας το Aspose.Tasks για .NET.
### Το Aspose.Tasks για .NET προσφέρει συμβατότητα μεταξύ πλατφορμών;
Το Aspose.Tasks για .NET στοχεύει κυρίως το πλαίσιο .NET, αλλά μπορεί να χρησιμοποιηθεί σε σενάρια πολλαπλών πλατφορμών με .NET Core και .NET Standard.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για .NET;
 Μπορείτε να λάβετε υποστήριξη για το Aspose.Tasks για .NET μέσω του[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks για .NET από το[δικτυακός τόπος](https://releases.aspose.com/).