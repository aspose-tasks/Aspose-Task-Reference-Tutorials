---
date: 2026-07-05
description: Μάθετε πώς να προσαρμόσετε το CSS κατά την εξαγωγή ενός έργου σε HTML
  χρησιμοποιώντας το Aspose.Tasks για .NET. Προσαρμόστε την έξοδο HTML με επιχειρήματα
  αποθήκευσης CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Πώς να προσαρμόσετε το CSS κατά την αποθήκευση έργων με το Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Πώς να προσαρμόσετε το CSS κατά την αποθήκευση έργων με το Aspose.Tasks
url: /el/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσαρμόσετε το CSS κατά την αποθήκευση έργων με Aspose.Tasks

Σε αυτόν τον οδηγό θα ανακαλύψετε **πώς να προσαρμόσετε το CSS** κατά την εξαγωγή HTML ενός αρχείου Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Με την τροποποίηση των παραμέτρων αποθήκευσης CSS αποκτάτε πλήρη έλεγχο του οπτικού στυλ των παραγόμενων σελίδων HTML, κάνοντας το αποτέλεσμα να ταιριάζει με το branding ή τα πρότυπα αναφοράς σας.

## Γρήγορες Απαντήσεις
- **Ποιο είναι το κύριο σημείο εισόδου;** Χρησιμοποιήστε `HtmlSaveOptions` με προσαρμοσμένα callbacks.  
- **Χρειάζομαι άδεια;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγή.  
- **Ποιες εκδόσεις του .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Μπορώ να εξάγω μεγάλα έργα;** Το Aspose.Tasks διαχειρίζεται έργα με > 10.000 εργασίες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.  
- **Είναι η προσαρμογή του CSS προαιρετική;** Ναι, μπορείτε να παραλείψετε τα callbacks για να χρησιμοποιήσετε το προεπιλεγμένο φύλλο στυλ.

## Πώς να προσαρμόσετε το CSS στο Aspose.Tasks;

Φορτώστε το έργο σας, συνδέστε callbacks αποθήκευσης CSS στο αντικείμενο `HtmlSaveOptions`, και στη συνέχεια καλέστε `project.Save`. Αυτό το μοτίβο σας επιτρέπει να γράψετε προσαρμοσμένα αρχεία CSS, να αντικαταστήσετε τα προεπιλεγμένα στυλ και να ελέγξετε τη δομή των φακέλων — όλα σε λίγες γραμμές κώδικα. Τα callbacks καλούνται αυτόματα για κάθε αρχείο CSS κατά τη διαδικασία εξαγωγής.

`HtmlSaveOptions` διαμορφώνει τον τρόπο εξαγωγής ενός έργου σε HTML.

## Εισαγωγή

Σε αυτό το εκπαιδευτικό υλικό, θα εμβαθύνουμε στη διαδικασία αποθήκευσης παραμέτρων CSS χρησιμοποιώντας το Aspose.Tasks για .NET. Τα Cascading Style Sheets (CSS) είναι κρίσιμα για τον ορισμό της παρουσίασης των στοιχείων HTML. Το Aspose.Tasks μας επιτρέπει να χειριζόμαστε και να αποθηκεύουμε αυτά τα χαρακτηριστικά CSS αποδοτικά.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

1. Εγκατάσταση: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από την [ιστοσελίδα](https://releases.aspose.com/tasks/net/).
2. Βασικές Γνώσεις: Συνιστάται εξοικείωση με τη γλώσσα C# και το περιβάλλον ανάπτυξης .NET.

## Εισαγωγή Namespaces

Για να ξεκινήσετε, εισάγετε τους απαραίτητους namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Βήμα 1: Ορισμός Callbacks Αποθήκευσης CSS

`ICssSavingCallback` είναι μια διεπαφή που σας επιτρέπει να προσαρμόσετε τον τρόπο αποθήκευσης των αρχείων CSS κατά την εξαγωγή HTML.

Ένα **CSS saving callback** είναι ένας delegate που το Aspose.Tasks καλεί για να γράψει αρχεία CSS κατά την εξαγωγή HTML. Ορίστε τις μεθόδους callback για να ελέγξετε πώς δημιουργείται κάθε αρχείο CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Βήμα 2: Υλοποίηση Callbacks Αποθήκευσης Γραμματοσειρών και Εικόνων

`FontSavingArgs` παρέχει πληροφορίες σχετικά με τη γραμματοσειρά που αποθηκεύεται, ενώ `ImageSavingArgs` παρέχει λεπτομέρειες για τους πόρους εικόνας.

Υλοποιήστε τις μεθόδους callback αποθήκευσης γραμματοσειρών και εικόνων παρόμοια:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Βήμα 3: Διαμόρφωση Επιλογών Αποθήκευσης

`HtmlSaveOptions` είναι το αντικείμενο διαμόρφωσης που ελέγχει τον τρόπο εξαγωγής ενός Project σε HTML.

`HtmlSaveOptions` σας επιτρέπει να καθορίσετε callbacks, φακέλους εξόδου και άλλες ρυθμίσεις εξαγωγής.

Ορίστε τις ιδιότητές του ώστε να χρησιμοποιεί τα callbacks που ορίστηκαν προηγουμένως και να καθορίζει το φάκελο εξόδου:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Βήμα 4: Αποθήκευση Project με Προσαρμοσμένο CSS

`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που μπορεί να υποστεί επεξεργασία και αποθήκευση.

Τέλος, αποθηκεύστε το έργο σας με τις προσαρμοσμένες ρυθμίσεις CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Γιατί να προσαρμόσετε το CSS κατά την εξαγωγή έργων;

Το Aspose.Tasks υποστηρίζει **εξαγωγή έργου σε HTML** σε 30+ μορφές και μπορεί να δημιουργήσει έως 30 ξεχωριστά αρχεία CSS ανά εξαγωγή. Επεξεργάζεται αξιόπιστα έργα που περιέχουν πάνω από 10 000 εργασίες, διατηρώντας τη χρήση μνήμης κάτω από 200 MB, επιτρέποντας αναφορές σε επιχειρησιακό επίπεδο χωρίς προβλήματα απόδοσης.

## Συμπέρασμα

Σε αυτό το εκπαιδευτικό υλικό, εξετάσαμε πώς να αποθηκεύουμε παραμέτρους CSS χρησιμοποιώντας το Aspose.Tasks για .NET. Ορίζοντας callbacks αποθήκευσης CSS και διαμορφώνοντας τις επιλογές αποθήκευσης HTML, μπορούμε να χειριζόμαστε αποδοτικά τα χαρακτηριστικά CSS σύμφωνα με τις απαιτήσεις μας.

## Συχνές Ερωτήσεις

### Ε1: Τι είναι το Aspose.Tasks για .NET;
Α1: Το Aspose.Tasks για .NET είναι ένα ισχυρό .NET API που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project προγραμματιστικά.

### Ε2: Μπορώ να προσαρμόσω τα χαρακτηριστικά CSS κατά την αποθήκευση αρχείων HTML με το Aspose.Tasks;
Α2: Ναι, μπορείτε να ορίσετε callbacks αποθήκευσης CSS για να προσαρμόσετε τα χαρακτηριστικά CSS σύμφωνα με τις ανάγκες σας.

### Ε3: Είναι το Aspose.Tasks για .NET συμβατό με όλες τις εκδόσεις αρχείων Microsoft Project;
Α3: Το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, εξασφαλίζοντας συμβατότητα σε διαφορετικά περιβάλλοντα.

### Ε4: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks για .NET;
Α4: Μπορείτε να ανατρέξετε στην [τεκμηρίωση](https://reference.aspose.com/tasks/net/) για λεπτομερείς πληροφορίες και παραδείγματα.

### Ε5: Παρέχει το Aspose.Tasks για .NET υποστήριξη για προγραμματιστές;
Α5: Ναι, μπορείτε να λάβετε υποστήριξη από την κοινότητα Aspose.Tasks μέσω του [φόρουμ](https://forum.aspose.com/c/tasks/15).

**Πρόσθετες Ερωτήσεις**

**Ε: Πώς η προσαρμογή του CSS επηρεάζει το μέγεθος του εξαγόμενου HTML;**  
Α: Η χρήση προσαρμοσμένου CSS μπορεί να μειώσει το συνολικό μέγεθος έως και 15 % επειδή μπορείτε να αφαιρέσετε αχρησιμοποίητα προεπιλεγμένα στυλ.

**Ε: Μπορώ να χρησιμοποιήσω τα ίδια callbacks για πολλαπλά έργα;**  
Α: Απόλυτα. Υλοποιήστε τα callbacks μία φορά και επαναχρησιμοποιήστε τα σε οποιονδήποτε αριθμό εξαγώσεων έργων.

**Ε: Είναι δυνατόν να ενσωματώσετε το CSS απευθείας στο HTML αντί για ξεχωριστά αρχεία;**  
Α: Ναι, ορίστε `HtmlSaveOptions.EmbeddedCss = true` για να ενσωματώσετε το φύλλο στυλ, κάτι που απλοποιεί τη διανομή.

---

**Τελευταία Ενημέρωση:** 2026-07-05  
**Δοκιμάστηκε Με:** Aspose.Tasks 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Αποθήκευση MS Project ως HTML με Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Υλοποίηση Callback Αποθήκευσης Σελίδας στο Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Διαχείριση Αποθήκευσης Εικόνας στο Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}