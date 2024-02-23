---
title: Κατακτήστε τις τιμές περίληψης του έργου MS με το Aspose.Tasks
linktitle: Διαχείριση τιμών περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις τιμές περιγράμματος του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε τα περιγράμματα του έργου με ευκολία.
type: docs
weight: 16
url: /el/net/outline-code-page-settings/outline-values/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να διαχειριστείτε τις τιμές περίγραμμα του Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για .NET. Με το Aspose.Tasks, μπορείτε εύκολα να χειριστείτε τους κώδικες περιγράμματος, να δημιουργήσετε νέες τιμές περιγράμματος και να προσαρμόσετε τα περιγράμματα έργων σύμφωνα με τις απαιτήσεις σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Εγκατάσταση του Aspose.Tasks για .NET: Λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης, όπως το Visual Studio, με συμβατότητα πλαισίου .NET.
3. Βασική κατανόηση του προγραμματισμού C#: Εξοικειωθείτε με τα βασικά στοιχεία της γλώσσας προγραμματισμού C#, καθώς θα χρησιμοποιήσουμε την C# για να εργαστούμε με τη βιβλιοθήκη Aspose.Tasks.

## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στον κώδικα C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Αυτό το βήμα προετοιμάζει ένα νέο αντικείμενο Project και φορτώνει το αρχείο Microsoft Project από τον καθορισμένο κατάλογο.
## Βήμα 2: Καθορίστε ορισμούς κωδικών περιγράμματος
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Εδώ, ορίζουμε δύο αντικείμενα OutlineCodeDefinition και τα προσθέτουμε στη συλλογή OutlineCodes του έργου.
## Βήμα 3: Καθορίστε τη Μάσκα περιγράμματος
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Αυτό το βήμα δημιουργεί μια Μάσκα Outline για τον ορισμό του κώδικα περίγραμμα.
## Βήμα 4: Δημιουργήστε τιμές περίληψης
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Σε αυτό το βήμα, δημιουργούμε δύο αντικείμενα OutlineValue και ορίζουμε τις ιδιότητές τους, όπως τιμή, αναγνωριστικό τιμής, τύπο, περιγραφή και κατάσταση σύμπτυξης.

## συμπέρασμα
Η διαχείριση των τιμών περίγραμμα του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET είναι απλή με τις παρεχόμενες λειτουργίες. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να χειριστείτε αποτελεσματικά τους κωδικούς και τις τιμές περιγράμματος για να προσαρμόσετε τα περιγράμματα του έργου σύμφωνα με τις ανάγκες σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλα πλαίσια .NET;
Α: Ναι, το Aspose.Tasks είναι συμβατό με διάφορα πλαίσια .NET, διασφαλίζοντας ευελιξία στο περιβάλλον ανάπτυξής σας.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;
 Α: Ναι, μπορείτε να αποκτήσετε πρόσβαση σε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Α: Για υποστήριξη και βοήθεια, μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks.[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια για το Aspose.Tasks;
 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια χρήσης για το Aspose.Tasks από[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks;
 Α: Μπορείτε να ανατρέξετε στην ολοκληρωμένη διαθέσιμη τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/net/).