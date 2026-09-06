---
date: 2026-08-13
description: Μάθετε πώς να διαβάζετε τις εβδομάδες εργασίας από ένα ημερολόγιο MS
  Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθήστε τον οδηγό βήμα‑βήμα
  με παραδείγματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Ανάγνωση Εβδομάδων Εργασίας από το Ημερολόγιο με το Aspose.Tasks
og_description: Πώς να διαβάσετε τις εβδομάδες εργασίας από ένα ημερολόγιο MS Project
  χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθήστε το σύντομο σεμινάριο με βήματα
  εγκατάστασης, αποσπάσματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Πώς να διαβάσετε τις εβδομάδες εργασίας από το ημερολόγιο MS με το Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Πώς να διαβάσετε τις εβδομάδες εργασίας από το ημερολόγιο MS με το Aspose.Tasks
url: /el/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε τις εβδομάδες εργασίας από το ημερολόγιο MS με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το μάθημα θα **μάθετε πώς να διαβάζετε τις εβδομάδες εργασίας** από ένα ημερολόγιο Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε δημιουργείτε έναν πίνακα αναφορών, συγχρονίζετε προγράμματα με σύστημα ERP, είτε αυτοματοποιείτε την εξαγωγή δεδομένων για αναλύσεις, η προγραμματιστική πρόσβαση στους ορισμούς εβδομάδας εργασίας εξοικονομεί αμέτρητες χειροκίνητες ώρες. Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί αρχεία έργου εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας τόσο ευελιξία όσο και απόδοση.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “read workweeks”;** Αναφέρεται στην εξαγωγή των ορισμών εβδομάδας εργασίας (ημερομηνίες και καθημερινούς κανόνες ωραρίου) από ένα αρχείο Project μέσω κώδικα Java.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (διαθέσιμο δωρεάν trial).  
- **Χρειάζεται άδεια για ανάπτυξη;** Το trial λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις.  
- **Ποιες μορφές αρχείων υποστηρίζονται;** Τanto *.mpp* όσο και αρχεία Project XML, συν 50+ άλλες μορφές για εισαγωγή/εξαγωγή.  
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως κάτω από 10 λεπτά μόλις ρυθμιστεί η βιβλιοθήκη.

## Τι είναι μια εβδομάδα εργασίας στο MS Project;
Μια εβδομάδα εργασίας ορίζει τους κανόνες του ημερολογίου που καθορίζουν πότε οι πόροι είναι διαθέσιμοι κατά τη διάρκεια μιας συγκεκριμένης περιόδου. Περιλαμβάνει ημερομηνία έναρξης, ημερομηνία λήξης και καθημερινά διαστήματα εργασίας (π.χ., 9 π.μ.–5 μ.μ.). Στο MS Project, κάθε ημερολόγιο μπορεί να περιέχει πολλαπλές εβδομάδες εργασίας, επιτρέποντάς σας να μοντελοποιήσετε διακοπές, βάρδιες ή εποχιακά προγράμματα.

## Πώς το Aspose.Tasks διαβάζει τις εβδομάδες εργασίας από ένα ημερολόγιο;
Το Aspose.Tasks εκθέτει το `WorkWeekCollection` ενός αντικειμένου `Calendar`. Δημιουργώντας μια παρουσία `Project`, επιλέγοντας το επιθυμητό ημερολόγιο (με UID ή όνομα) και επαναλαμβάνοντας το `WorkWeekCollection` του, μπορείτε να ανακτήσετε την ετικέτα κάθε εβδομάδας εργασίας, το εύρος ημερομηνιών ισχύος της και τα λεπτομερή καθημερινά διαστήματα εργασίας. Το API διαχειρίζεται όλες τις μετατροπές ημερομηνίας‑ώρας και σέβεται αυτόματα τις ρυθμίσεις ζώνης ώρας του έργου.

## Γιατί να διαβάζετε τις εβδομάδες εργασίας Java από ένα ημερολόγιο Microsoft Project;
Η προγραμματιστική ανάγνωση των εβδομάδων εργασίας εξαλείφει την χειροκίνητη αντιγραφή‑επικόλληση, εξασφαλίζει ότι τα συστήματα downstream (ERP, HR, αναφορές) χρησιμοποιούν ακριβώς τους ίδιους κανόνες προγραμματισμού και εγγυάται τη συνέπεια μεταξύ πολλαπλών έργων. Η αυτοματοποίηση μειώνει επίσης τα ανθρώπινα λάθη και επιταχύνει τις διαδικασίες ενσωμάτωσης, ειδικά όταν χρειάζεται να επεξεργαστείτε δεκάδες αρχεία έργου κάθε νύχτα.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – εγκατεστημένη έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το τελευταίο JAR από την επίσημη ιστοσελίδα: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Ένα **δείγμα αρχείου Project** (`ReadWorkWeeksInformation.mpp`) τοποθετημένο σε γνωστό φάκελο στον υπολογιστή σας.

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε για την αλληλεπίδραση με ημερολόγια και εβδομάδες εργασίας:

`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project, `Calendar` παρέχει τα ημερολόγιά του, `WorkWeek` ορίζει μια εβδομάδα εργασίας, και `WeekDay` αντιπροσωπεύει μια ημέρα.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Βήμα 1: Ρυθμίστε τον φάκελο δεδομένων σας
Ορίστε το φάκελο που περιέχει το αρχείο `.mpp`. Αντικαταστήστε το σύμβολο κράτησης θέσης με την πραγματική διαδρομή στον υπολογιστή σας:

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Δημιουργήστε μια παρουσία Project και αποκτήστε πρόσβαση στο ημερολόγιο
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project και παρέχει πρόσβαση στις δομές δεδομένων του, συμπεριλαμβανομένων των ημερολογίων, των εργασιών και των πόρων.  
Δημιουργήστε ένα αντικείμενο `Project`, επιλέξτε το ημερολόγιο που θέλετε (με UID) και αποκτήστε το `WorkWeekCollection` του:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Συμβουλή:** Αν δεν είστε σίγουροι για το UID του ημερολογίου, επαναλάβετε μέσω `project.getCalendars()` και εκτυπώστε πρώτα το όνομα και το UID κάθε ημερολογίου.

## Βήμα 3: Επανάληψη μέσω των εβδομάδων εργασίας
Η κλάση `WorkWeek` περιλαμβάνει τον ορισμό μιας εβδομάδας εργασίας, περιέχοντας ημερομηνίες έναρξης/λήξης και καθημερινές ρυθμίσεις ωραρίου.  
Περάστε μέσα από κάθε `WorkWeek` για να εμφανίσετε το όνομά του, τις ημερομηνίες έναρξης/λήξης και τις καθημερινές ώρες εργασίας:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Τι θα δείτε:** Η κονσόλα εκτυπώνει την ετικέτα κάθε εβδομάδας εργασίας (π.χ., “Standard”), το εύρος ημερομηνιών ισχύος της, και μπορείτε να εμβαθύνετε στις ακριβείς ώρες εργασίας για κάθε ημέρα.

## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| `NullPointerException` when accessing `calendar` | Λάθος UID ή το ημερολόγιο δεν υπάρχει | Επαληθεύστε το UID με `project.getCalendars().size()` και πρώτα καταγράψτε τα διαθέσιμα ημερολόγια. |
| No output for work weeks | Το επιλεγμένο ημερολόγιο δεν έχει προσαρμοσμένες εβδομάδες εργασίας (χρησιμοποιεί προεπιλογή) | Χρησιμοποιήστε το προεπιλεγμένο ημερολόγιο (`project.getDefaultCalendar()`) ή δημιουργήστε μια εβδομάδα εργασίας προγραμματιστικά. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Εφαρμόστε ένα `SimpleDateFormat` για να μορφοποιήσετε τις ημερομηνίες όπως χρειάζεται. |

## Συχνές ερωτήσεις
**Μ: Μπορώ να τροποποιήσω τις πληροφορίες των εβδομάδων εργασίας χρησιμοποιώντας το Aspose.Tasks για Java;**  
Α: Ναι. Το API παρέχει `addWorkWeek()`, `removeWorkWeek()`, και setters ιδιοτήτων για αλλαγή ονομάτων, ημερομηνιών και ωραρίων.

**Μ: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;**  
Α: Απόλυτα. Υποστηρίζει αρχεία MPP από το Project 98 έως τις πιο πρόσφατες εκδόσεις, καθώς και αρχεία Project XML.

**Μ: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλα Java frameworks;**  
Α: Ναι. Η βιβλιοθήκη είναι καθαρή Java, οπότε μπορείτε να τη χρησιμοποιήσετε μαζί με Spring, Jakarta EE ή οποιοδήποτε άλλο framework.

**Μ: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση 30 ημερών από την επίσημη ιστοσελίδα: [Aspose.Tasks trial](https://releases.aspose.com/).

**Μ: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;**  
Α: Το φόρουμ της κοινότητας Aspose είναι το καλύτερο μέρος: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Τελευταία ενημέρωση:** 2026-08-13  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Προσθήκη ημερολογίου στο έργο με Aspose.Tasks για Java](/tasks/java/calendars/create/)
- [Ανάκτηση εξαιρέσεων ημερολογίου με Aspose.Tasks – μάθημα Java](/tasks/java/calendar-exceptions/retrieve/)
- [Πώς να ορίσετε ημερολόγιο και ημέρες εβδομάδας στο MS Project με Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}