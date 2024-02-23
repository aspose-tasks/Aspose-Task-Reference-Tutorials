---
title: Αποθήκευση αρχείων έργου MS σε διάφορες μορφές στο Aspose.Tasks
linktitle: Αποθήκευση αρχείων σε διάφορες μορφές στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να αποθηκεύετε αρχεία MS Project σε διάφορες μορφές χρησιμοποιώντας το Aspose.Tasks για .NET. Εύκολα βήματα για αποτελεσματική διαχείριση έργου.
type: docs
weight: 17
url: /el/net/rate-recurring-tasks/save-file-formats/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο αποθήκευσης αρχείων Microsoft Project σε διάφορες μορφές χρησιμοποιώντας το Aspose.Tasks για .NET. Το Aspose.Tasks είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να χειρίζονται και να διαχειρίζονται αρχεία έργου μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET, όπως το Visual Studio.
3. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων
Βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στην αρχή του αρχείου C#:
```csharp

using Aspose.Tasks.Saving;
```
## Βήμα 1: Δημιουργήστε ένα αντικείμενο έργου
Πρώτα, δημιουργήστε ένα αντικείμενο Project και φορτώστε το αρχείο Microsoft Project.
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Βήμα 2: Αποθήκευση έργου σε μορφή CSV
Τώρα, ας αποθηκεύσουμε το έργο σε μορφή CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Βήμα 3: Εξερευνήστε άλλες μορφές
 Το Aspose.Tasks υποστηρίζει διάφορες μορφές για την αποθήκευση αρχείων έργου, όπως XML, PDF, XLSX και άλλα. Μπορείτε να εξερευνήσετε αυτές τις μορφές αλλάζοντας απλώς τις`SaveFileFormat` παραμέτρους στο`Save` μέθοδος.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να αποθηκεύσετε αρχεία Microsoft Project σε διάφορες μορφές χρησιμοποιώντας το Aspose.Tasks για .NET.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να αποθηκεύουμε αρχεία MS Project σε διαφορετικές μορφές χρησιμοποιώντας το Aspose.Tasks για .NET. Το Aspose.Tasks απλοποιεί τη διαδικασία χειρισμού αρχείων έργου μέσω προγραμματισμού, προσφέροντας ευελιξία και αποτελεσματικότητα στους προγραμματιστές.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks υποστηρίζει μορφές Microsoft Project 2003 XML, Microsoft Project 2007 MPP και Microsoft Project 2010 MPP.
### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks πριν από την αγορά;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks.[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Διατίθενται προσωρινές άδειες για το Aspose.Tasks;
 Α: Ναι, διατίθενται προσωρινές άδειες για σκοπούς αξιολόγησης. Μπορείτε να πάρετε ένα[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Ποια είναι η τιμολόγηση για το Aspose.Tasks;
 Α: Πληροφορίες τιμολόγησης μπορείτε να βρείτε στη σελίδα αγοράς Aspose.Tasks[εδώ](https://purchase.aspose.com/buy).