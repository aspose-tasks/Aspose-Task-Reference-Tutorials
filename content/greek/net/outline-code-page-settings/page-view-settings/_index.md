---
title: Προσαρμόστε τις ρυθμίσεις προβολής σελίδας MS Project στο Aspose.Tasks
linktitle: Διαμόρφωση ρυθμίσεων προβολής σελίδας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαμορφώνετε τις ρυθμίσεις προβολής σελίδας στο Aspose.Tasks για .NET για να προσαρμόσετε τη μορφή εκτύπωσης των εγγράφων του Microsoft Project.
type: docs
weight: 21
url: /el/net/outline-code-page-settings/page-view-settings/
---
## Εισαγωγή
Το Microsoft Project είναι ένα ισχυρό εργαλείο για τη διαχείριση έργου, αλλά μερικές φορές χρειάζεται να προσαρμόσετε τον τρόπο προβολής και εκτύπωσης του έργου σας. Με το Aspose.Tasks για .NET, μπορείτε εύκολα να διαμορφώσετε τις ρυθμίσεις προβολής σελίδας ώστε να ανταποκρίνονται στις συγκεκριμένες απαιτήσεις σας. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε κατεβάσει και εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Αρχείο Microsoft Project: Έχετε έτοιμο ένα αρχείο Microsoft Project για το οποίο θέλετε να διαμορφώσετε τις ρυθμίσεις προβολής σελίδας.

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για να εργαστείτε με το Aspose.Tasks στο έργο σας .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
 Ξεκινήστε φορτώνοντας το αρχείο Microsoft Project σε μια παρουσία του`Project` τάξη.
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Βήμα 2: Ορίστε τον αριθμό πρώτων στηλών
Καθορίστε τον αριθμό των πρώτων στηλών που θα εκτυπωθούν σε όλες τις σελίδες.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Βήμα 3: Εκτύπωση σημειώσεων
Επιλέξτε εάν θα εκτυπώσετε σημειώσεις μαζί με το έργο.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Βήμα 4: Προσαρμογή χρονικής κλίμακας στο τέλος της σελίδας
Αποφασίστε εάν θα ταιριάζει η χρονική κλίμακα στο τέλος μιας σελίδας κατά την εκτύπωση.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Βήμα 5: Εκτυπώστε όλες τις στήλες φύλλου
Καθορίστε εάν θα εκτυπωθούν όλες οι στήλες φύλλου μιας προβολής.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Βήμα 6: Εκτύπωση λευκών σελίδων
Επιλέξτε εάν θα εκτυπωθούν κενές σελίδες μιας προβολής.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Βήμα 7: Εκτυπώστε τις πρώτες στήλες σε όλες τις σελίδες
Ορίστε εάν θα εκτυπωθεί ένας καθορισμένος αριθμός πρώτων στηλών σε όλες τις σελίδες.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Βήμα 8: Αποθηκεύστε το έργο με διαμορφωμένες ρυθμίσεις
Τέλος, αποθηκεύστε το έργο με τις διαμορφωμένες ρυθμίσεις προβολής σελίδας, καθορίζοντας τη μορφή εξόδου, όπως το PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## συμπέρασμα
Η διαμόρφωση των ρυθμίσεων προβολής σελίδας του Microsoft Project στο Aspose.Tasks για .NET είναι απλή και σας επιτρέπει να προσαρμόσετε τη μορφή εκτύπωσης στις ακριβείς ανάγκες σας. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να διασφαλίσετε ότι τα έγγραφα του έργου σας παρουσιάζονται ακριβώς όπως απαιτείται.
## Συχνές ερωτήσεις
### Ε: Μπορώ να διαμορφώσω τις ρυθμίσεις προβολής σελίδας για άλλες μορφές αρχείων εκτός από το PDF;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων για την αποθήκευση έργων, συμπεριλαμβανομένων των XLSX, MPP και HTML.
### Ε: Υπάρχουν περιορισμοί στον αριθμό των στηλών που μπορώ να εκτυπώσω;
Α: Το Aspose.Tasks σάς επιτρέπει να προσαρμόσετε τον αριθμό των στηλών που θα εκτυπωθούν με βάση τις απαιτήσεις σας.
### Ε: Μπορώ να εφαρμόσω διαφορετικές ρυθμίσεις προβολής σελίδας για διαφορετικά έργα;
Α: Ναι, μπορείτε να προσαρμόσετε τις ρυθμίσεις προβολής σελίδας ανεξάρτητα για κάθε αρχείο έργου με το οποίο εργάζεστε.
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks προσφέρει συμβατότητα με το Microsoft Project 2003 και νεότερες εκδόσεις.
### Ε: Πού μπορώ να βρω περαιτέρω βοήθεια ή υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για τυχόν απορίες ή προβλήματα που αντιμετωπίζετε κατά τη χρήση.