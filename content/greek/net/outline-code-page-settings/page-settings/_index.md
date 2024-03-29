---
title: Διαμορφώστε τις ρυθμίσεις σελίδας MS Project με το Aspose.Tasks
linktitle: Διαμόρφωση ρυθμίσεων σελίδας στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να διαμορφώνετε τις ρυθμίσεις σελίδας MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε τον προσανατολισμό, το μέγεθος και πολλά άλλα με απλά βήματα.
type: docs
weight: 20
url: /el/net/outline-code-page-settings/page-settings/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία διαμόρφωσης των ρυθμίσεων σελίδας του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Το Aspose.Tasks είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Δημιουργήστε ένα περιβάλλον ανάπτυξης με το Visual Studio ή οποιοδήποτε άλλο προτιμώμενο IDE για την ανάπτυξη .NET.

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας. Αυτοί οι χώροι ονομάτων παρέχουν πρόσβαση στις κλάσεις και τις μεθόδους Aspose.Tasks που απαιτούνται για τον χειρισμό αρχείων MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
Πρώτα, πρέπει να φορτώσετε το αρχείο MS Project για το οποίο θέλετε να διαμορφώσετε τις ρυθμίσεις σελίδας.
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Βήμα 2: Πρόσβαση στις Ρυθμίσεις σελίδας
Στη συνέχεια, θα έχετε πρόσβαση στις ρυθμίσεις σελίδας του αρχείου έργου.
```csharp
// Λάβετε τις ρυθμίσεις
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Βήμα 3: Διαμόρφωση ρυθμίσεων σελίδας
Τώρα, ας διαμορφώσουμε διάφορες ιδιότητες των ρυθμίσεων σελίδας σύμφωνα με τις απαιτήσεις σας.
```csharp
// Ορίστε τον προσανατολισμό της σελίδας σε κατακόρυφο
settings.IsPortrait = true;
// Ορίστε τον αριθμό των σελίδων σε πλάτος που θα εκτυπωθούν
settings.PagesInWidth = 5;
// Ορίστε τον αριθμό των σελίδων σε ύψος που θα εκτυπωθούν
settings.PagesInHeight = 7;
// Ορίστε το ποσοστό του κανονικού μεγέθους για να προσαρμόσετε την εκτύπωση
settings.PercentOfNormalSize = 200;
// Ρύθμιση μεγέθους χαρτιού
settings.PaperSize = PrinterPaperSize.PaperB4;
// Ορίστε τον αριθμό πρώτης σελίδας για εκτύπωση
settings.FirstPageNumber = 3;
```
## Βήμα 4: Αποθηκεύστε το Αρχείο Έργου
Τέλος, αποθηκεύστε το αρχείο του έργου με τις ενημερωμένες ρυθμίσεις σελίδας.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαμορφώνουμε τις ρυθμίσεις σελίδας του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσαρμόσετε τον προσανατολισμό της σελίδας, το μέγεθος και άλλες επιλογές εκτύπωσης σύμφωνα με τις απαιτήσεις σας.

## Συχνές ερωτήσεις
### Ε: Μπορώ να διαμορφώσω τις ρυθμίσεις σελίδας για πολλά αρχεία MS Project ταυτόχρονα;
Α: Ναι, μπορείτε να κάνετε επαναφορά σε πολλά αρχεία έργου και να εφαρμόσετε τις ίδιες ρυθμίσεις σελίδας σε καθένα.
### Ε: Είναι δυνατή η επαναφορά των ρυθμίσεων της σελίδας στις προεπιλογές;
Α: Οπωσδήποτε, μπορείτε απλά να παραλείψετε τα βήματα διαμόρφωσης ή να επαναφέρετε τις ρυθμίσεις στις προεπιλεγμένες τιμές τους.
### Ε: Υπάρχουν περιορισμοί στα μεγέθη χαρτιού που υποστηρίζονται;
Α: Το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μεγεθών χαρτιού, συμπεριλαμβανομένων τυπικών και προσαρμοσμένων μεγεθών.
### Ε: Μπορώ να αυτοματοποιήσω τη διαδικασία διαμόρφωσης ρυθμίσεων σελίδας;
Α: Σίγουρα, μπορείτε να ενσωματώσετε αυτήν τη λειτουργία στη ροή εργασιών της εφαρμογής σας για να αυτοματοποιήσετε τη διαμόρφωση ρυθμίσεων σελίδας.
### Ε: Το Aspose.Tasks προσφέρει υποστήριξη για διαφορετικές μορφές αρχείων εκτός από το .mpp;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων όπως XML, MPT και HTML, μεταξύ άλλων.