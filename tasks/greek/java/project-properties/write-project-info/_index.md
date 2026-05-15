---
date: 2026-05-15
description: Μάθετε πώς να ορίσετε την ημερομηνία έναρξης του έργου, να γράψετε πληροφορίες
  έργου και να αποθηκεύσετε το έργο ως XML χρησιμοποιώντας Aspose.Tasks for Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Γράψτε πληροφορίες έργου στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ορισμός ημερομηνίας έναρξης έργου στο MS Project χρησιμοποιώντας Aspose.Tasks
  for Java
url: /el/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Ημερομηνίας Έναρξης Έργου στο MS Project χρησιμοποιώντας το Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial, θα ανακαλύψετε πώς να **ορίσετε την ημερομηνία έναρξης του έργου** και να γράψετε πρόσθετες πληροφορίες MS Project με το Aspose.Tasks for Java. Είτε αυτοματοποιείτε χρονοδιαγράμματα έργων, δημιουργείτε εκθέσεις ή ενσωματώνετε δεδομένα Project σε ένα μεγαλύτερο σύστημα, ο προγραμματιστικός έλεγχος της ημερομηνίας έναρξης σας δίνει ακριβή διαχείριση των χρονοδιαγραμμάτων σας. Θα περάσουμε βήμα-βήμα από τη ρύθμιση του περιβάλλοντος μέχρι την αποθήκευση του ενημερωμένου έργου ως αρχείο XML, ώστε να μπορείτε να εφαρμόσετε αυτές τις τεχνικές αμέσως.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για τη διαχείριση ενός έργου;** `Project` from the Aspose.Tasks library.  
  Η κλάση `Project` αντιπροσωπεύει ένα αρχείο MS Project στη μνήμη.  
- **Πώς ορίζω την ημερομηνία έναρξης του έργου;** Use `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` είναι το κλειδί ιδιότητας που χρησιμοποιείται για τον ορισμό της ημερομηνίας έναρξης του έργου.  
- **Μπορώ επίσης να ορίσω την ημερομηνία κατάστασης;** Yes, with `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` καθορίζει την ημερομηνία που αντανακλά την τρέχουσα κατάσταση του έργου.  
- **Ποια μορφή πρέπει να χρησιμοποιήσω για την εξαγωγή του έργου;** Save as XML with `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` υποδεικνύει ότι το έργο θα αποθηκευτεί σε μορφή XML.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** A valid Aspose.Tasks license is required for full functionality.  
- **Ποια περιβάλλοντα υποστηρίζει το Aspose.Tasks;** Windows, Linux, and macOS with Java 8+.

## Τι είναι ο ορισμός ημερομηνίας έναρξης έργου;
Ο ορισμός της ημερομηνίας έναρξης του έργου καθορίζει την ημερολογιακή ημέρα κατά την οποία αρχίζει το χρονοδιάγραμμα, θέτοντας τη βάση για όλους τους υπολογισμούς εργασιών, τις εξαρτήσεις και την ανάλυση κρίσιμης διαδρομής. Ορίζοντας αυτήν την ημερομηνία προγραμματιστικά, εξασφαλίζετε ότι κάθε δημιουργημένο αρχείο έργου ξεκινά από το ίδιο σημείο, εξαλείφοντας τα λάθη χειροκίνητης εισαγωγής και διασφαλίζοντας επαναλήψιμα αποτελέσματα σε όλες τις εκδόσεις.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks for Java για να γράψετε πληροφορίες έργου;
Το Aspose.Tasks for Java παρέχει **πάνω από 150 παραμετροποιήσιμες ιδιότητες έργου** και υποστηρίζει **30+ μορφές αρχείων**, επιτρέποντάς σας να διαβάζετε, να τροποποιείτε και να γράφετε δεδομένα MS Project χωρίς να έχετε εγκατεστημένο το Microsoft Project. Η βιβλιοθήκη λειτουργεί σε Windows, Linux και macOS, επεξεργάζεται αρχεία εκατοντάδων σελίδων σε λειτουργία εξοικονόμησης μνήμης και μπορεί να ενσωματωθεί σε CI/CD pipelines, υπηρεσίες batch‑processing ή cloud‑based back‑ends. Αυτές οι μετρήσιμες δυνατότητες την καθιστούν την πιο αξιόπιστη επιλογή για αυτοματοποίηση σε επιχειρησιακό επίπεδο.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – οποιαδήποτε πρόσφατη έκδοση (συνιστάται 8+).  
2. **Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.  

## Εισαγωγή Πακέτων
First, import the necessary packages in your Java project:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Βήμα 1: Ρύθμιση Καταλόγου Δεδομένων
Define the directory where your project data will be stored.
```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Δημιουργία Αντικειμένου Project
The `Project` class is Aspose.Tasks' top‑level object that represents a single MS Project file in memory. Initializing it creates an empty schedule that you can immediately start populating.
```java
Project project = new Project();
```

## Βήμα 3: Ορισμός Ιδιοτήτων Πληροφοριών Έργου
Here we set the **project start date**, schedule‑from‑start flag, and status date—covering the primary and secondary keywords *write project information* and *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Βήμα 4: Αποθήκευση Έργου ως XML
Finally, persist the updated project file. Saving as XML ensures maximum compatibility with downstream tools and keeps the file size small.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Κοινά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Incorrect start date** | Calendar month is zero‑based in Java. | Use `Calendar.JULY` (or add 1 to month index) as shown. |
| **File not saved** | `dataDir` does not exist or lacks write permission. | Create the directory beforehand or choose a writable path. |
| **License warning** | Running without a license adds a watermark. | Apply a valid Aspose.Tasks license before creating the `Project` object. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java για να διαβάσω αρχεία MS Project;**  
A: Yes, Aspose.Tasks for Java provides robust functionalities for both reading and writing MS Project files.

**Q: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις του MS Project;**  
A: Absolutely, Aspose.Tasks for Java supports various MS Project versions, ensuring seamless handling of MPP, XML, and Primavera formats.

**Q: Υπάρχουν περιορισμοί στην έκδοση δοκιμής του Aspose.Tasks for Java;**  
A: The trial version allows full feature exploration but inserts a watermark on generated files and limits the number of project entities you can create.

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;**  
A: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks for Java;**  
A: Yes, temporary licenses are available for short‑term usage. You can obtain one from [here](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
You’ve now learned how to **set project start date**, write essential project information, and **save project as XML** using Aspose.Tasks for Java. These building blocks empower you to automate project‑management workflows, generate consistent schedules, and integrate MS Project data into your Java applications. Next, explore how to add tasks, resources, and custom fields to further enrich your automated schedules.

---

**Τελευταία Ενημέρωση:** 2026-05-15  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Ορίσετε το Ημερολόγιο Έργου με το Aspose.Tasks για Java](/tasks/java/calendars/properties/)
- [Πώς να Διαβάσετε Πληροφορίες Έργου από το Microsoft Project με το Aspose.Tasks για Java](/tasks/java/project-properties/read-project-info/)
- [Φόρτωση Αρχείου MPP Java - Διαχείριση Ιδιοτήτων Έργου με το Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}