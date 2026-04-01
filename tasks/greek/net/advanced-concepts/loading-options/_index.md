---
date: 2026-03-08
description: Μάθετε πώς να εισάγετε αρχείο έργου χρησιμοποιώντας το Aspose.Tasks για
  .NET, συμπεριλαμβανομένου του πώς να καθορίσετε την κωδικοποίηση του αρχείου και
  να φορτώσετε αποδοτικά το αρχείο Microsoft Project.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Εισαγωγή αρχείου έργου – Επιλογές φόρτωσης στο Aspose.Tasks
url: /el/net/advanced-concepts/loading-options/
weight: 16
---

.

Make sure we keep markdown formatting: headings, bold, lists, code block placeholders.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εισαγωγή Αρχείου Έργου – Επιλογές Φόρτωσης στο Aspose.Tasks

## Εισαγωγή

Το Aspose.Tasks for .NET καθιστά εύκολη την **import project file** δεδομένων από Microsoft Project, Primavera και άλλες μορφές. Είτε χρειάζεστε να διαβάσετε ένα αρχείο προστατευμένο με κωδικό, να ορίσετε προσαρμοσμένη κωδικοποίηση ή να διαχειριστείτε σφάλματα ανάλυσης, η βιβλιοθήκη σας παρέχει λεπτομερή έλεγχο μέσω των επιλογών φόρτωσης. Σε αυτό το tutorial θα περάσουμε από τα πιο συνηθισμένα σενάρια ώστε να μπορείτε με σιγουριά **load Microsoft Project file** αντικείμενα στις .NET εφαρμογές σας.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος τρόπος για την εισαγωγή ενός αρχείου έργου;** Χρησιμοποιήστε τον κατασκευαστή `Project` με μια παρουσία `LoadOptions`.  
- **Μπορώ να ανοίξω αρχεία προστατευμένα με κωδικό;** Ναι—ορίστε την ιδιότητα `Password` στο `LoadOptions`.  
- **Πώς καθορίζω την κωδικοποίηση του αρχείου;** Αναθέστε ένα αντικείμενο `Encoding` στο `LoadOptions.Encoding`.  
- **Μπορεί η διαχείριση σφαλμάτων να προσαρμοστεί;** Απόλυτα—παρέχετε έναν delegate στο `LoadOptions.ErrorHandler`.  
- **Λειτουργούν αυτές οι επιλογές με αρχεία Primavera;** Ναι, μέσω του `PrimaveraReadOptions` μέσα στο `LoadOptions`.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Visual Studio** (ή οποιοδήποτε προτιμώμενο .NET IDE).  
2. **Aspose.Tasks for .NET** – κατεβάστε το από την [website](https://releases.aspose.com/tasks/net/).  
3. Μια βασική κατανόηση της σύνταξης **C#** και της δομής του έργου.

Τώρα που είμαστε έτοιμοι, ας εισάγουμε τα απαιτούμενα namespaces.

## Εισαγωγή Namespaces

Στο C# έργο σας, προσθέστε τις παρακάτω δηλώσεις `using` ώστε οι κλάσεις του API να είναι διαθέσιμες:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Πώς να Εισάγετε Αρχείο Έργου με Επιλογές Φόρτωσης

Παρακάτω υπάρχουν τέσσερα πρακτικά παραδείγματα που καλύπτουν τα πιο συχνά σενάρια φόρτωσης.

### Βήμα 1: Φόρτωση Έργου Προστατευμένου με Κωδικό

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Βήμα 2: Φόρτωση Έργου Primavera με Προσαρμοσμένες Επιλογές

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Βήμα 3: **Specify File Encoding** Κατά την Εισαγωγή Αρχείου XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Βήμα 4: Φόρτωση Έργου Primavera με Προσαρμοσμένη Διαχείριση Σφαλμάτων

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Ακολουθώντας αυτά τα βήματα μπορείτε με ακρίβεια να **import project file** δεδομένα, να προσαρμόσετε τη διαδικασία φόρτωσης στις ανάγκες σας και να διατηρήσετε την εφαρμογή σας ανθεκτική.

## Συνηθισμένα Προβλήματα & Συμβουλές

- **Λάθος κωδικός** – η ιδιότητα `Password` θα ρίξει εξαίρεση· επαληθεύστε τα διαπιστευτήρια πριν τη φόρτωση.  
- **Μη υποστηριζόμενη κωδικοποίηση** – βεβαιωθείτε ότι η κωδικοσελίδα που ορίζετε υπάρχει στο στόχο μηχάνημα (`Encoding.GetEncoding(1251)` λειτουργεί για Κυριλλικά).  
- **Απουσία επιλογών Primavera** – εάν χρειάζεται να διατηρήσετε τα UID των εργασιών, ορίστε `PreserveUids = true`; διαφορετικά μπορεί να εμφανιστούν διπλότυπα IDs.  
- **Ο διαχειριστής σφαλμάτων επιστρέφει null** – η επιστροφή `null` υποδεικνύει στον parser να παραλείψει το προβληματικό στοιχείο· προσαρμόστε το όπως απαιτείται.

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.Tasks for .NET συμβατό με όλες τις εκδόσεις του Microsoft Project;**  
A: Ναι, υποστηρίζει ένα ευρύ φάσμα εκδόσεων του Microsoft Project, έτσι ώστε να μπορείτε να **load Microsoft Project file** μορφές από παλαιότερα αρχεία MPP μέχρι τις πιο πρόσφατες μορφές.

**Q: Μπορώ να ενσωματώσω το Aspose.Tasks for .NET με άλλες βιβλιοθήκες τρίτων;**  
A: Απόλυτα. Η βιβλιοθήκη λειτουργεί άψογα με άλλα πακέτα .NET, επιτρέποντάς σας να τη συνδυάσετε με εργαλεία αναφοράς, UI ή πλαίσια πρόσβασης σε δεδομένα.

**Q: Παρέχει το Aspose.Tasks for .NET τεκμηρίωση και πόρους υποστήριξης;**  
A: Ναι, μπορείτε να ανατρέξετε στην ολοκληρωμένη [documentation](https://reference.aspose.com/tasks/net/) και να έχετε πρόσβαση στην υποστήριξη μέσω του [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Υπάρχουν διαθέσιμες επιλογές αδειοδότησης για το Aspose.Tasks for .NET;**  
A: Ναι, μπορείτε να εξερευνήσετε διάφορες επιλογές αδειοδότησης, συμπεριλαμβανομένων δωρεάν δοκιμών και προσωρινών αδειών, στην [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Πόσο συχνά κυκλοφορούν ενημερώσεις και νέες λειτουργίες για το Aspose.Tasks for .NET;**  
A: Το Aspose.Tasks λαμβάνει τακτικές ενημερώσεις που προσθέτουν λειτουργίες, βελτιώνουν την απόδοση και διατηρούν τη συμβατότητα με τις τελευταίες εκδόσεις του Microsoft Project.

---

**Τελευταία Ενημέρωση:** 2026-03-08  
**Δοκιμάστηκε Με:** Aspose.Tasks 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}