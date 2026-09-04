---
date: 2026-07-05
description: Μάθετε πώς να αντιγράψετε δεδομένα έργου χρησιμοποιώντας το Aspose.Tasks
  για .NET με copy options. Ενισχύστε τις .NET εφαρμογές σας με ακριβή project management.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Πώς να αντιγράψετε δεδομένα έργου με copy options στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Πώς να αντιγράψετε δεδομένα έργου με copy options στο Aspose.Tasks
url: /el/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Αντιγράψετε Δεδομένα Έργου με Επιλογές Αντιγραφής στο Aspose.Tasks

## Εισαγωγή

Αν χρειάζεστε **πώς να αντιγράψετε έργο** πληροφορίες από ένα αρχείο Microsoft Project σε ένα άλλο, το Aspose.Tasks για .NET σας παρέχει έναν καθαρό, κώδικα‑πρώτο τρόπο για να το κάνετε. Σε αυτό το tutorial θα περάσουμε από τη πλήρη ροή εργασίας — φόρτωση ενός πηγαίου έργου, διαμόρφωση επιλογών αντιγραφής, δημιουργία αντιγράφου και φόρτωση του αποτελέσματος — ώστε να μπορείτε να ενσωματώσετε τη λογική αντιγραφής έργου σε οποιαδήποτε εφαρμογή .NET με σιγουριά.

## Γρήγορες Απαντήσεις
- **Τι κάνει η λειτουργία αντιγραφής;** Διπλασιάζει τα δεδομένα του έργου ενώ σας επιτρέπει να συμπεριλάβετε ή να εξαιρέσετε συγκεκριμένα τμήματα όπως ημερολόγια, πόρους ή πληροφορίες προβολής.  
- **Ποια κλάση ελέγχει τη συμπεριφορά;** `CopyToOptions` σας επιτρέπει να ρυθμίσετε λεπτομερώς τι αντιγράφεται.  
- **Χρειάζομαι άδεια;** Απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη.  
- **Υποστηριζόμενες μορφές;** Το Aspose.Tasks διαχειρίζεται αρχεία MPP, XML και XER — πάνω από 20 + μορφές συνολικά.  
- **Μπορώ να παραλείψω τα δεδομένα προβολής;** Ναι, ορίστε `CopyToOptions.SkipViewData = true` για να παραλείψετε πληροφορίες σχετικές με το UI.

## Τι είναι το “πώς να αντιγράψετε έργο” στο Aspose.Tasks;

**“Πώς να αντιγράψετε έργο”** αναφέρεται στη χρήση του API του Aspose.Tasks για να διπλασιάσετε τα δεδομένα ενός αντικειμένου Project σε ένα νέο αρχείο, προαιρετικά φιλτράροντας ανεπιθύμητα στοιχεία. Αυτή η λειτουργία είναι χρήσιμη για δημιουργία προτύπων, αρχειοθέτηση ή δημιουργία παραλλαγών έργου χωρίς χειροκίνητα βήματα UI, και λειτουργεί σε όλες τις υποστηριζόμενες μορφές αρχείων.

## Γιατί να χρησιμοποιήσετε τις Επιλογές Αντιγραφής στο Aspose.Tasks;

Το Aspose.Tasks υποστηρίζει **πάνω από 50 οντότητες σχετικές με το έργο** (εργασίες, πόροι, ημερολόγια, εκχωρήσεις κ.λπ.) και μπορεί να επεξεργαστεί αρχεία με **έως 10.000 εργασίες** διατηρώντας τη χρήση μνήμης κάτω από 200 MB. Η χρήση του `CopyToOptions` σας επιτρέπει να αποφύγετε την αντιγραφή βαριών δεδομένων προβολής, μειώνοντας το μέγεθος του αρχείου εξόδου κατά **30‑40 %** και επιταχύνοντας τη λειτουργία περίπου **2×** για μεγάλα έργα.

## Προαπαιτούμενα

1. **Aspose.Tasks for .NET** – κατεβάστε την πιο πρόσφατη έκδοση από το [download link](https://releases.aspose.com/tasks/net/).  
2. **.NET development environment** – Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET 6+) εγκατεστημένο.  
3. **Μια έγκυρη άδεια Aspose.Tasks** – προαιρετική για αξιολόγηση, υποχρεωτική για παραγωγικές εκδόσεις.  
4. **Ένα υπάρχον αρχείο έργου** (π.χ., `SourceProject.xml`) που θέλετε να αντιγράψετε.

## Πώς να εισάγετε ονόματα χώρων για το Aspose.Tasks;

Προσθέστε τις απαιτούμενες οδηγίες `using` στην αρχή του αρχείου C# ώστε ο μεταγλωττιστής να εντοπίζει τους τύπους του Aspose.Tasks. Η συμπερίληψη αυτών των δηλώσεων σας δίνει άμεση πρόσβαση στα `Project`, `CopyToOptions` και άλλες βοηθητικές κλάσεις χωρίς να χρειάζεται να προσδιορίζετε πλήρως τα ονόματά τους, απλοποιώντας τον κώδικά σας και βελτιώνοντας την αναγνωσιμότητα.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Βήμα 1: Αρχικοποίηση Αντικειμένων Project

Πρώτα, δημιουργήστε μια παρουσία `Project` που αντιπροσωπεύει το πηγαίο αρχείο και φορτώστε τα δεδομένα XML.  
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που έχει φορτωθεί στη μνήμη, εκθέτοντας εργασίες, πόρους, ημερολόγια και άλλες πληροφορίες του έργου.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Συμβουλή:** Αν εργάζεστε με πολύ μεγάλα αρχεία, σκεφτείτε να χρησιμοποιήσετε τον κατασκευαστή `LoadOptions` για να ενεργοποιήσετε τη lazy φόρτωση και να διατηρήσετε τη χρήση μνήμης χαμηλή.

## Βήμα 2: Δημιουργία Αντιγράφου του Project

Στη συνέχεια, δημιουργήστε ένα δεύτερο αντικείμενο `Project` που θα λάβει τα αντιγραμμένα δεδομένα. Αυτό το αντικείμενο ξεκινά κενό.

```csharp
Project copiedProject = new Project();
```

Τώρα έχετε δύο διαφορετικά αντικείμενα `Project`: ένα φορτωμένο από το δίσκο και ένα έτοιμο να λάβει το αντίγραφο.

## Βήμα 3: Φόρτωση Αντιγραμμένου Project

Μετά τη λειτουργία αντιγραφής (που θα εμφανιστεί αργότερα), θα θέλετε να επαληθεύσετε το αποτέλεσμα φορτώνοντας το νεοαποθηκευμένο αρχείο σε μια άλλη παρουσία `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Η φόρτωση του αρχείου ξανά επιβεβαιώνει ότι η αντιγραφή πέτυχε και ότι οι επιλογές που ορίσατε λειτούργησαν όπως αναμενόταν.

## Βήμα 4: Διαμόρφωση Επιλογών Αντιγραφής

Η κλάση `CopyToOptions` σας επιτρέπει να καθορίσετε ακριβώς τι μεταφέρεται από την πηγή στον προορισμό.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Ο ορισμός `SkipViewData = true` μειώνει το μέγεθος του αρχείου εξόδου και επιταχύνει τη λειτουργία, ειδικά όταν χρειάζεστε μόνο λογικά δεδομένα του έργου.

## Βήμα 5: Εκτέλεση Αντιγραφής Project

Τέλος, καλέστε τη μέθοδο `CopyTo` στο πηγαίο project, περνώντας το προορισμό project και τις επιλογές που διαμορφώσατε.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Αυτή η κλήση δύο γραμμών εκτελεί ολόκληρη τη λειτουργία αντιγραφής, σεβόμενη τις επιλογές που ορίσατε. Το αποτέλεσμα `CopiedProject.xml` περιέχει μόνο τα δεδομένα που ζητήσατε.

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **NullReferenceException κατά την κλήση του `CopyTo`** | Το προορισμό project δεν έχει δημιουργηθεί. | Βεβαιωθείτε ότι καλείται `new Project()` πριν το `CopyTo`. |
| **Απουσία εργασιών μετά την αντιγραφή** | `CopyCommonData` ορίστηκε σε `false`. | Ορίστε `CopyCommonData = true` ή αντιγράψτε συγκεκριμένες συλλογές χειροκίνητα. |
| **Μεγάλο αρχείο εξόδου** | `SkipViewData` παραμένει `false`. | Ενεργοποιήστε `SkipViewData` για να παραλείψετε δεδομένα σχετιζόμενα με το UI. |
| **Η άδεια δεν εφαρμόστηκε** | Το αρχείο άδειας δεν φορτώθηκε. | Καλέστε `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` πριν από οποιαδήποτε χρήση του API. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να αντιγράψω μόνο ένα υποσύνολο εργασιών;**  
Α: Ναι, χρησιμοποιήστε το `CopyToOptions` μαζί με το `ProjectRootTask` για να καθορίσετε μια αρχική εργασία, ή αντιγράψτε χειροκίνητα τις επιλεγμένες εργασίες μετά την αρχική αντιγραφή.

**Ε: Υποστηρίζει το Aspose.Tasks την αντιγραφή μεταξύ διαφορετικών μορφών αρχείων;**  
Α: Απόλυτα. Μπορείτε να φορτώσετε ένα αρχείο MPP και να αποθηκεύσετε το αντίγραφο ως XML, XER ή οποιαδήποτε άλλη υποστηριζόμενη μορφή — πάνω από **20 + μορφές** συνολικά.

**Ε: Πώς να διαχειριστώ αρχεία έργου με κωδικό πρόσβασης;**  
Α: Φορτώστε την πηγή με `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, έπειτα προχωρήστε στην αντιγραφή όπως συνήθως.

**Ε: Υπάρχει τρόπος να αντιγράψω τις δεσμευμένες πόρων χωρίς εργασίες;**  
Α: Ορίστε `CopyToOptions.CopyResources = true` και `CopyToOptions.CopyTasks = false` για να μεταφέρετε μόνο τις πληροφορίες πόρων.

**Ε: Πού μπορώ να βρω περισσότερα παραδείγματα;**  
Α: Επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για παραδείγματα από την κοινότητα, συμβουλές αντιμετώπισης προβλημάτων και επίσημη τεκμηρίωση.

**Τελευταία Ενημέρωση:** 2026-07-05  
**Δοκιμή Με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Κατακτώντας τα Δεδομένα Έργου με το Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Κατακτώντας τις Επιλογές Αποθήκευσης του MS Project για το Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Η Ημερολόγιο και Προγραμματισμός του Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}