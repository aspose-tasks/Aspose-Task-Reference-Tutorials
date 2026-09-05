---
date: 2026-07-29
description: Μάθετε πώς να προγραμματίζετε μη εργάσιμες ημέρες δημιουργώντας ένα project
  calendar με Aspose.Tasks for Java, ορίζοντας weekday exceptions και διαχειριζόμενοι
  holiday schedules.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Προγραμματισμός μη εργάσιμων ημερών – Create Project Calendar Aspose
og_description: Προγραμματίστε μη εργάσιμες ημέρες χρησιμοποιώντας Aspose.Tasks for
  Java. Μάθετε να ορίζετε weekdays, να προσθέτετε calendar exceptions και να διαχειρίζεστε
  holiday schedules αποδοτικά.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Προγραμματισμός μη εργάσιμων ημερών – Create Project Calendar Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Προγραμματισμός μη εργάσιμων ημερών – Create Project Calendar Aspose
url: /el/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προγραμματισμός μη εργάσιμων ημερών – Δημιουργία ημερολογίου έργου Aspose

### Εισαγωγή
Όταν χρειάζεται να **προγραμματίσετε μη εργάσιμες ημέρες** για ένα έργο, πρέπει να μπορείτε να μοντελοποιήσετε διακοπές, ειδικές βάρδιες ή προσωρινές κλεισίματα απευθείας στο σχέδιο του έργου. Το Aspose.Tasks for Java σας δίνει πλήρη έλεγχο πάνω στους ορισμούς ημερολογίων, επιτρέποντάς σας να προσθέτετε εξαιρέσεις που αντικατοπτρίζουν πραγματικά προγράμματα. Σε αυτό το tutorial θα περάσουμε βήμα-βήμα τις ακριβείς ενέργειες για τον ορισμό των ημερών της εβδομάδας για εξαιρέσεις ημερολογίου, ώστε τα χρονοδιαγράμματα του έργου σας να παραμένουν ακριβή και αξιόπιστα. Στο τέλος θα δείτε επίσης πώς αυτό εντάσσεται σε μια ευρύτερη στρατηγική **προγράμματος μη εργάσιμων ημερών** για οποιοδήποτε εταιρικό έργο.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “προγραμματισμός μη εργάσιμων ημερών”**  
  Σημαίνει ότι χρησιμοποιώντας το Aspose.Tasks δημιουργείται ένα ημερολόγιο που σημειώνει συγκεκριμένες ημερομηνίες ως μη εργάσιμες, επηρεάζοντας αυτόματα τις ημερομηνίες των εργασιών.  
- **Χρειάζομαι άδεια για να εκτελέσω το δείγμα;**  
  Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια IDEs υποστηρίζονται;**  
  IntelliJ IDEA, Eclipse, NetBeans ή οποιοδήποτε IDE που υποστηρίζει Java 8+.  
- **Μπορώ να προσθέσω πολλαπλές εξαιρέσεις στο ίδιο ημερολόγιο;**  
  Ναι – μπορείτε να προσθέσετε όσες `CalendarException` αντικείμενα χρειάζονται.  
- **Σε ποιες μορφές αρχείων μπορώ να αποθηκεύσω το έργο;**  
  XML, MPP και αρκετές άλλες μορφές που υποστηρίζονται από το Aspose.Tasks.  

## Τι είναι το Ημερολόγιο Έργου στο Aspose.Tasks;
Το **project calendar** είναι το κορυφαίο αντικείμενο του Aspose.Tasks που ορίζει τις εργάσιμες ημέρες και ώρες για ένα έργο. Επηρεάζει άμεσα τις ημερομηνίες έναρξης/λήξης των εργασιών, την κατανομή πόρων και τους συνολικούς υπολογισμούς χρονοδιαγράμματος. Προσαρμόζοντας ένα ημερολόγιο, εξασφαλίζετε ότι το χρονοδιάγραμμα σέβεται πραγματικούς περιορισμούς όπως οι εταιρικές διακοπές ή οι πολιτικές εργασίας τα Σαββατοκύριακα.

## Γιατί να ορίζετε ημέρες της εβδομάδας για εξαιρέσεις ημερολογίου;
Ορίζοντας εξαιρέσεις για τις ημέρες της εβδομάδας διασφαλίζει ότι η μηχανή του έργου αντιμετωπίζει αυτές τις ημέρες ως μη εργάσιμες, αποτρέποντας την αυτόματη προγραμματισμό των εργασιών σε αυτές και διατηρώντας το χρονοδιάγραμμα ευθυγραμμισμένο με πραγματικούς περιορισμούς όπως διακοπές, περιόδους συντήρησης ή ειδικά πρότυπα βαρδιών σε όλη την οργάνωση.

- **Ακριβή χρονοδιαγράμματα:** Οι εργασίες δεν θα τοποθετούνται σε διακοπές ή περιόδους αποκλεισμού.  
- **Σχεδιασμός πόρων:** Οι πόροι κατανεμηθούν μόνο σε έγκυρες εργάσιμες ημέρες, αποτρέποντας την υπερκατανομή.  
- **Συμμόρφωση:** Τα χρονοδιαγράμματα ακολουθούν αυτόματα τις πολιτικές της οργάνωσης ή τα νομικά ημερολόγια διακοπών.  

## Πρόγραμμα μη εργάσιμων ημερών με εξαιρέσεις ημερολογίου
Όταν διατηρείτε ένα **πρόγραμμα μη εργάσιμων ημερών**, συνήθως έχετε μια κύρια λίστα διακοπών, περιόδων συντήρησης ή άλλων περιόδων αποκλεισμού. Η προσθήκη αυτών των ημερομηνιών ως αντικείμενα `CalendarException` εγγυάται ότι κάθε υπολογισμός—είτε είναι ανάλυση κρίσιμης διαδρομής είτε εξισορρόπηση πόρων—σέβεται αυτόματα αυτούς τους περιορισμούς. Αυτή η προσέγγιση εξαλείφει τις χειροκίνητες προσαρμογές ημερομηνιών και μειώνει τον κίνδυνο απόκλισης του χρονοδιαγράμματος.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε από την επίσημη [σελίδα λήψης Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).  
3. **Ένα IDE** – IntelliJ IDEA, Eclipse, NetBeans ή οποιονδήποτε επεξεργαστή συμβατό με Java.  

## Πώς να προγραμματίσετε μη εργάσιμες ημέρες χρησιμοποιώντας εξαιρέσεις ημερολογίου

Φορτώστε το έργο σας, δημιουργήστε ένα προσαρμοσμένο ημερολόγιο και προσθέστε αντικείμενα `CalendarException` που σημειώνουν τις επιθυμητές ημέρες της εβδομάδας ως μη εργάσιμες. Όλη αυτή η διαδικασία μπορεί να ολοκληρωθεί σε λίγα απλά βήματα, και το προκύπτον ημερολόγιο θα επηρεάσει αυτόματα όλη τη λογική προγραμματισμού εργασιών.

### Οδηγός βήμα‑βήμα

### Βήμα 1: Εισαγωγή Απαιτούμενων Πακέτων
Χρειαζόμαστε τις βασικές κλάσεις του Aspose.Tasks και το `GregorianCalendar` της Java για τη διαχείριση ημερομηνιών.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Βήμα 2: Ορισμός του Καταλόγου Δεδομένων
Καθορίστε πού θα αποθηκευτεί το παραγόμενο αρχείο έργου.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 3: Δημιουργία Αντικειμένου Project
`Project` είναι το κύριο αντικείμενο που περιέχει όλα τα δεδομένα του έργου, συμπεριλαμβανομένων των εργασιών, των πόρων και των ημερολογίων.

```java
Project project = new Project();
```

### Βήμα 4: Ορισμός Ημερολογίου
`Calendar` αντιπροσωπεύει ένα πρόγραμμα εργάσιμων και μη εργάσιμων ωρών εντός ενός έργου.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Βήμα 5: Ορισμός Εξαίρεσης Ημερών Εβδομάδας
`CalendarException` αντιπροσωπεύει μια περίοδο που σημειώνεται ως μη εργάσιμη σε ένα ημερολόγιο.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Βήμα 6: Αποθήκευση του Έργου
Αποθηκεύστε το έργο, συμπεριλαμβανομένου του προσαρμοσμένου ημερολογίου και της εξαίρεσής του, σε αρχείο XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Οι ημερομηνίες εξαίρεσης δεν εφαρμόζονται** | Βεβαιωθείτε ότι το `setEnteredByOccurrences(false)` και οι σωστές τιμές `FromDate/ToDate` είναι ορισμένες. |
| **Το αποθηκευμένο αρχείο είναι κενό** | Επαληθεύστε ότι το `dataDir` δείχνει σε φάκελο με δικαιώματα εγγραφής και ότι το όνομα αρχείου λήγει με `.xml`. |
| **Το ημερολόγιο δεν αντικατοπτρίζεται στον προγραμματισμό εργασιών** | Αναθέστε το ημερολόγιο σε εργασίες ή πόρους χρησιμοποιώντας `task.setCalendar(cal)` ή `resource.setCalendar(cal)`. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να ορίσω πολλαπλές εξαιρέσεις για διαφορετικές ημέρες της εβδομάδας στο ίδιο ημερολόγιο;**  
A: Ναι. Προσθέστε επιπλέον αντικείμενα `CalendarException` στο `cal.getExceptions()` για κάθε ξεχωριστή περίοδο ή κανόνα.

**Q: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικά Java IDEs;**  
A: Απόλυτα. Η βιβλιοθήκη λειτουργεί με IntelliJ IDEA, Eclipse, NetBeans και οποιοδήποτε IDE που υποστηρίζει τυπικά έργα Java.

**Q: Μπορώ να προσαρμόσω τύπους εξαιρέσεων εκτός από τις καθημερινές εξαιρέσεις;**  
A: Ναι. Χρησιμοποιήστε `CalendarExceptionType.Weekly`, `Monthly` ή `Yearly` για να ταιριάξουν στις ανάγκες του προγραμματισμού σας.

**Q: Πώς μπορώ να διαχειριστώ τις εξαιρέσεις δυναμικά βάσει των απαιτήσεων του έργου;**  
A: Δημιουργήστε τα αντικείμενα εξαίρεσης προγραμματιστικά—π.χ., διαβάστε τις ημερομηνίες διακοπών από μια βάση δεδομένων ή αρχείο ρυθμίσεων και δημιουργήστε `CalendarException` στιγμιότυπα σε βρόχο.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή από τη [σελίδα λήψης Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε πώς να **προγραμματίσετε μη εργάσιμες ημέρες** δημιουργώντας ένα ημερολόγιο έργου και ορίζοντας εξαιρέσεις ημερών της εβδομάδας που αντικατοπτρίζουν ακριβώς τις διακοπές ή ειδικές μη εργάσιμες περιόδους. Η σωστή διαμόρφωση του ημερολογίου είναι ουσιώδης για ρεαλιστικά χρονοδιαγράμματα, κατανομή πόρων και συνολική επιτυχία του έργου. Εξερευνήστε περαιτέρω συνδέοντας το προσαρμοσμένο ημερολόγιο με εργασίες ή πόρους και πειραματιζόμενοι με άλλους τύπους εξαιρέσεων για να δημιουργήσετε ένα ολοκληρωμένο **πρόγραμμα μη εργάσιμων ημερών** για οποιοδήποτε έργο.

---

**Τελευταία ενημέρωση:** 2026-07-29  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Προσθήκη ημερολογίου στο έργο με Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Δημιουργία Εξαίρεσης Ημερολογίου Aspose για Java](/tasks/java/calendar-exceptions/add-remove/)
- [Πώς να ορίσετε Ημερολόγιο και Ημέρες Εβδομάδας στο MS Project με Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}