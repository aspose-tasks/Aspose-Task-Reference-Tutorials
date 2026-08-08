---
date: 2026-08-08
description: Μάθετε πώς να ορίσετε το calendar ms project, να ορίσετε τις ημερήσιες
  ώρες εργασίας και να προσθέσετε εργάσιμες ημέρες το Σαββατοκύριακο χρησιμοποιώντας
  το Aspose.Tasks για Java. Αποθηκεύστε το έργο ως XML με λίγες μόνο γραμμές κώδικα.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Πώς να ορίσετε το calendar ms project και να ορίσετε τις ημέρες της εβδομάδας
og_description: Ορίστε το calendar ms project, ορίστε τις ημέρες της εβδομάδας και
  προσθέστε εργάσιμες ημέρες το Σαββατοκύριακο χρησιμοποιώντας το Aspose.Tasks για
  Java. Ακολουθήστε αυτό το step‑by‑step tutorial και αποθηκεύστε ως XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Ορίστε το calendar ms project με το Aspose.Tasks – Οδηγός Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Πώς να ορίσετε το calendar ms project και να ορίσετε τις ημέρες της εβδομάδας
url: /el/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε το ημερολόγιο ms project και να ορίσετε τις εργάσιμες ημέρες

Σε αυτό το μάθημα θα μάθετε **πώς να ορίσετε το ημερολόγιο ms project** προγραμματιστικά, να ορίσετε τις εργάσιμες ημέρες και να διαμορφώσετε προσαρμοσμένες εργάσιμες ημέρες χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε δημιουργείτε μια μηχανή χρονοπρογραμματισμού, ενσωματώνετε με συστήματα ERP, είτε απλώς χρειάζεστε να δημιουργήσετε ένα σχέδιο έργου χωρίς να ανοίξετε το Microsoft Project, τα παρακάτω βήματα δείχνουν πώς να δημιουργήσετε ένα ημερολόγιο, να ορίσετε ημερήσιες ώρες εργασίας και να προσθέσετε εργάσιμες ημέρες το Σαββατοκύριακο με λίγες γραμμές κώδικα.

## Σύντομες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java.  
- **Μπορώ να προσθέσω εργάσιμες ημέρες το Σαββατοκύριακο;** Ναι – απλώς σημειώστε το Σάββατο και την Κυριακή ως εργάσιμες ημέρες.  
- **Πώς αποθηκεύω το έργο;** Καλέστε `prj.save(..., SaveFileFormat.Xml)`.  
- **Απαιτείται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται άδεια για παραγωγική χρήση.  
- **Ποια έκδοση Java υποστηρίζεται;** Java 8 ή νεότερη.

## Τι είναι το set calendar ms project;
Η ρύθμιση του ημερολογίου στο MS Project καθορίζει ποιες ημέρες θεωρούνται εργάσιμες, τον αριθμό των ωρών εργασίας ανά ημέρα και τυχόν ειδικές εξαιρέσεις όπως αργίες ή κλεισίματα ολόκληρης εταιρείας. Αυτές οι πληροφορίες καθοδηγούν τον προγραμματισμό εργασιών, την κατανομή πόρων και τις συνολικές χρονοδιαγράμματα του έργου, διασφαλίζοντας ότι οι υπολογισμοί σέβονται τα πραγματικά πρότυπα εργασίας του οργανισμού.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για χειρισμό ημερολογίων;
Το Aspose.Tasks σας δίνει προγραμματιστικό έλεγχο πάνω στα ημερολόγια χωρίς να ανοίγετε το UI του Microsoft Project. Λειτουργεί σε οποιοδήποτε λειτουργικό σύστημα υποστηρίζει Java, υποστηρίζει πάνω από 50 μορφές εισόδου/εξόδου και μπορεί να επεξεργαστεί έργα εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας το ιδανικό για αυτοματοποίηση από την πλευρά του διακομιστή.

## Προαπαιτούμενα
- **Java Development Kit (JDK) 8+** – κατεβάστε το από την [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – αποκτήστε το τελευταίο JAR από τη [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- Ένα IDE ή εργαλείο κατασκευής (Maven/Gradle) για να προσθέσετε το Aspose.Tasks JAR στο classpath σας.

## Εισαγωγή πακέτων
Εισάγετε τις κλάσεις που παρέχουν πρόσβαση σε έργα, ημερολόγια και αντικείμενα χρόνου εργασίας.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: δημιουργία ενός αντικειμένου Project
Δημιουργήστε ένα αντικείμενο `Project`, το οποίο αντιπροσωπεύει το αρχείο MS Project που θα επεξεργαστείτε.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Βήμα 2: ορισμός νέου ημερολογίου
`Calendar` αντιπροσωπεύει ένα σύνολο ωρών εργασίας, εξαιρέσεων και αργιών για ένα έργο.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Βήμα 3: προσθήκη τυπικών εργάσιμων ημερών (Δευτέρα‑Πέμπτη)
`WeekDay` ορίζει τον χρόνο εργασίας για μια συγκεκριμένη ημέρα της εβδομάδας.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Βήμα 4: προσθήκη εργάσιμων ημερών το Σαββατοκύριακο
Αν το έργο σας λειτουργεί και τα Σαββατοκύριακα, προσθέστε το Σάββατο και την Κυριακή ως κανονικές εργάσιμες ημέρες. Αυτό δείχνει **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Βήμα 5: ορισμός προσαρμοσμένης σύντομης εργάσιμης ημέρας (Παρασκευή)
Διαμορφώστε την Παρασκευή με πρωινή βάρδια (9 πμ‑12 μμ) και απογευματινή βάρδια (1 μμ‑4 μμ) για να απεικονίσετε **set daily working hours** και μια προσαρμοσμένη σύντομη εργάσιμη ημέρα.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Βήμα 6: αποθήκευση του έργου ως XML
`SaveFileFormat` απαριθμεί τις υποστηριζόμενες μορφές αρχείων κατά την αποθήκευση ενός έργου, όπως XML ή MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Συνηθισμένα προβλήματα & λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Οι ώρες εργασίας δεν εφαρμόζονται** | Βεβαιωθείτε ότι καλείται `setDayWorking(true)` σε κάθε προσαρμοσμένο `WeekDay`. |
| **Το αρχείο δεν βρέθηκε κατά την αποθήκευση** | Επαληθεύστε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι η εφαρμογή έχει δικαιώματα εγγραφής. |
| **Το ημερολόγιο δεν αντικατοπτρίζεται στις εργασίες** | Αναθέστε το νεοδημιουργημένο ημερολόγιο σε πόρους ή εργασίες χρησιμοποιώντας `task.setCalendar(cal)`. |

## Συχνές ερωτήσεις

**Ε: Μπορώ να ορίσω προσαρμοσμένες μη‑εργάσιμες ημέρες χρησιμοποιώντας το Aspose.Tasks for Java;**  
Α: Ναι. Ορίστε την ιδιότητα `DayWorking` σε `false` για οποιοδήποτε `WeekDay` θέλετε να θεωρήσετε μη‑εργάσιμη ημέρα.

**Ε: Πώς μπορώ να προσθέσω αργίες ή εξαιρέσεις σε επίπεδο εταιρείας;**  
Α: Δημιουργήστε αντικείμενα `CalendarException`, ορίστε τις ημερομηνίες εξαίρεσης και προσθέστε τα στο `cal.getExceptions()`.

**Ε: Είναι η βιβλιοθήκη συμβατή με παλαιότερες εκδόσεις του MS Project;**  
Α: Απόλυτα. Το Aspose.Tasks υποστηρίζει μορφές MPP, MPT και XML σε πολλές εκδόσεις του Project.

**Ε: Μπορώ να τροποποιήσω ένα υπάρχον ημερολόγιο σε εισαγόμενο έργο;**  
Α: Φορτώστε το έργο με `new Project("existing.mpp")`, ανακτήστε το επιθυμητό ημερολόγιο, κάντε τις αλλαγές και αποθηκεύστε.

**Ε: Το Aspose.Tasks διαχειρίζεται επίσης επαναλαμβανόμενες εργασίες;**  
Α: Ναι, μπορείτε να δημιουργήσετε και να επεξεργαστείτε επαναλαμβανόμενες εργασίες χρησιμοποιώντας την κλάση `RecurringTask`.

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να ορίσετε το ημερολόγιο ms project**, να ορίσετε τις εργάσιμες ημέρες, να προσθέσετε εργάσιμες ημέρες το Σαββατοκύριακο και να διαμορφώσετε ένα σύντομο πρόγραμμα για την Παρασκευή — όλα με το Aspose.Tasks για Java. Αποθηκεύστε το αποτέλεσμα ως XML και ενσωματώστε τη λογική του ημερολογίου σε οποιαδήποτε λύση διαχείρισης έργων βασισμένη σε Java.

---

**Τελευταία ενημέρωση:** 2026-08-08  
**Δοκιμή με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικές οδηγίες

- [Προσθήκη ημερολογίου σε έργο με Aspose.Tasks για Java](/tasks/java/calendars/create/)
- [Καθορισμός εργάσιμων ημερών & ωρών εργασίας με Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Προσθήκη αργιών στο ημερολόγιο και αποθήκευση ως MPP με Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}