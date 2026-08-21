---
date: 2026-03-16
description: Μάθετε πώς να υλοποιήσετε την κλήση επιστροφής αποθήκευσης σελίδας στο
  Aspose.Tasks για .NET, επιτρέποντας προσαρμοσμένη διαχείριση των ροών εξόδου εγγράφων
  πολλαπλών σελίδων.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Υλοποίηση κλήσης επιστροφής αποθήκευσης σελίδας στο Aspose.Tasks
url: /el/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Υλοποίηση της κλήσης αποθήκευσης σελίδας στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το tutorial, θα μάθετε πώς να **υλοποιήσετε την κλήση αποθήκευσης σελίδας** στο Aspose.Tasks για .NET. Αυτή η ισχυρή δυνατότητα σας επιτρέπει να κατευθύνετε κάθε σελίδα ενός πολυ‑σελίδων εγγράφου σε ένα stream της επιλογής σας, δίνοντάς σας πλήρη έλεγχο πάνω στο πώς αποθηκεύεται ή επεξεργάζεται περαιτέρω το αποτέλεσμα.

## Γρήγορες Απαντήσεις
- **Τι κάνει η κλήση αποθήκευσης σελίδας;** Καταγράφει κάθε αποδοθείσα σελίδα σε ξεχωριστό stream ώστε να μπορείτε να τις διαχειριστείτε ξεχωριστά.  
- **Σε ποια μορφή μπορώ να εξάγω;** Σε οποιαδήποτε μορφή υποστηρίζεται από `ImageSaveOptions`, π.χ., PNG, JPEG, PDF.  
- **Χρειάζομαι άδεια;** Απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγική χρήση.  
- **Μπορώ να το χρησιμοποιήσω με .NET Core;** Ναι, το Aspose.Tasks υποστηρίζει πλήρως .NET Core και .NET 5/6+.  
- **Είναι η κλήση thread‑safe;** Η κλήση εκτελείται στο ίδιο νήμα που πραγματοποιεί το rendering, οπότε ισχύουν οι κανονικοί κανόνες thread‑safety.

## Τι είναι η **υλοποίηση της κλήσης αποθήκευσης σελίδας**;
Το πρότυπο **υλοποίηση της κλήσης αποθήκευσης σελίδας** σας επιτρέπει να ενσωματώσετε προσαρμοσμένη λογική στην αλυσίδα αποθήκευσης του Aspose.Tasks. Αντί να γράφετε απευθείας σε αρχείο, λαμβάνετε ένα αντικείμενο `Stream` για κάθε σελίδα, επιτρέποντάς σας να το αποθηκεύσετε στη μνήμη, να το ανεβάσετε σε cloud storage ή να εφαρμόσετε πρόσθετη επεξεργασία.

## Γιατί να εξάγετε το έργο ως PNG με κλήση;
Η εξαγωγή ενός έργου ως PNG παρέχει μια raster εικόνα κάθε σελίδας του διαγράμματος Gantt, η οποία είναι ιδανική για αναφορές, email ή ενσωμάτωση σε ιστοσελίδες. Η χρήση κλήσης σημαίνει ότι μπορείτε να κρατήσετε κάθε σελίδα σε ξεχωριστό `MemoryStream` χωρίς να δημιουργείτε προσωρινά αρχεία στο δίσκο.

## Προαπαιτούμενα

1. **Γνώση C#** – βασική εξοικείωση με κλάσεις, interfaces και streams.  
2. **Aspose.Tasks for .NET** – κατεβάστε και εγκαταστήστε από [εδώ](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider ή οποιονδήποτε επεξεργαστή συμβατό με .NET.

## Εισαγωγή Namespaces

Για να ξεκινήσετε, εισάγετε τα απαιτούμενα namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Βήμα 1: Δημιουργία αντικειμένου Project

Φορτώστε ένα υπάρχον αρχείο MPP σε μια παρουσία `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Βήμα 2: Διαμόρφωση Image Save Options

Ρυθμίστε το `ImageSaveOptions` για έξοδο PNG και συνδέστε την προσαρμοσμένη κλήση:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Συμβουλή:** Ορίζοντας `RenderToSinglePage = false` εξασφαλίζει ότι κάθε σελίδα του διαγράμματος Gantt αποδίδεται ξεχωριστά, κάτι που είναι απαραίτητο ώστε η κλήση να λαμβάνει διακριτά streams.

## Βήμα 3: Αποθήκευση Project με κλήση

Κληθείτε τη μέθοδο `Save`, περνώντας `Stream.Null` επειδή τα πραγματικά streams παρέχονται από την κλήση:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Βήμα 4: Επεξεργασία των αποθηκευμένων streams σελίδων

Αφού ολοκληρωθεί η λειτουργία αποθήκευσης, η κλήση διατηρεί μια συλλογή αντικειμένων `MemoryStream`—ένα ανά σελίδα. Μπορείτε τώρα να τα διατρέξετε:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Βήμα 5: Υλοποίηση προσαρμοσμένης κλήσης αποθήκευσης σελίδας

Δημιουργήστε μια sealed κλάση που υλοποιεί το `IPageSavingCallback`. Αυτή η κλάση καταγράφει το stream κάθε σελίδας και το αποθηκεύει σε λίστα για μετέπειτα χρήση.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Συνηθισμένα προβλήματα & Αντιμετώπιση

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Δεν επιστρέχονται σελίδες** | `RenderToSinglePage` παραμένει `true`. | Ορίστε `RenderToSinglePage = false` για να δημιουργηθούν ξεχωριστές σελίδες. |
| **Τα streams είναι κενά** | `KeepStreamOpen` ορίστηκε σε `true` χωρίς να διαγραφούν αργότερα. | Διατηρήστε το `false` (προεπιλογή) και αφήστε την κλήση να κλείσει αυτόματα τα streams. |
| **Σφάλματα out‑of‑memory** | Πολύ μεγάλα έργα παράγουν πολλές υψηλής ανάλυσης PNG. | Επεξεργαστείτε τα streams ένα‑ένα ή αυξήστε τα όρια μνήμης της VM. |

## Συχνές Ερωτήσεις

**Q1: Τι είναι μια κλήση αποθήκευσης σελίδας στο Aspose.Tasks;**  
A: Μια κλήση αποθήκευσης σελίδας σας επιτρέπει να παρεμβείτε στη διαδικασία αποθήκευσης για κάθε σελίδα ενός πολυ‑σελίδων εγγράφου, παρέχοντας ένα προσαρμοσμένο `Stream` για εκείνη τη σελίδα.

**Q2: Μπορώ να χρησιμοποιήσω διαφορετικές μορφές για την αποθήκευση σελίδων χρησιμοποιώντας αυτήν την κλήση;**  
A: Ναι. Αλλάζοντας το `SaveFileFormat` μπορείτε να εξάγετε σε PNG, JPEG, PDF, SVG κ.ά.

**Q3: Είναι το Aspose.Tasks συμβατό με .NET Core;**  
A: Απόλυτα. Το Aspose.Tasks υποστηρίζει .NET Core, .NET 5 και .NET 6.

**Q4: Πώς μπορώ να διαχειριστώ σφάλματα κατά τη διαδικασία αποθήκευσης σελίδας;**  
A: Τυλίξτε τη λογική της κλήσης σε try/catch μπλοκ και καταγράψτε τις εξαιρέσεις. Η μέθοδος `OnFinish` είναι καλό σημείο για τελική εκκαθάριση.

**Q5: Πού μπορώ να βρω περισσότερους πόρους και υποστήριξη για το Aspose.Tasks;**  
A: Μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για βοήθεια, να αποκτήσετε πρόσβαση στην τεκμηρίωση [εδώ](https://reference.aspose.com/tasks/net/), ή να εξερευνήσετε πρόσθετες δυνατότητες και επιλογές αδειοδότησης στην ιστοσελίδα [Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Τελευταία ενημέρωση:** 2026-03-16  
**Δοκιμάστηκε με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}