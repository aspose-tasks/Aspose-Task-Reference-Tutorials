---
title: Χειρισμός κριτηρίων ομάδας έργου MS στο Aspose.Tasks
linktitle: Κριτήρια ομάδας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε πώς να χειρίζεστε αρχεία MS Project μέσω προγραμματισμού στο .NET χρησιμοποιώντας το Aspose.Tasks. Ανάκτηση πληροφοριών ομάδας εργασιών και κριτηρίων βήμα προς βήμα.
weight: 27
url: /el/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Χειρισμός κριτηρίων ομάδας έργου MS στο Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks για .NET είναι ένα ισχυρό API που διευκολύνει την εργασία με αρχεία Microsoft Project στις εφαρμογές σας .NET. Είτε αναπτύσσετε λογισμικό διαχείρισης έργου είτε χρειάζεται να χειριστείτε τα δεδομένα του έργου μέσω προγραμματισμού, το Aspose.Tasks προσφέρει ένα ολοκληρωμένο σύνολο λειτουργιών για να καλύψει τις ανάγκες σας.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Γνώση C# και .NET Framework
Η εξοικείωση με τη γλώσσα προγραμματισμού C# και το .NET Framework είναι απαραίτητη για την κατανόηση και την υλοποίηση των παραδειγμάτων που παρέχονται σε αυτό το σεμινάριο.
### 2. Εγκατάσταση του Aspose.Tasks για .NET
 Βεβαιωθείτε ότι έχετε εγκατεστημένο το Aspose.Tasks για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/tasks/net/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται.
### 3. Ολοκληρωμένο Αναπτυξιακό Περιβάλλον (IDE)
Έχετε ένα IDE όπως το Visual Studio εγκατεστημένο στο σύστημά σας για τη σύνταξη και την εκτέλεση κώδικα C#.

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, εισαγάγετε τους απαραίτητους χώρους ονομάτων στον κώδικα C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Βήμα 1: Φορτώστε ένα αρχείο Microsoft Project
Αρχικά, καθορίστε τη διαδρομή προς το αρχείο Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Αντικαθιστώ`"Your Document Directory"` με τη διαδρομή προς το αρχείο του έργου σας.
## Βήμα 2: Ανάκτηση πληροφοριών ομάδων εργασιών
Στη συνέχεια, ανακτήστε πληροφορίες σχετικά με τις ομάδες εργασιών στο έργο:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Αυτό το απόσπασμα κώδικα εκτυπώνει τον συνολικό αριθμό των ομάδων εργασιών, ανακτά τη δεύτερη ομάδα εργασιών, το όνομά της και τον αριθμό των κριτηρίων που διαθέτει.
## Βήμα 3: Ανάκτηση των πληροφοριών κριτηρίου της ομάδας εργασιών
Τώρα, ας εμβαθύνουμε στις λεπτομέρειες ενός συγκεκριμένου κριτηρίου εντός της ομάδας εργασιών:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Αυτό το τμήμα εμφανίζει διάφορες ιδιότητες του κριτηρίου, όπως ευρετήριο, πεδίο, πληροφορίες ομαδοποίησης, χρώμα κελιού, χρώμα γραμματοσειράς, διάστημα ομάδας και σημείο εκκίνησης.
## Βήμα 4: Ανάκτηση των πληροφοριών γραμματοσειράς του κριτηρίου
Τέλος, λάβετε λεπτομέρειες σχετικά με τη γραμματοσειρά του κριτηρίου:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Αυτό το βήμα εκτυπώνει το όνομα της γραμματοσειράς, το μέγεθος, το στυλ και εάν το κριτήριο ταξινομείται σε αύξουσα ή φθίνουσα σειρά.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο χρήσης του Aspose.Tasks για .NET για την ανάκτηση πληροφοριών σχετικά με ομάδες εργασιών και κριτήρια από ένα αρχείο Microsoft Project. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να εργαστείτε αποτελεσματικά με δεδομένα έργου μέσω προγραμματισμού στις εφαρμογές σας .NET.
## Συχνές ερωτήσεις
### Μπορεί το Aspose.Tasks να χειριστεί μεγάλα αρχεία Microsoft Project;
Το Aspose.Tasks είναι βελτιστοποιημένο για να χειρίζεται αποτελεσματικά μεγάλα αρχεία έργων, διασφαλίζοντας υψηλή απόδοση και αξιοπιστία.
### Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις του Microsoft Project, διασφαλίζοντας τη συμβατότητα μεταξύ διαφορετικών μορφών αρχείων.
### Μπορώ να χειριστώ τα δεδομένα του έργου χρησιμοποιώντας το Aspose.Tasks;
Οπωσδήποτε, το Aspose.Tasks παρέχει εκτεταμένες λειτουργίες για τον χειρισμό δεδομένων έργου, συμπεριλαμβανομένων εργασιών, πόρων, ημερολογίων και άλλων.
### Το Aspose.Tasks προσφέρει υποστήριξη για διαφορετικές πλατφόρμες .NET;
Ναι, το Aspose.Tasks υποστηρίζει πολλές πλατφόρμες .NET, συμπεριλαμβανομένων των .NET Framework, .NET Core και .NET Standard.
### Υπάρχει κάποιο φόρουμ κοινότητας για το Aspose.Tasks όπου μπορώ να ζητήσω βοήθεια;
 Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για να κάνετε ερωτήσεις, να μοιραστείτε γνώσεις και να συνεργαστείτε με άλλους χρήστες.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
