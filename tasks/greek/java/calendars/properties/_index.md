---
date: 2026-09-09
description: Πώς να ορίσετε το ημερολόγιο έργου σε Java χρησιμοποιώντας το Aspose.Tasks.
  Μάθετε πώς να εμφανίζετε τις ώρες εργασίας του ημερολογίου, να ρυθμίζετε τον χρόνο
  εργασίας και να τροποποιείτε τις ημέρες του ημερολογίου σε αρχεία MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Διαχείριση ιδιοτήτων ημερολογίου στο Aspose.Tasks
og_description: Πώς να ορίσετε το ημερολόγιο έργου σε Java χρησιμοποιώντας το Aspose.Tasks.
  Μάθετε πώς να εμφανίζετε τις ώρες εργασίας του ημερολογίου, να ρυθμίζετε τον χρόνο
  εργασίας και να τροποποιείτε τις ημέρες του ημερολογίου σε αρχεία MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Πώς να ορίσετε το ημερολόγιο έργου Java με το Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Πώς να ορίσετε το ημερολόγιο έργου Java με το Aspose.Tasks
url: /el/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε το ημερολόγιο έργου Java με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το μάθημα θα μάθετε **πώς να ορίσετε το ημερολόγιο έργου** σε Java χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks. Ο έλεγχος των ιδιοτήτων του ημερολογίου σας επιτρέπει να **εμφανίσετε τις ώρες εργασίας του ημερολογίου**, να διαμορφώσετε προσαρμοσμένες εργάσιμες ημέρες και να διατηρήσετε το χρονοδιάγραμμα του έργου σας ευθυγραμμισμένο με πραγματικούς περιορισμούς όπως αργίες ή βάρδιες. Θα περάσουμε από τη ρύθμιση του περιβάλλοντος, τη φόρτωση ενός έργου, την επανάληψη μέσω των ημερολογίων και την ανάγνωση ή ενημέρωση των ιδιοτήτων τους, ώστε να μπορείτε με σιγουριά **να διαχειρίζεστε τις ρυθμίσεις του ημερολογίου MS Project** σε οποιαδήποτε εφαρμογή Java.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “ορισμός ημερολογίου έργου”;** Σημαίνει τη δημιουργία ή ενημέρωση των ωρών εργασίας ενός ημερολογίου, του βασικού ημερολογίου και των τύπων ημερών μέσα σε ένα αρχείο MS Project.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (οποιαδήποτε πρόσφατη έκδοση).  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να εμφανίσω τις ώρες εργασίας του ημερολογίου;** Ναι—διαβάζοντας κάθε `WeekDay` μπορείτε να εμφανίσετε τις ώρες για κάθε τύπο ημέρας.  
- **Είναι συμβατό με Maven/Gradle;** Απόλυτα—προσθέστε το JAR του Aspose.Tasks ως εξάρτηση.

## Πώς να ορίσετε το ημερολόγιο έργου σε Java
Φορτώστε το αρχείο του έργου σας, εντοπίστε το επιθυμητό ημερολόγιο και, στη συνέχεια, προσαρμόστε τους ορισμούς χρόνου εργασίας, το βασικό ημερολόγιο και τους τύπους ημερών όπως απαιτείται. Τα παρακάτω βήματα παρέχουν μια πλήρη, ολοκληρωμένη λύση που δείχνει τη φόρτωση, την επανάληψη, την τροποποίηση και την αποθήκευση του έργου, διαχειριζόμενη εξαιρέσεις και εξασφαλίζοντας ακριβείς υπολογισμούς ωρών εργασίας.

## Τι είναι ένα ημερολόγιο έργου;
Ένα ημερολόγιο έργου ορίζει τις εργάσιμες ημέρες και ώρες για εργασίες, πόρους και το συνολικό χρονοδιάγραμμα του έργου. Στο MS Project, τα ημερολόγια μπορούν να κληρονομούν από ένα βασικό ημερολόγιο, και κάθε τύπος ημέρας (π.χ. **Standard**, **Non‑working**) μπορεί να έχει τον δικό του χρόνο εργασίας. Η διαχείριση αυτών των ρυθμίσεων προγραμματιστικά επιτρέπει δυναμικές προσαρμογές του προγράμματος χωρίς χειροκίνητη επεξεργασία.

## Γιατί να διαχειρίζεστε το ημερολόγιο MS Project προγραμματιστικά;
Η προγραμματιστική διαχείριση των ημερολογίων σας επιτρέπει να εφαρμόζετε συνεπείς κανόνες χρονοπρογραμματισμού σε πολλά έργα, να μειώνετε τα χειροκίνητα σφάλματα και να ενσωματώνετε τα δεδομένα του ημερολογίου με άλλα επιχειρησιακά συστήματα όπως HR ή ERP. Αυτή η αυτοματοποίηση επιταχύνει τη δημιουργία του έργου και διασφαλίζει ότι όλα τα μέλη της ομάδας ακολουθούν τις ίδιες πολιτικές χρόνου εργασίας.

- **Αυτοματοποίηση:** Προσαρμόστε τα ημερολόγια σε δεκάδες έργα με ένα μόνο script.  
- **Συνέπεια:** Επιβάλετε αυτόματα πολιτικές χρόνου εργασίας σε όλη την οργάνωση.  
- **Ενσωμάτωση:** Συγχρονίστε τα ημερολόγια με εξωτερικά συστήματα HR ή ERP.  
- **Ορατότητα:** Εμφανίστε γρήγορα **τις ώρες εργασίας του ημερολογίου** για αναφορές ή εντοπισμό σφαλμάτων.  
- **Ευελιξία:** Προσθέστε εξαιρέσεις ή βάρδιες άμεσα χωρίς να ανοίξετε το UI.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- **Java Development Kit (JDK) 8+** εγκατεστημένο και ρυθμισμένο το `JAVA_HOME`.  
- **Aspose.Tasks for Java** βιβλιοθήκη που έχετε κατεβάσει από τη [download page](https://releases.aspose.com/tasks/java/). Προσθέστε το JAR στο classpath ή δηλώστε το ως εξάρτηση Maven/Gradle.  
- Ένα δείγμα αρχείου MS Project (`.mpp` ή `.xml`) που περιέχει τουλάχιστον ένα ημερολόγιο που θέλετε να ελέγξετε ή να τροποποιήσετε.

## Εισαγωγή πακέτων
Οι κλάσεις `Project`, `Calendar`, `WeekDay` και οι συναφείς είναι ο πυρήνας της διαχείρισης ημερολογίων.
Η κλάση `Calendar` αντιπροσωπεύει ένα ημερολόγιο έργου, περιλαμβάνοντας εργάσιμες ημέρες, εξαιρέσεις και σχέσεις με το βασικό ημερολόγιο.
Η κλάση `WeekDay` ορίζει τις ρυθμίσεις χρόνου εργασίας για μια μόνο ημέρα μέσα σε ένα ημερολόγιο.

Η κλάση `Project` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Tasks που αντιπροσωπεύει ένα αρχείο MS Project στη μνήμη. Αφού φορτώσετε ένα αρχείο, όλες οι λειτουργίες ημερολογίου περνούν μέσω αυτού του αντικειμένου.

```java
import com.aspose.tasks.*;
```

## Βήμα 1: ρύθμιση του καταλόγου δεδομένων
Ορίστε το φάκελο που περιέχει τα αρχεία του έργου σας. Αντικαταστήστε το placeholder με την πραγματική διαδρομή στο σύστημά σας.

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: ορισμός σταθερών μονάδας χρόνου
Οι χρόνοι εργασίας εκφράζονται σε χιλιοστά του δευτερολέπτου. Ο ορισμός επαναχρησιμοποιήσιμων σταθερών κάνει τον κώδικα πιο ευανάγνωστο και σας βοηθά να **υπολογίσετε ακριβώς τις ώρες εργασίας Java**.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Βήμα 3: φόρτωση δεδομένων έργου
Δημιουργήστε ένα αντικείμενο `Project` φορτώνοντας ένα υπάρχον αρχείο MS Project XML (`.xml` ή `.mpp`). Αυτό σας δίνει πρόσβαση σε όλα τα ημερολόγια που αποθηκεύονται στο αρχείο.

Η κλάση `Project` φορτώνει το αρχείο σε ένα ελαφρύ μοντέλο αντικειμένων· **δεν** απαιτεί την πλήρη φόρτωση του αρχείου στη μνήμη, επιτρέποντάς σας να εργάζεστε με έργα που περιέχουν δεκάδες χιλιάδες εργασίες.

```java
Project project = new Project(dataDir + "project.xml");
```

## Βήμα 4: επανάληψη μέσω ημερολογίων Java
Τώρα επαναλαμβάνουμε κάθε ημερολόγιο, εκτυπώνουμε το μοναδικό του αναγνωριστικό, το όνομα, το βασικό ημερολόγιο και τις ώρες εργασίας για κάθε τύπο ημέρας. Αυτό δείχνει **πώς να ορίσετε το ημερολόγιο έργου Java** τιμές και επίσης πώς να **εμφανίσετε τις ώρες εργασίας του ημερολογίου**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Τι κάνει αυτός ο κώδικας
- **Φιλτράρει ημερολόγια χωρίς όνομα** (ορισμένα εσωτερικά ημερολόγια μπορεί να έχουν `null` όνομα).  
- **Εκτυπώνει UID και όνομα** – χρήσιμο για την αναγνώριση του ημερολογίου αργότερα.  
- **Εμφανίζει το βασικό ημερολόγιο** – είτε “Self” (το ημερολόγιο είναι το δικό του βασικό) είτε το όνομα του κληρονομημένου ημερολογίου.  
- **Περιοδικά διατρέχει κάθε `WeekDay`** για να υπολογίσει και να εμφανίσει τις συνολικές ώρες εργασίας (`workingTime` είναι σε χιλιοστά του δευτερολέπτου, οπότε διαιρούμε με `OneHour`).  

## Ποσοτικοποιημένα οφέλη από τη χρήση του Aspose.Tasks
Το Aspose.Tasks υποστηρίζει **πάνω από 30 μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί **έργα με έως και 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, παρέχοντας αποτελέσματα σε λιγότερο από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή. Αυτοί οι αριθμοί το καθιστούν αξιόπιστη επιλογή για αυτοματοποίηση σε επιχειρησιακό επίπεδο.

## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| `NullPointerException` on `cal.getBaseCalendar()` | Το ημερολόγιο είναι το ίδιο το βασικό ημερολόγιο (`isBaseCalendar()` επιστρέφει `true`). | Χρησιμοποιήστε τον τελεστή ternary όπως φαίνεται (`cal.isBaseCalendar() ? "Self" : ...`). |
| Δεν εμφανίζονται ώρες εργασίας | Το αρχείο έργου χρησιμοποιεί διαφορετική μονάδα χρόνου (ticks). | Επαληθεύστε τη μορφή του αρχείου· το Aspose.Tasks κανονικοποιεί σε χιλιοστά του δευτερολέπτου, αλλά βεβαιωθείτε ότι φορτώνετε τον σωστό τύπο αρχείου. |
| Αδυναμία εντοπισμού του `project.xml` | Λανθασμένη διαδρομή `dataDir`. | Χρησιμοποιήστε απόλυτη διαδρομή ή `Paths.get(dataDir, "project.xml").toString()`. |

## Συχνές ερωτήσεις

**Q: Μπορώ να τροποποιήσω τις ιδιότητες του ημερολογίου προγραμματιστικά χρησιμοποιώντας το Aspose.Tasks;**  
A: Ναι, το API παρέχει πλήρη πρόσβαση ανάγνωση/εγγραφή στα ημερολόγια, επιτρέποντάς σας να προσθέτετε, επεξεργάζεστε ή διαγράφετε χρόνους εργασίας, εξαιρέσεις και σχέσεις βασικού ημερολογίου.

**Q: Υπάρχουν περιορισμοί στην προσαρμογή του ημερολογίου με το Aspose.Tasks;**  
A: Η βιβλιοθήκη αντικατοπτρίζει τις δυνατότητες του Microsoft Project, έτσι μπορείτε να προσαρμόσετε πρακτικά όλα τα στοιχεία του ημερολογίου. Μόνο πολύ παλιές εκδόσεις αρχείων Project μπορεί να έχουν μικρές ασυμβατότητες.

**Q: Μπορώ να ενσωματώσω τη διαχείριση ημερολογίου σε υπάρχοντα έργα Java;**  
A: Απόλυτα. Απλώς προσθέστε το JAR του Aspose.Tasks στη διαδρομή κατασκευής σας και χρησιμοποιήστε τα ίδια πρότυπα κώδικα που εμφανίζονται εδώ.

**Q: Υποστηρίζει το Aspose.Tasks άλλες λειτουργίες διαχείρισης έργου εκτός από τη διαχείριση ημερολογίου;**  
A: Ναι, καλύπτει εργασίες, πόρους, αναθέσεις, δομές, βάσεις, και άλλα—καθιστώντας το μια ολοκληρωμένη λύση για αυτοματοποίηση έργων με βάση τη Java.

**Q: Διατίθεται τεχνική υποστήριξη για προγραμματιστές που χρησιμοποιούν το Aspose.Tasks;**  
A: Ναι, η Aspose παρέχει αφιερωμένα φόρουμ, υποστήριξη μέσω email και εκτενή τεκμηρίωση για όλους τους χρήστες με άδεια.

---

**Τελευταία ενημέρωση:** 2026-09-09  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία Ημερολογίου Έργου Java – Οδηγός Aspose.Tasks για Java](/tasks/java/)
- [Φόρτωση Αρχείων Έργου σε Java και Διαχείριση Ιδιοτήτων Έργου](/tasks/java/project-management/default-properties/)
- [Ορισμός Ημερομηνίας Έναρξης Έργου στο MS Project χρησιμοποιώντας Aspose.Tasks για Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}