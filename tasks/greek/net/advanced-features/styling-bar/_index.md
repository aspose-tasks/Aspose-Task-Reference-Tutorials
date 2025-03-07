---
title: Styling Bar στο Aspose.Tasks
linktitle: Styling Bar στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να δημιουργείτε στυλ γραμμών στο Aspose.Tasks για .NET για να βελτιώσετε την οπτικοποίηση του έργου.
weight: 19
url: /el/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Styling Bar στο Aspose.Tasks

## Εισαγωγή

Η διαμόρφωση ράβδων στυλ στο Aspose.Tasks είναι μια ουσιαστική πτυχή της δημιουργίας οπτικά ελκυστικών σχεδίων έργου. Με την ευελιξία που προσφέρει το Aspose.Tasks API, οι προγραμματιστές μπορούν να προσαρμόσουν διάφορες πτυχές των γραμμών, όπως το χρώμα, το σχήμα και το στυλ κειμένου, για να βελτιώσουν την οπτικοποίηση του έργου. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να δημιουργείτε στυλ γραμμών χρησιμοποιώντας το Aspose.Tasks για .NET, αναλύοντας κάθε παράδειγμα σε διαχειρίσιμα βήματα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Tasks for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for .NET από το[σελίδα λήψης](https://releases.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης με υποστήριξη πλαισίου .NET.
3. Βασική κατανόηση της C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι επωφελής.

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για πρόσβαση σε κλάσεις και μεθόδους Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Βήμα 1: Φορτώστε το έργο

Για να ξεκινήσετε, φορτώστε το αρχείο του έργου χρησιμοποιώντας το Aspose.Tasks API:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Βήμα 2: Διαμόρφωση επιλογών αποθήκευσης

Καθορίστε τις επιλογές αποθήκευσης, προσδιορίζοντας τα στυλ της γραμμής που θα εφαρμοστούν:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Βήμα 3: Ορισμός στυλ γραμμής

Δημιουργήστε ένα νέο στυλ γραμμής και προσαρμόστε τις ιδιότητές του:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Ορισμός τύπου στοιχείου γραμμής
style.BarColor = Color.Green; // Ορισμός χρώματος γραμμής
style.BarShape = BarShape.HalfHeight; // Ορίστε σχήμα ράβδου
style.StartShape = Shape.LeftBracket; // Ορίστε το σχήμα στην αρχή της ράβδου
style.StartShapeColor = Color.Aqua; // Ορίστε το χρώμα του σχήματος έναρξης
style.EndShape = Shape.RightBracket; // Ρυθμίστε το σχήμα στο τέλος της ράβδου
style.EndShapeColor = Color.Aquamarine; // Σετ χρώματος του ακραίου σχήματος
style.TextStyle = new TextStyle(); // Ορισμός στυλ κειμένου
style.TextStyle.BackgroundColor = Color.Black; // Ορισμός χρώματος φόντου για κείμενο
```

## Βήμα 4: Προσαρμογή του μετατροπέα κειμένου

Προαιρετικά, προσαρμόστε τον μετατροπέα κειμένου για να τροποποιήσετε την απόδοση κειμένου:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Βήμα 5: Προσθήκη στυλ γραμμής στις Επιλογές

Προσθέστε το στυλ διαμορφωμένης γραμμής στις επιλογές αποθήκευσης:

```csharp
options.BarStyles.Add(style);
```

## Βήμα 6: Αποθηκεύστε το έργο

Τέλος, αποθηκεύστε το έργο με τα εφαρμοσμένα στυλ γραμμής:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## συμπέρασμα

Η προσαρμογή των στυλ γραμμής στο Aspose.Tasks για .NET παρέχει στους προγραμματιστές τη δυνατότητα να δημιουργούν οπτικά ελκυστικά σχέδια έργων. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να διαμορφώσετε αποτελεσματικά τις γραμμές για να ικανοποιήσετε συγκεκριμένες απαιτήσεις οπτικοποίησης έργου.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να εφαρμόσω πολλά στυλ γραμμής σε ένα μόνο έργο;

A1: Ναι, μπορείτε να ορίσετε και να εφαρμόσετε πολλά στυλ γραμμής σε διαφορετικούς τύπους εργασιών στο ίδιο έργο.
   
### Ε2: Είναι δυνατή η δυναμική αλλαγή των στυλ γραμμής κατά τη διάρκεια του χρόνου εκτέλεσης;

A2: Ναι, μπορείτε να τροποποιήσετε δυναμικά τα στυλ γραμμής με βάση ορισμένες συνθήκες ή προτιμήσεις χρήστη εντός της εφαρμογής σας.
   
### Ε3: Το Aspose.Tasks υποστηρίζει την εξαγωγή έργων με γραμμές στυλ σε διαφορετικές μορφές αρχείων;

A3: Ναι, το Aspose.Tasks υποστηρίζει την εξαγωγή έργων με γραμμές στυλ σε διάφορες μορφές όπως PDF, XLSX και HTML.
   
### Ε4: Υπάρχουν προκαθορισμένα στυλ γραμμής διαθέσιμα στο Aspose.Tasks;

A4: Ενώ το Aspose.Tasks παρέχει προεπιλεγμένα στυλ γραμμής, οι προγραμματιστές μπορούν επίσης να δημιουργήσουν προσαρμοσμένα στυλ γραμμής προσαρμοσμένα στις απαιτήσεις του έργου τους.
   
### Ε5: Μπορώ να ανακτήσω και να τροποποιήσω υπάρχοντα στυλ γραμμής σε ένα έργο χρησιμοποιώντας το API;

A5: Ναι, μπορείτε να ανακτήσετε και να τροποποιήσετε υπάρχοντα στυλ γραμμής μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για .NET API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
