---
date: 2026-08-13
description: Μάθετε πώς να προσθέσετε αργίες σε ένα calendar, να αναθέσετε το calendar
  σε ένα project και να αποθηκεύσετε το αρχείο MS Project ως MPP χρησιμοποιώντας Aspose.Tasks
  για Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Ενημέρωση του calendar σε μορφή MPP στο Aspose.Tasks
og_description: Προσθήκη αργιών στο calendar, ανάθεση του σε ένα project και μετατροπή
  του schedule σε MPP χρησιμοποιώντας Aspose.Tasks για Java. Μάθετε αυτοματοποίηση
  βήμα προς βήμα.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Προσθήκη αργιών στο calendar και αποθήκευση ως MPP με Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Προσθήκη αργιών στο calendar και αποθήκευση ως MPP με Aspose.Tasks
url: /el/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη αργιών στο ημερολόγιο και αποθήκευση ως MPP με Aspose.Tasks

## Εισαγωγή

Στη σύγχρονη διαχείριση έργων συχνά χρειάζεται να **add holidays to calendar** αρχεία, να δημιουργήσετε ένα **MS Project calendar**, και στη συνέχεια να μοιραστείτε το χρονοδιάγραμμα σε μορφή MPP. Είτε ενοποιείτε χρονολογίες από πολλαπλές πηγές είτε μεταφέρετε παλαιά δεδομένα, η δημιουργία ημερολογίου προγραμματιστικά εξαλείφει τα χειροκίνητα σφάλματα και επιταχύνει την παράδοση. Αυτό το σεμινάριο σας οδηγεί μέσα από τη διαδικασία δημιουργίας ημερολογίου στο MS Project, προσαρμογής του με αργίες, **assign calendar to project**, και τελικά **convert project to MPP** χρησιμοποιώντας το Aspose.Tasks Java API.

## Γρήγορες Απαντήσεις
- **Τι καλύπτει αυτό το σεμινάριο;** Προσθήκη αργιών σε ένα ημερολόγιο, ανάθεση του σε ένα έργο, και αποθήκευση του αποτελέσματος ως αρχείο MPP με Aspose.Tasks for Java.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση της Java απαιτείται;** Java 8 ή νεότερη (JDK 8+).  
- **Μπορώ να προσαρμόσω το ημερολόγιο;** Ναι – μπορείτε να προσθέσετε ώρες εργασίας, εξαιρέσεις και αργίες.  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα βασικό ημερολόγιο.  

## Τι είναι το “create calendar MS Project”?

Η δημιουργία ημερολογίου MS Project σημαίνει τον ορισμό των εργάσιμων ημερών, ωρών και εξαιρέσεων που καθορίζουν τον προγραμματισμό των εργασιών μέσα σε ένα αρχείο Microsoft Project. Χρησιμοποιώντας το Aspose.Tasks μπορείτε προγραμματιστικά να δημιουργήσετε αυτό το ημερολόγιο, να ορίσετε αργίες και να το ενσωματώσετε σε ένα έργο χωρίς να ανοίξετε το UI του MS Project.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για αυτήν την εργασία;

Θα πρέπει να χρησιμοποιήσετε το Aspose.Tasks επειδή προσφέρει πλήρη συμβατότητα με Java, δεν απαιτείται Microsoft Office και σας επιτρέπει να δημιουργήσετε και να αποθηκεύσετε αρχεία MPP απευθείας από κώδικα. Η βιβλιοθήκη υποστηρίζει όλες τις λειτουργίες ημερολογίου, λειτουργεί σε οποιοδήποτε περιβάλλον διακομιστή και επεξεργάζεται έργα έως 10 000 εργασίες σε λιγότερο από ένα δευτερόλεπτο.

## Προαπαιτούμενα

1. **Java Development Kit (JDK) 8+** – βεβαιωθείτε ότι η εντολή `java -version` εμφανίζει 1.8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το πιο πρόσφατο JAR από την [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή προτιμάτε.  
4. **Βασικές γνώσεις Java** – εξοικείωση με κλάσεις, μεθόδους και I/O αρχείων.  

## Πώς να προσθέσετε αργίες στο ημερολόγιο

Για να προσθέσετε αργίες δημιουργείτε ένα νέο αντικείμενο `Calendar`, ανακτάτε τη συλλογή `Exceptions` του και προσθέτετε καταχωρήσεις `DateException` για κάθε ημερομηνία αργίας. Το `DateException` αντιπροσωπεύει μια μη εργάσιμη ημερομηνία ή εύρος σε ένα ημερολόγιο. Το Aspose.Tasks στη συνέχεια αντιμετωπίζει αυτές τις ημερομηνίες ως μη εργάσιμες, εξασφαλίζοντας ότι οι εργασίες προγραμματίζονται γύρω από τις καθορισμένες αργίες.

### Βήμα 1: εισαγωγή απαιτούμενων πακέτων

Πρώτα, φέρτε τις κλάσεις του Aspose.Tasks και τις βοηθητικές βιβλιοθήκες της Java στο πεδίο ορατότητας.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Βήμα 2: ορισμός του καταλόγου δεδομένων

Ορίστε πού θα βρίσκονται τα αρχεία προτύπου εισόδου και εξόδου. Αντικαταστήστε το σύμβολο κράτησης θέσης με την πραγματική διαδρομή στο σύστημά σας.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 3: ορισμός ονομάτων αρχείων εισόδου και εξόδου

Θα φορτώσουμε ένα υπάρχον αρχείο MPP (ή ένα κενό έργο) και θα γράψουμε το αποτέλεσμα σε ένα νέο αρχείο.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Βήμα 4: φόρτωση του έργου και προσθήκη νέου ημερολογίου

Η κλάση `Project` αντιπροσωπεύει ένα αρχείο MS Project στη μνήμη και παρέχει πρόσβαση στα ημερολόγια, τις εργασίες και τους πόρους του.

Δημιουργήστε μια παρουσία `Project` από το αρχείο προέλευσης και προσθέστε ένα ημερολόγιο με όνομα **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Βήμα 5: προσαρμογή του ημερολογίου (προαιρετικό)

Το αντικείμενο `Calendar` ορίζει τις εργάσιμες ημέρες, ώρες και εξαιρέσεις για το χρονοδιάγραμμα ενός έργου.

Αν χρειάζεστε συγκεκριμένες ώρες εργασίας, αργίες ή εξαιρέσεις, καλέστε τη δική σας βοηθητική μέθοδο. Το παράδειγμα χρησιμοποιεί το `GetTestCalendar` ως σύμβολο κράτησης θέσης.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Μπορείτε να χειριστείτε απευθείας το `cal1.getWeekDays()` για να ορίσετε τις εργάσιμες ώρες για κάθε ημέρα της εβδομάδας, ή να χρησιμοποιήσετε το `cal1.getExceptions()` για **add holidays to calendar**.

### Βήμα 6: ανάθεση του ημερολογίου στο έργο

Ενημερώστε το έργο ώστε να χρησιμοποιεί το νεοδημιουργημένο ημερολόγιο για όλους τους υπολογισμούς χρονοπρογραμματισμού.

```java
project.set(Prj.CALENDAR, cal1);
```

### Βήμα 7: αποθήκευση του έργου ως MPP

Η απαρίθμηση `SaveFileFormat` καθορίζει τη μορφή εξόδου, με το `Mpp` να υποδεικνύει τη γνήσια μορφή Microsoft Project.

Τώρα **convert project to MPP** αποθηκεύοντας το με την επιλογή `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Βήμα 8: επιβεβαίωση επιτυχούς ολοκλήρωσης

Ένα απλό μήνυμα στην κονσόλα σας ενημερώνει ότι η διαδικασία ολοκληρώθηκε χωρίς σφάλματα.

```java
System.out.println("Process completed Successfully");
```

## Συνηθισμένες περιπτώσεις χρήσης

- **Αυτοματοποιημένη δημιουργία χρονοδιαγράμματος** για επαναλαμβανόμενα έργα (π.χ. εβδομαδιαίες σπριντ).  
- **Μεταφορά παλαιών ημερολογίων CSV ή Excel** σε ένα πλήρως εξοπλισμένο αρχείο MS Project.  
- **Αναφορές από τον διακομιστή** όπου μια υπηρεσία web επιστρέφει αρχείο MPP κατόπιν αιτήματος.  

## Αντιμετώπιση προβλημάτων & κοινές παγίδες

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Βεβαιωθείτε ότι ο φάκελος υπάρχει ή δημιουργήστε τον προγραμματιστικά. |
| Calendar not applied to tasks | Tasks still reference the default calendar | After setting `Prj.CALENDAR`, also update each task’s `Task.CALENDAR` if they were previously overridden. |
| Output file is 0 KB | Missing write permissions | Run the JVM with appropriate file system rights or choose a writable path. |

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις του MS Project;**  
A: Ναι, το Aspose.Tasks υποστηρίζει όλες τις μορφές αρχείων Microsoft Project από το Project 2007 έως το Project 2024, καλύπτοντας περισσότερες από 10 εκδόσεις.

**Q: Μπορώ να προσαρμόσω τα ημερολόγια σύμφωνα με συγκεκριμένες απαιτήσεις του έργου;**  
A: Απόλυτα. Μπορείτε να ορίσετε εργάσιμες ημέρες, να δημιουργήσετε προσαρμοσμένες εβδομάδες εργασίας, να προσθέσετε αργίες και ακόμη να δημιουργήσετε πολλαπλά ημερολόγια μέσα σε ένα μόνο αρχείο έργου.

**Q: Παρέχει το Aspose.Tasks for Java υποστήριξη για αντιμετώπιση προβλημάτων και βοήθεια;**  
A: Ναι, μπορείτε να λάβετε βοήθεια από το φόρουμ της κοινότητας Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks for Java;**  
A: Ναι, είναι διαθέσιμη πλήρως λειτουργική δωρεάν δοκιμή [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks for Java;**  
A: Προσωρινές άδειες μπορούν να ζητηθούν μέσω της ιστοσελίδας Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**Τελευταία ενημέρωση:** 2026-08-13  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [How to Define Weekdays in MS Project Calendars – Aspose.Tasks Java](/tasks/java/calendars/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}