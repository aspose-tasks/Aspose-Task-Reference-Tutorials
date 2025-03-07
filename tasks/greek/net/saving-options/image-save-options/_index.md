---
title: Image Save MS Project Options for Aspose.Tasks
linktitle: Επιλογές αποθήκευσης εικόνας για Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να αποθηκεύετε τις επιλογές του MS Project ως εικόνες χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτη ενσωμάτωση.
weight: 11
url: /el/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Image Save MS Project Options for Aspose.Tasks


## Εισαγωγή
Στον κόσμο της ανάπτυξης λογισμικού, ο αποτελεσματικός χειρισμός των εργασιών του έργου είναι ζωτικής σημασίας για την επιτυχή διαχείριση του έργου. Το Aspose.Tasks για .NET προσφέρει μια ισχυρή λύση για προγραμματιστές που εργάζονται με αρχεία Microsoft Project, επιτρέποντάς τους να χειρίζονται, να μετατρέπουν και να διαχειρίζονται εργασίες έργου απρόσκοπτα στις εφαρμογές τους .NET.
## Προαπαιτούμενα
Πριν ξεκινήσετε τη χρήση του Aspose.Tasks για .NET για να αποθηκεύσετε τις επιλογές του MS Project ως εικόνες, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστήστε το Aspose.Tasks για .NET
Για να ξεκινήσετε, πρέπει να έχετε εγκατεστημένο το Aspose.Tasks για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το[δικτυακός τόπος](https://releases.aspose.com/tasks/net/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται.
### 2. Λάβετε άδεια χρήσης (Προαιρετικό)
 Ενώ το Aspose.Tasks για .NET μπορεί να χρησιμοποιηθεί χωρίς άδεια χρήσης σε λειτουργία αξιολόγησης, η απόκτηση άδειας χρήσης συνιστάται για πλήρη λειτουργικότητα και για την κατάργηση των περιορισμών αξιολόγησης. Μπορείτε να αποκτήσετε άδεια από το[σελίδα αγοράς](https://purchase.aspose.com/buy) ή επιλέξτε ένα[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για δοκιμαστικούς σκοπούς.
### 3. Βασικές γνώσεις C# και .NET Development
Η βασική κατανόηση της γλώσσας προγραμματισμού C# και του πλαισίου .NET είναι απαραίτητη για να ακολουθήσετε μαζί με τα παραδείγματα και να ενσωματώσετε αποτελεσματικά τις λειτουργίες Aspose.Tasks στις εφαρμογές σας.
## Εισαγωγή χώρων ονομάτων
Προτού αρχίσουμε να αποθηκεύουμε τις επιλογές του MS Project ως εικόνες χρησιμοποιώντας το Aspose.Tasks για .NET, ας βεβαιωθούμε ότι εισάγουμε τους απαραίτητους χώρους ονομάτων στο έργο C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Βήμα 1: Ρύθμιση διαδρομής καταλόγου εγγράφων
Βεβαιωθείτε ότι έχετε έναν καθορισμένο κατάλογο για τα έγγραφά σας και ορίστε τη διαδρομή ανάλογα:
```csharp
String DataDir = "Your Document Directory";
```
## Βήμα 2: Φορτώστε το αρχείο MS Project
 Αρχικοποιήστε ένα νέο`Project` αντικείμενο φορτώνοντας το αρχείο MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Βήμα 3: Ορίστε τις επιλογές αποθήκευσης εικόνας
 Δημιουργήστε ένα παράδειγμα του`ImageSaveOptions`και καθορίστε τις επιθυμητές ρυθμίσεις:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Βήμα 4: Καθορίστε τις σελίδες προς αποθήκευση
Εάν χρειάζεται, καθορίστε τις σελίδες που θα αποθηκευτούν. Σε αυτό το παράδειγμα, προσθέτουμε τη σελίδα 2:
```csharp
options.Pages.Add(2);
```
## Βήμα 5: Αποθηκεύστε την εικόνα
Τέλος, αποθηκεύστε τις επιλεγμένες σελίδες ως εικόνα με τις καθορισμένες επιλογές:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## συμπέρασμα
Το Aspose.Tasks για .NET απλοποιεί τη διαδικασία εργασίας με αρχεία MS Project, επιτρέποντας στους προγραμματιστές να χειρίζονται αβίαστα τις εργασίες του έργου. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να αποθηκεύσετε αποτελεσματικά τις επιλογές του MS Project ως εικόνες στις εφαρμογές σας .NET.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET χωρίς άδεια χρήσης;
Α: Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.Tasks για .NET χωρίς άδεια χρήσης σε λειτουργία αξιολόγησης. Ωστόσο, συνιστάται να αποκτήσετε άδεια για πλήρη λειτουργικότητα και να καταργήσετε τους περιορισμούς αξιολόγησης.
### Ε2: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμή;
 Α: Μπορείτε να αποκτήσετε μια προσωρινή άδεια για σκοπούς δοκιμής από το[σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).
### Ε3: Είναι το Aspose.Tasks για .NET συμβατό με άλλα πλαίσια .NET;
Α: Ναι, το Aspose.Tasks για .NET είναι συμβατό με διάφορα πλαίσια .NET, συμπεριλαμβανομένων των .NET Core και .NET Standard.
### Ε4: Μπορώ να προσαρμόσω περαιτέρω τις επιλογές αποθήκευσης εικόνας;
Α: Ναι, μπορείτε να προσαρμόσετε τις επιλογές αποθήκευσης εικόνας σύμφωνα με τις συγκεκριμένες απαιτήσεις σας, όπως προσαρμογή μεγέθους σελίδας, ανάλυσης ή μορφής εξόδου.
### Ε5: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks για .NET;
 Α: Μπορείτε να βρείτε υποστήριξη και βοήθεια για το Aspose.Tasks για .NET στο[δικαστήριο](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
