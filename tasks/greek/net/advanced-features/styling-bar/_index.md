---
date: 2026-04-06
description: Μάθετε πώς να αλλάξετε το στυλ των ράβδων και να προσαρμόσετε τα χρώματα
  των ράβδων στο Aspose.Tasks για .NET ώστε να βελτιώσετε την οπτικοποίηση του έργου.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Γραμμή Στυλ στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Πώς να αλλάξετε το στυλ μπαρ στο Aspose.Tasks
url: /el/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Αλλάξετε το Στυλ Μπάρων στο Aspose.Tasks

## Εισαγωγή

Αν χρειάζεστε να **πώς να αλλάξετε τη μπάρα** την εμφάνιση σε ένα αρχείο Microsoft Project, το Aspose.Tasks for .NET σας δίνει πλήρη έλεγχο πάνω στα χρώματα, τα σχήματα και τα στυλ κειμένου των μπάρων. Προσαρμόζοντας τα χρώματα των μπάρων και άλλα οπτικά χαρακτηριστικά, μπορείτε να κάνετε τα σχέδια έργων πολύ πιο εύκολα στην ανάγνωση και πιο σύμφωνα με το branding του οργανισμού σας. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα από τη φόρτωση ενός έργου μέχρι την εξαγωγή του με τους νέους οπτικούς κανόνες εφαρμοσμένους.

## Γρήγορες Απαντήσεις
- **Τι μπορώ να μορφοποιήσω;** Bars, milestones, and task text in Gantt charts.  
- **Ποια μορφή υποστηρίζει μορφοποιημένες μπάρες;** PDF, XLSX, HTML and native MPP when saved with `PdfSaveOptions`.  
- **Χρειάζομαι άδεια;** A commercial license is required for production use; a free trial works for testing.  
- **Μπορώ να εφαρμόσω πολλαπλά στυλ;** Yes – add as many `BarStyle` objects as you need.  
- **Είναι συμβατό με .NET Core;** Absolutely – works with .NET Framework and .NET Core/5/6+.

## Τι είναι η Μορφοποίηση Μπάρων στο Aspose.Tasks;

Η μορφοποίηση μπάρων σας επιτρέπει να ορίζετε οπτικούς κανόνες που η μηχανή Aspose.Tasks εφαρμόζει κατά την απόδοση των διαγραμμάτων Gantt. Κάθε κανόνας (ένα **BarStyle**) στοχεύει έναν συγκεκριμένο τύπο αντικειμένου — εργασίες, ορόσημα ή συνοπτικές εργασίες — και σας επιτρέπει να ορίσετε χρώματα, σχήματα και ακόμη προσαρμοσμένο κείμενο.

## Γιατί να προσαρμόσετε τα χρώματα των μπάρων;

Η προσαρμογή των χρωμάτων των μπάρων βοηθά τα ενδιαφερόμενα μέρη να αναγνωρίζουν αμέσως κρίσιμες διαδρομές, καθυστερημένες εργασίες ή ορόσημα. Επίσης, σας επιτρέπει να ταιριάζετε με τα εταιρικά χρώματα, κάνοντας τις αναφορές πιο επαγγελματικές και εντός brand.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Aspose.Tasks for .NET** – κατεβάστε το από τη [download page](https://releases.aspose.com/tasks/net/).  
2. Ένα περιβάλλον ανάπτυξης που υποστηρίζει .NET (Framework 4.6+, .NET Core 3.1+, ή νεότερο).  
3. Βασική εξοικείωση με C# – τα παραδείγματα χρησιμοποιούν απλό, αυτόνομο κώδικα.

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τα namespaces που περιέχουν τις κλάσεις που θα χρησιμοποιήσουμε:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Βήμα 1: Φόρτωση του Έργου

Φορτώστε ένα υπάρχον αρχείο MPP (ή δημιουργήστε νέο) ώστε να έχετε ένα αντικείμενο project για εργασία:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Βήμα 2: Διαμόρφωση Επιλογών Αποθήκευσης

Δημιουργήστε μια παρουσία `PdfSaveOptions` και αρχικοποιήστε τη συλλογή `BarStyles` όπου θα αποθηκεύσουμε τα προσαρμοσμένα στυλ:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Βήμα 3: Ορισμός Στυλ Μπάρας

Τώρα δημιουργούμε ένα αντικείμενο `BarStyle` και ορίζουμε τις ιδιότητες που ελέγχουν την εμφάνιση της μπάρας. Εδώ **προσαρμόζουμε τα χρώματα** και τα σχήματα της μπάρας:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Βήμα 4: Προσαρμογή Μετατροπέα Κειμένου (Προαιρετικό)

Αν θέλετε να τροποποιήσετε το κείμενο που εμφανίζεται στη μπάρα, μπορείτε να ορίσετε έναν προσαρμοσμένο μετατροπέα. Το παράδειγμα προσθέτει πρόθεμα στα ονόματα εργασιών που δεν ξεκινούν ήδη με “T”:

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

## Βήμα 5: Προσθήκη Στυλ Μπάρας στις Επιλογές

Προσθέστε το πλήρως διαμορφωμένο στυλ στη συλλογή `BarStyles` των επιλογών αποθήκευσης:

```csharp
options.BarStyles.Add(style);
```

## Βήμα 6: Αποθήκευση του Έργου

Τέλος, εξάγετε το έργο. Το PDF (ή άλλη μορφή) θα αποδώσει το διάγραμμα Gantt χρησιμοποιώντας το στυλ μπάρας που ορίσαμε:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Το στυλ μπάρας δεν εφαρμόστηκε** | `BarStyles` η συλλογή ήταν κενή ή δεν ήταν συνδεδεμένη με τις επιλογές αποθήκευσης. | Βεβαιωθείτε ότι προσθέτετε το `BarStyle` στο `options.BarStyles` πριν καλέσετε το `Save`. |
| **Τα χρώματα φαίνονται διαφορετικά στο PDF** | Η απόδοση PDF μπορεί να χρησιμοποιεί διαφορετικό προφίλ χρώματος. | Χρησιμοποιήστε τυπικές τιμές `System.Drawing.Color` ή ορίστε προσαρμοσμένα χρώματα ARGB. |
| **Ο μετατροπέας κειμένου προκαλεί σφάλμα null reference** | Η ιδιότητα `Tsk.Name` της εργασίας είναι null για ορισμένες εργασίες. | Προσθέστε έλεγχο null πριν την πρόσβαση στο `task.Get(Tsk.Name)`. |

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να εφαρμόσω πολλαπλά στυλ μπάρας σε ένα μόνο έργο;

A1: Ναι, μπορείτε να ορίσετε και να εφαρμόσετε πολλαπλά στυλ μπάρας σε διαφορετικούς τύπους εργασιών εντός του ίδιου έργου.

### Ε2: Είναι δυνατόν να αλλάζετε δυναμικά τα στυλ μπάρας κατά τη διάρκεια εκτέλεσης;

A2: Ναι, μπορείτε να τροποποιείτε δυναμικά τα στυλ μπάρας βάσει ορισμένων συνθηκών ή προτιμήσεων χρήστη μέσα στην εφαρμογή σας.

### Ε3: Υποστηρίζει το Aspose.Tasks την εξαγωγή έργων με μορφοποιημένες μπάρες σε διαφορετικές μορφές αρχείων;

A3: Ναι, το Aspose.Tasks υποστηρίζει την εξαγωγή έργων με μορφοποιημένες μπάρες σε διάφορες μορφές όπως PDF, XLSX και HTML.

### Ε4: Υπάρχουν προ‑ορισμένα στυλ μπάρας διαθέσιμα στο Aspose.Tasks;

E4: Αν και το Aspose.Tasks παρέχει προεπιλεγμένα στυλ μπάρας, οι προγραμματιστές μπορούν επίσης να δημιουργήσουν προσαρμοσμένα στυλ μπάρας σύμφωνα με τις απαιτήσεις του έργου τους.

### Ε5: Μπορώ να ανακτήσω και να τροποποιήσω υπάρχοντα στυλ μπάρας σε ένα έργο χρησιμοποιώντας το API;

A5: Ναι, μπορείτε να ανακτήσετε και να τροποποιήσετε υπάρχοντα στυλ μπάρας προγραμματιστικά χρησιμοποιώντας το Aspose.Tasks for .NET API.

## Συχνές Ερωτήσεις

**Ε: Πώς αλλάζω το χρώμα μπάρας για κανονικές εργασίες αντί για ορόσημα;**  
A: Ορίστε `style.ItemType = BarItemType.Task;` και αναθέστε `style.BarColor` στο επιθυμητό `Color`.

**Ε: Μπορώ να χρησιμοποιήσω αυτή τη μέθοδο για να μορφοποιήσω μπάρες κατά την εξαγωγή σε HTML;**  
A: Ναι. Χρησιμοποιήστε `HtmlSaveOptions` και γεμίστε τη συλλογή `BarStyles` με τον ίδιο τρόπο.

**Ε: Υπάρχει όριο στον αριθμό των στυλ μπάρας που μπορώ να ορίσω;**  
A: Πρακτικά όχι· μπορείτε να προσθέσετε όσα χρειάζεστε, αλλά λάβετε υπόψη την απόδοση για πολύ μεγάλες συλλογές.

**Ε: Πρέπει να καλέσω `project.Calculate()` μετά την αλλαγή των στυλ;**  
A: Όχι, τα στυλ εφαρμόζονται κατά τη λειτουργία αποθήκευσης· η επανυπολογισμός απαιτείται μόνο για αλλαγές στο χρονοδιάγραμμα.

---

**Τελευταία Ενημέρωση:** 2026-04-06  
**Δοκιμή με:** Aspose.Tasks 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}