---
date: 2026-10-05
description: Μάθετε πώς να δημιουργήσετε δοκιμαστικό έργο και να υπολογίσετε τις ημέρες
  μεταξύ ημερομηνιών χρησιμοποιώντας το Aspose.Tasks for Java, να προσθέσετε ένα προσαρμοσμένο
  πεδίο και να διαχειριστείτε αρχεία MPP αποδοτικά.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Εργασία με τύπους στο Aspose.Tasks
og_description: Δημιουργία δοκιμαστικού έργου και υπολογισμός ημερών μεταξύ ημερομηνιών
  χρησιμοποιώντας το Aspose.Tasks for Java. Αυτός ο οδηγός δείχνει πώς να προσθέσετε
  ένα προσαρμοσμένο πεδίο, να ορίσετε προθεσμίες εργασιών και να αποθηκεύσετε το έργο
  ως αρχείο MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Δημιουργία δοκιμαστικού έργου και υπολογισμός ημερών μεταξύ ημερομηνιών
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Δημιουργία δοκιμαστικού έργου και υπολογισμός ημερών μεταξύ ημερομηνιών
url: /el/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία δοκιμαστικού έργου και υπολογισμός ημερών μεταξύ ημερομηνιών

Σε αυτό το tutorial θα **δημιουργήσετε δοκιμαστικό έργο** και **υπολογίσετε ημέρες μεταξύ ημερομηνιών** προσθέτοντας ένα προσαρμοσμένο πεδίο, ορίζοντας ένα εκτεταμένο χαρακτηριστικό και εφαρμόζοντας έναν τύπο Microsoft Project μέσω της βιβλιοθήκης Aspose.Tasks για Java. Είτε χρειάζεστε τη δημιουργία χρονοδιαγραμμάτων, τον υπολογισμό προθεσμιών ή την αυτοματοποίηση αναφορών, το Aspose.Tasks σας επιτρέπει να χειρίζεστε δεδομένα Project προγραμματιστικά χωρίς εγκατάσταση επιφάνειας εργασίας, υποστηρίζοντας πάνω από 50 μορφές εισόδου/εξόδου και διαχειριζόμενο αρχεία εκατοντάδων σελίδων με αποδοτική χρήση μνήμης.

## Γρήγορες απαντήσεις
- **Τι καλύπτει το tutorial;** Δείχνει πώς να δημιουργήσετε ένα δοκιμαστικό έργο, να ορίσετε ένα εκτεταμένο χαρακτηριστικό, να θέσετε προθεσμία εργασίας και να χρησιμοποιήσετε έναν τύπο για τον υπολογισμό ημερών μεταξύ ημερομηνιών.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (τελευταία έκδοση).  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποιο IDE μπορώ να χρησιμοποιήσω;** Οποιοδήποτε Java IDE (IntelliJ IDEA, Eclipse, VS Code) που υποστηρίζει JDK 8+.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για αντιγραφή του κώδικα και εκτέλεση.

## Τι είναι το «υπολογισμός ημερών μεταξύ ημερομηνιών» στο Aspose.Tasks;
Στο Aspose.Tasks, ένας τύπος είναι μια συμβολοσειρά που μπορεί να αναφέρεται σε πεδία εργασίας και να εκτελεί υπολογισμούς. `[Deadline] - [Finish]` είναι η σύνταξη τύπου που χρησιμοποιεί το Aspose.Tasks για να επιστρέψει τη διαφορά σε ημέρες μεταξύ δύο πεδίων ημερομηνίας. Το αποτέλεσμα αποθηκεύεται ως αριθμητική τιμή που αντιπροσωπεύει ολόκληρες ημέρες, την οποία μπορείτε να εμφανίσετε σε προσαρμοσμένο πεδίο ή να τη χρησιμοποιήσετε σε περαιτέρω υπολογισμούς.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για τον υπολογισμό ημερών μεταξύ ημερομηνιών;
Το Aspose.Tasks παρέχει **πλήρη κάλυψη API** για κάθε ιδιότητα Project, Task και Resource, λειτουργεί σε Windows, Linux και macOS, και **δεν απαιτεί την εγκατάσταση του Microsoft Project ή του Office**. Η μηχανή μπορεί να επεξεργαστεί έργα με **πάνω από 500 εργασίες** σε λιγότερο από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή, καθιστώντας το ιδανικό για CI pipelines, Docker containers και επεξεργασία μεγάλου όγκου batch.

## Πώς να ορίσετε προθεσμία για μια εργασία
Η java.util.Calendar είναι μια κλάση Java που αντιπροσωπεύει μια συγκεκριμένη στιγμή στο χρόνο. Ορίζετε μια προθεσμία αναθέτοντας μια τιμή `java.util.Calendar` στο πεδίο `Tsk.DEADLINE` μιας εργασίας. Μετά τη δημιουργία του αντικειμένου Calendar, ορίστε το έτος, το μήνα και την ημέρα στην επιθυμητή προθεσμία, στη συνέχεια καλέστε `task.set(Tsk.DEADLINE, calendar);`. Η προθεσμία αποθηκεύεται στο αρχείο του έργου και μπορεί να χρησιμοποιηθεί σε τύπους όπως `[Deadline] - [Finish]`.

## Πώς να ορίσετε εκτεταμένο χαρακτηριστικό
Ένα εκτεταμένο χαρακτηριστικό είναι ένα προσαρμοσμένο πεδίο που αποθηκεύει το αποτέλεσμα του τύπου σας. Το δημιουργείτε μία φορά, του δίνετε ένα φιλικό ψευδώνυμο και συνδέετε την έκφραση `[Deadline] - [Finish]` ώστε κάθε εργασία να υπολογίζει αυτόματα το διάστημα. Δημιουργήστε το με την δημιουργία ενός `ExtendedAttribute`, ορίζοντας το Alias του, αναθέτοντας τον τύπο και προσθέτοντάς το στη συλλογή του έργου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- **Java Development Kit (JDK) 8+** – κατεβάστε από την ιστοσελίδα της Oracle ή χρησιμοποιήστε OpenJDK.  
- **Aspose.Tasks for Java** – αποκτήστε το τελευταίο JAR από τη [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) και προσθέστε το στο classpath του έργου σας ή στις εξαρτήσεις Maven/Gradle.

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστούμε:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Δημιουργία δοκιμαστικού έργου με προσαρμοσμένο πεδίο
Ξεκινάμε με **δημιουργία δοκιμαστικού έργου** και προσθέτουμε ένα προσαρμοσμένο πεδίο που θα κρατήσει αργότερα το αποτέλεσμα του τύπου μας.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Συμβουλή:* `CreateTestProjectWithCustomField()` είναι μια βοηθητική μέθοδος που δημιουργεί ένα ελάχιστο χρονοδιάγραμμα και καταχωρεί ένα εκτεταμένο χαρακτηριστικό έτοιμο για ανάθεση τύπου.

### Βήμα 2: Ορισμός εκτεταμένου χαρακτηριστικού (προσθήκη προσαρμοσμένου πεδίου)
Στη συνέχεια, **ορίζουμε ένα εκτεταμένο χαρακτηριστικό** – ουσιαστικά το προσαρμοσμένο πεδίο – και του δίνουμε ένα φιλικό ψευδώνυμο. Εδώ είναι που **προσθέτουμε λογική προσαρμοσμένου πεδίου**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** κάνει το πεδίο αναγνώσιμο στο Project.  
- **Formula** υπολογίζει τον αριθμό ημερών μεταξύ της ημερομηνίας *Finish* μιας εργασίας και της *Deadline* της – ο πυρήνας του *υπολογισμού ημερών μεταξύ ημερομηνιών*.

### Βήμα 3: Ορισμός προθεσμίας για μια εργασία (προσθήκη εργασίας προθεσμίας & ορισμός προθεσμίας εργασίας)
Τώρα **προσθέτουμε δεδομένα προθεσμίας εργασίας** ορίζοντας την ιδιότητα *Deadline* σε μια συγκεκριμένη εργασία.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Το αντικείμενο `Calendar` ορίζει την ακριβή στιγμή της προθεσμίας.  
- `set(Tsk.DEADLINE, …)` **ορίζει την προθεσμία της εργασίας** για την επιλεγμένη εργασία.

### Βήμα 4: Αποθήκευση του έργου (χειρισμός αρχείου Microsoft Project)
Τέλος, **χειριζόμαστε το Microsoft Project** αποθηκεύοντας τις αλλαγές σε ένα αρχείο MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Μπορείτε να ανοίξετε το `SaveFile.mpp` στο Microsoft Project για να δείτε το προσαρμοσμένο πεδίο, το αποτέλεσμα του τύπου και την προθεσμία να εμφανίζονται στο χρονοδιάγραμμα.

## Συχνά προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Ο τύπος δεν αξιολογείται** | Βεβαιωθείτε ότι η συμβολοσειρά `Formula` του χαρακτηριστικού χρησιμοποιεί σωστά ονόματα πεδίων (π.χ., `[Deadline]`, `[Finish]`). |
| **Η εργασία δεν βρέθηκε** | Επαληθεύστε ότι το ID της εργασίας (`1` στο παράδειγμα) υπάρχει· χρησιμοποιήστε `project.getRootTask().getChildren().size()` για εντοπισμό σφαλμάτων. |
| **Εξαίρεση άδειας** | Εφαρμόστε μια έγκυρη άδεια Aspose.Tasks πριν καλέσετε οποιεσδήποτε μεθόδους API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;**  
A: Ναι, το Aspose.Tasks παρέχει API για .NET, Java και άλλες πλατφόρμες, επιτρέποντάς σας να χειρίζεστε αρχεία Microsoft Project στη γλώσσα της επιλογής σας.

**Q: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks;**  
A: Απόλυτα. Κατεβάστε μια πλήρως λειτουργική δοκιμή από τη [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks;**  
A: Η επίσημη τεκμηρίωση φιλοξενείται στη [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;**  
A: Επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για να θέσετε ερωτήσεις και να μοιραστείτε εμπειρίες με την κοινότητα.

**Q: Χρειάζομαι προσωρινή άδεια για αξιολόγηση;**  
A: Μια προσωρινή άδεια είναι διαθέσιμη για βραχυπρόθεσμη δοκιμή· μπορείτε να ζητήσετε μία από τη [temporary license request page](https://purchase.aspose.com/temporary-license/).

---

**Τελευταία ενημέρωση:** 2026-10-05  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε αρχείο MPP – Δημιουργία & αποθήκευση κεντρικού έργου σε μορφή MPP με Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Ορισμός ημερομηνίας έναρξης έργου στο MS Project χρησιμοποιώντας Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Πώς να δημιουργήσετε εκτεταμένο χαρακτηριστικό σε Java με Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}