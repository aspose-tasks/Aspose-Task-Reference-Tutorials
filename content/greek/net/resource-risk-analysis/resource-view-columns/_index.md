---
title: Προσαρμόστε τις στήλες προβολής πόρων MS Project στο Aspose.Tasks
linktitle: Προσαρμογή στηλών προβολής πόρων στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να προσαρμόζετε αποτελεσματικά τις στήλες προβολής πόρων του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Δημιουργήστε προσαρμοσμένες προβολές για καλύτερη διαχείριση έργου.
type: docs
weight: 17
url: /el/net/resource-risk-analysis/resource-view-columns/
---
## Εισαγωγή
Το Aspose.Tasks for .NET είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project μέσω προγραμματισμού. Μια κοινή εργασία στη διαχείριση έργου είναι η προσαρμογή των προβολών για την εμφάνιση συγκεκριμένων πληροφοριών. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να προσαρμόσετε τις στήλες προβολής πόρων του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Aspose.Tasks for .NET Library: Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
2. Αρχείο Microsoft Project: Έχετε ένα δείγμα αρχείου MS Project για δοκιμή.
3. Αναπτυξιακό Περιβάλλον: Ένα περιβάλλον ανάπτυξης που έχει δημιουργηθεί με πλαίσιο .NET.
## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισάγουμε τους απαραίτητους χώρους ονομάτων στο έργο μας:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
Φορτώστε το αρχείο MS Project χρησιμοποιώντας το Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Βήμα 2: Λήψη πόρων και ορισμός επιλογών
Στη συνέχεια, λάβετε τον πόρο του οποίου οι στήλες προβολής θέλετε να προσαρμόσετε και ορίστε τις επιλογές αποθήκευσης PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Βήμα 3: Ορισμός προσαρμοσμένων στηλών
Τώρα, ορίστε προσαρμοσμένες στήλες για την προβολή πόρων. Μπορείτε να καθορίσετε διάφορα πεδία και ακόμη και να χρησιμοποιήσετε πληρεξούσιους για προσαρμοσμένους υπολογισμούς:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Βήμα 4: Επανάληψη πάνω από στήλες
Επαναλάβετε τις καθορισμένες στήλες και εμφανίστε τις ιδιότητές τους:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Βήμα 5: Αποθηκεύστε την προσαρμοσμένη προβολή
Τέλος, ορίστε την προσαρμοσμένη προβολή και αποθηκεύστε την ως αρχείο PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Ακολουθώντας αυτά τα βήματα, μπορείτε να προσαρμόσετε αποτελεσματικά τις στήλες προβολής πόρων του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET.
## συμπέρασμα
Η προσαρμογή των στηλών προβολής πόρων του MS Project είναι απαραίτητη για την εμφάνιση σχετικών πληροφοριών προσαρμοσμένων στις ανάγκες του έργου σας. Με το Aspose.Tasks για .NET, αυτή η εργασία γίνεται απλή και αποτελεσματική, επιτρέποντάς σας να δημιουργείτε προσαρμοσμένες προβολές χωρίς κόπο.
## Συχνές ερωτήσεις
### Μπορώ να προσαρμόσω τις προβολές για άλλα στοιχεία εκτός από πόρους;
Ναι, το Aspose.Tasks επιτρέπει επίσης την προσαρμογή για εργασίες, αναθέσεις και άλλα στοιχεία έργου.
### Το Aspose.Tasks υποστηρίζει την αποθήκευση προβολών σε άλλες μορφές εκτός από το PDF;
Ναι, μπορείτε να αποθηκεύσετε προβολές σε διάφορες μορφές, όπως XLSX, HTML και εικόνες.
### Είναι δυνατή η εφαρμογή μορφοποίησης στην προσαρμοσμένη προβολή;
Οπωσδήποτε, το Aspose.Tasks παρέχει εκτενείς επιλογές μορφοποίησης για τη βελτίωση της εμφάνισης των προσαρμοσμένων προβολών σας.
### Μπορώ να ενημερώσω δυναμικά την προσαρμοσμένη προβολή με βάση την αλλαγή των δεδομένων του έργου;
Ναι, μπορείτε να ενημερώσετε και να αναδημιουργήσετε την προσαρμοσμένη προβολή κάθε φορά που αλλάζουν τα υποκείμενα δεδομένα του έργου.
### Το Aspose.Tasks υποστηρίζει την ανάπτυξη πολλαπλών πλατφορμών;
Το Aspose.Tasks για .NET στοχεύει κυρίως πλατφόρμες .NET, αλλά υπάρχουν επίσης διαθέσιμες εκδόσεις για Java και άλλες πλατφόρμες.