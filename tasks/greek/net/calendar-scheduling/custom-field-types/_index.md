---
date: 2026-07-19
description: Μάθετε πώς να προσθέσετε custom field types στο Aspose.Tasks για .NET
  με κώδικα step‑by‑step, prerequisites και FAQs.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Custom Field Types στο Aspose.Tasks
og_description: Μάθετε πώς να προσθέσετε custom field types στο Aspose.Tasks για .NET.
  Ακολουθήστε αυτόν τον οδηγό step‑by‑step για να δημιουργήσετε, ορίσετε και χρησιμοποιήσετε
  extended attributes αποδοτικά.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Πώς να προσθέσετε Custom Field Types στο Aspose.Tasks για .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Πώς να προσθέσετε Custom Field Types στο Aspose.Tasks για .NET
url: /el/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Τύπους Προσαρμοσμένων Πεδίων στο Aspose.Tasks

## Εισαγωγή

Σε αυτό το σεμινάριο θα ανακαλύψετε **πώς να προσθέσετε προσαρμοσμένο πεδίο** σε ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET. Τα προσαρμοσμένα πεδία σας επιτρέπουν να αποθηκεύετε πρόσθετες πληροφορίες—όπως βαθμολογίες κινδύνου, κωδικούς τμημάτων ή προσαρμοσμένες σημειώσεις—απευθείας σε εργασίες, πόρους ή στο ίδιο το έργο. Θα περάσουμε από όλη τη διαδικασία, από τη ρύθμιση του περιβάλλοντος μέχρι τον ορισμό, την προσθήκη και την επαλήθευση ενός προσαρμοσμένου πεδίου κειμένου.

## Γρήγορες Απαντήσεις
- **Τι είναι ένα προσαρμοσμένο πεδίο;** Μια στήλη που ορίζεται από τον χρήστη και μπορεί να περιέχει κείμενο, αριθμούς, ημερομηνίες ή σημαίες σε εργασίες/πόρους.  
- **Ποια κλάση ορίζει ένα προσαρμοσμένο πεδίο;** `ExtendedAttributeDefinition`.  
- **Μπορώ να προσθέσω ένα προσαρμοσμένο πεδίο σε υπάρχον έργο;** Ναι—φορτώστε το έργο, δημιουργήστε τον ορισμό, στη συνέχεια προσθέστε το στη συλλογή.  
- **Χρειάζομαι άδεια για το Aspose.Tasks;** Απαιτείται άδεια για παραγωγική χρήση· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Υποστηριζόμενες εκδόσεις .NET;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι το “πώς να προσθέσετε προσαρμοσμένο πεδίο” στο Aspose.Tasks;

**Πώς να προσθέσετε προσαρμοσμένο πεδίο** αναφέρεται στη διαδικασία δημιουργίας ενός `ExtendedAttributeDefinition` και της προσάρτησής του στη συλλογή `ExtendedAttributes` του έργου. Αυτό σας επιτρέπει να αποθηκεύετε επιπλέον μεταδεδομένα που δεν αποτελούν μέρος του τυπικού σχήματος του Project. Μπορεί να χρησιμοποιηθεί για εργασίες, πόρους ή το ίδιο το έργο, επιτρέποντάς σας να καταγράψετε πληροφορίες όπως επίπεδα κινδύνου, κωδικοί τμημάτων ή προσαρμοσμένες σημειώσεις που δεν είναι διαθέσιμες στα προεπιλεγμένα πεδία.

## Γιατί να χρησιμοποιήσετε προσαρμοσμένα πεδία στη διαχείριση έργων;

Το Aspose.Tasks υποστηρίζει **πάνω από 50 ενσωματωμένους τύπους εκτεταμένων χαρακτηριστικών** και σας επιτρέπει να ορίσετε **οποιονδήποτε αριθμό προσαρμοσμένων πεδίων** χωρίς να επηρεάζει σημαντικά το μέγεθος του αρχείου. Χρησιμοποιώντας προσαρμοσμένα πεδία μπορείτε:  
Αυτά τα πεδία εμφανίζονται ως επιπλέον στήλες στο Microsoft Project και μπορούν να αναφερθούν σε τύπους, αναφορές και φίλτρα. Αποθηκεύονται μέσα στο αρχείο του έργου και το συνοδεύουν, εξασφαλίζοντας ότι οποιαδήποτε επόμενα εργαλεία διατηρούν τα προσαρμοσμένα δεδομένα.

## Προαπαιτούμενα

### 1. Εγκατεστημένο Visual Studio
Βεβαιωθείτε ότι το Visual Studio (2019 ή νεότερο) είναι εγκατεστημένο στον υπολογιστή σας. Μπορείτε να το κατεβάσετε από την ιστοσελίδα της Microsoft.

### 2. Aspose.Tasks για .NET
Προσθέστε το πακέτο NuGet Aspose.Tasks στο έργο σας. Κατεβάστε την πιο πρόσφατη έκδοση από [εδώ](https://releases.aspose.com/tasks/net/).

### 3. Βασικές Γνώσεις C#
Θα πρέπει να είστε άνετοι με τη σύνταξη C#, τις κλάσεις και τη δομή έργου .NET.

## Εισαγωγή Χώρων Ονομάτων

Τα `Project`, `ExtendedAttributeDefinition` και τα σχετιζόμενα enums βρίσκονται στον χώρο ονομάτων `Aspose.Tasks`. Εισάγετέ το στην αρχή του αρχείου σας:

Ο χώρος ονομάτων `Aspose.Tasks` παρέχει όλους τους βασικούς τύπους για τη διαχείριση αρχείων Microsoft Project.

```csharp

```

## Πώς να προσθέσετε προσαρμοσμένο πεδίο σε ένα έργο;

Φορτώστε το υπάρχον έργο, δημιουργήστε έναν ορισμό προσαρμοσμένου πεδίου και προσθέστε το στη συλλογή εκτεταμένων χαρακτηριστικών του έργου—όλα σε τρία σύντομα βήματα. Αυτό το πρότυπο λειτουργεί για εργασίες, πόρους και το ίδιο το έργο, και εξασφαλίζει ότι το προσαρμοσμένο πεδίο αποθηκεύεται όταν αποθηκεύετε το αρχείο.

### Βήμα 1: Δημιουργία Αντικειμένου Project
`Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα μοναδικό αρχείο Project στη μνήμη. Η δημιουργία του φορτώνει το αρχείο και σας δίνει πρόσβαση σε εργασίες, πόρους και εκτεταμένα χαρακτηριστικά.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Βήμα 2: Ορισμός Προσαρμοσμένου Πεδίου
`ExtendedAttributeDefinition` περιγράφει μια νέα στήλη. Σε αυτό το παράδειγμα δημιουργούμε ένα προσαρμοσμένο πεδίο τύπου **Text** για εργασίες και του δίνουμε το ψευδώνυμο “MyText”. Η τιμή enum `ExtendedAttributeTask.Text1` λέει στο Aspose.Tasks πού να αποθηκεύσει την τιμή.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Βήμα 3: Προσθήκη Ορισμού Προσαρμοσμένου Πεδίου στο Project
Η συλλογή `ExtendedAttributes` του έργου περιέχει όλους τους ορισμούς προσαρμοσμένων πεδίων. Η προσθήκη του ορισμού το καθιστά διαθέσιμο για κάθε εργασία στο έργο.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Συχνά Προβλήματα και Λύσεις
- **Το πεδίο δεν εμφανίζεται στη διεπαφή χρήστη του MS Project** – Βεβαιωθείτε ότι έχετε ορίσει την ιδιότητα `Alias`; το MS Project εμφανίζει το ψευδώνυμο ως επικεφαλίδα στήλης.  
- **Η αποθήκευση προκαλεί εξαίρεση** – Επαληθεύστε ότι το αρχείο του έργου δεν είναι μόνο για ανάγνωση και ότι έχετε έγκυρη άδεια.  
- **Οι τιμές του προσαρμοσμένου πεδίου χάνονται μετά την επαναφόρτωση** – Βεβαιωθείτε ότι καλείτε `project.Save("output.mpp")` μετά την ανάθεση τιμών στις εργασίες.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλα .NET frameworks;**  
A: Ναι, το Aspose.Tasks λειτουργεί με .NET Framework, .NET Core και .NET 5/6/7.

**Q: Είναι το Aspose.Tasks κατάλληλο για εφαρμογές επιπέδου επιχείρησης;**  
A: Απόλυτα. Υποστηρίζει την επεξεργασία έργων με **μέχρι 10.000 εργασίες** και μπορεί να λειτουργήσει σε πολυνηματικά περιβάλλοντα διακομιστών.

**Q: Υποστηρίζει το Aspose.Tasks πολλαπλές μορφές αρχείων έργου;**  
A: Ναι—το Aspose.Tasks διαβάζει και γράφει μορφές MPP, XML, HTML και CSV, καλύπτοντας **όλες τις κύριες εκδόσεις του Microsoft Project**.

**Q: Μπορώ να διαχειριστώ δεδομένα πόρων χρησιμοποιώντας το Aspose.Tasks;**  
A: Ναι, μπορείτε να προσθέσετε, να ενημερώσετε και να διαγράψετε πόρους, καθώς και να εκχωρήσετε προσαρμοσμένα πεδία σε αυτούς.

**Q: Υπάρχει φόρουμ κοινότητας για χρήστες του Aspose.Tasks;**  
A: Ναι, μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για να αλληλεπιδράσετε με άλλους χρήστες και να λάβετε υποστήριξη από την ομάδα της Aspose.

---

**Τελευταία Ενημέρωση:** 2026-07-19  
**Δοκιμασμένο με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Κατακτήστε τους Ορισμούς Εκτεταμένων Χαρακτηριστικών MS Project στο Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Διαχείριση Εκτεταμένων Χαρακτηριστικών MS Project με Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Βοηθός Πεδίου Ενσωμάτωση MS Project στο Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}