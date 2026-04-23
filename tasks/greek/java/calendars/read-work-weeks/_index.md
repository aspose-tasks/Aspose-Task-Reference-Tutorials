---
date: 2026-02-05
description: Μάθετε πώς να διαβάζετε τις εβδομάδες εργασίας Java από ένα ημερολόγιο
  Microsoft Project χρησιμοποιώντας το Aspose.Tasks. Ακολουθήστε τον οδηγό βήμα‑προς‑βήμα
  με πλήρη παραδείγματα κώδικα.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να διαβάσετε τις εβδομάδες εργασίας Java από το ημερολόγιο MS Project Aspose.Tasks
url: /el/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαβάσετε τις Εργάσιμες Εβδομάδες Java από το Ημερολόγιο MS Project Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο θα **μάθετε πώς να διαβάζετε τις εργάσιμες εβδομάδες Java** από ένα ημερολόγιο Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks. Είτε δημιουργείτε ένα εργαλείο αναφοράς, συγχρονίζετε χρονοδιαγράμματα ή αυτοματοποιείτε την εξαγωγή δεδομένων έργου, η δυνατότητα προγραμματιστικής πρόσβασης στους ορισμούς των εργασιακών εβδομάδων εξοικονομεί αμέτρητες χειροκίνητες ώρες. Θα περάσουμε από τη απαιτούμενη ρύθμιση, θα σας δείξουμε τον ακριβή κώδικα για την ανάκτηση των λεπτομερειών των εργασιακών εβδομάδων και θα εξηγήσουμε κάθε βήμα ώστε να προσαρμόσετε τη λύση στα δικά σας έργα.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “read workweeks java”;** Αναφέρεται στην εξαγωγή των ορισμών των εργασιακών εβδομάδων από ένα αρχείο Project χρησιμοποιώντας κώδικα Java.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (διατίθεται δωρεάν δοκιμαστική έκδοση).  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δοκιμαστική έκδοση λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια μορφές αρχείων υποστηρίζονται;** Τanto *.mpp* όσο και αρχεία Project XML υποστηρίζονται.  
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως λιγότερο από 10 λεπτά μόλις ρυθμιστεί η βιβλιοθήκη.

## Πώς να Διαβάσετε τις Εργάσιμες Εβδομάδες Java από ένα Ημερολόγιο Microsoft Project
Η ανάγνωση των εργασιακών εβδομάδων σε Java σημαίνει τη χρήση του API Aspose.Tasks για πρόσβαση στη `WorkWeekCollection` ενός αντικειμένου ημερολογίου μέσα σε ένα αρχείο Microsoft Project. Κάθε `WorkWeek` περιέχει τις ημερομηνίες έναρξης/λήξης και τους καθημερινούς ορισμούς χρόνου εργασίας που καθορίζουν πώς προγραμματίζονται οι πόροι.

## Γιατί να διαβάζετε τις εργασιακές εβδομάδες Java από ένα ημερολόγιο Microsoft Project;
- **Αυτοματοποίηση:** Απενεργοποιήστε την χειροκίνητη αντιγραφή‑επικόλληση δεδομένων χρονοδιαγράμματος.  
- **Ενσωμάτωση:** Ενσωματώστε τις πληροφορίες των εργασιακών εβδομάδων σε συστήματα ERP, HR ή προσαρμοσμένα συστήματα αναφοράς.  
- **Συνέπεια:** Διασφαλίστε ότι όλα τα επόμενα εργαλεία σέβονται τους ίδιους κανόνες ημερολογίου που ορίζονται στο αρχείο Project.

## Προαπαιτούμενα
Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – εγκατεστημένη έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το πιο πρόσφατο JAR από την επίσημη ιστοσελίδα: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Ένα **δείγμα αρχείου Project** (`ReadWorkWeeksInformation.mpp`) τοποθετημένο σε γνωστό φάκελο.

## Εισαγωγή Πακέτων
Αρχικά, εισάγετε τις κλάσεις που θα χρειαστούμε για αλληλεπίδραση με ημερολόγια και εργασιακές εβδομάδες:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Βήμα 1: Ρυθμίστε τον Κατάλογο Δεδομένων σας
Ορίστε το φάκελο που περιέχει το αρχείο `.mpp`. Αντικαταστήστε το σύμβολο κράτησης θέσης με την πραγματική διαδρομή στο σύστημά σας:

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Δημιουργήστε ένα Αντικείμενο Project και Πρόσβαση στο Ημερολόγιο
Δημιουργήστε ένα αντικείμενο `Project`, επιλέξτε το ημερολόγιο που θέλετε (με UID) και αποκτήστε τη `WorkWeekCollection` του:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Συμβουλή:** Αν δεν είστε σίγουροι για το UID του ημερολογίου, μπορείτε να επαναλάβετε μέσω του `project.getCalendars()` και να εκτυπώσετε το όνομα και το UID κάθε ημερολογίου.

## Βήμα 3: Επανάληψη μέσω των Εργατικών Εβδομάδων
Κάντε βρόχο σε κάθε `WorkWeek` για να εμφανίσετε το όνομα, τις ημερομηνίες έναρξης/λήξης και τις καθημερινές ώρες εργασίας:

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

**Τι θα δείτε:** Η κονσόλα εκτυπώνει την ετικέτα κάθε εργασιακής εβδομάδας (π.χ., “Standard”), το εύρος ημερομηνιών ισχύος της, και μπορείτε να εμβαθύνετε στις ακριβείς ώρες εργασίας για κάθε ημέρα.

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| `NullPointerException` κατά την πρόσβαση στο `calendar` | Λάθος UID ή το ημερολόγιο δεν υπάρχει | Επαληθεύστε το UID με `project.getCalendars().size()` και πρώτα εμφανίστε τα διαθέσιμα ημερολόγια. |
| Δεν υπάρχει έξοδος για τις εργασιακές εβδομάδες | Το επιλεγμένο ημερολόγιο δεν έχει προσαρμοσμένες εργασιακές εβδομάδες (χρησιμοποιεί το προεπιλεγμένο) | Χρησιμοποιήστε το προεπιλεγμένο ημερολόγιο (`project.getDefaultCalendar()`) ή δημιουργήστε μια εργασιακή εβδομάδα προγραμματιστικά. |
| Η μορφή ημερομηνίας φαίνεται περίεργη | `System.out.println` χρησιμοποιεί την προεπιλεγμένη μορφή `java.util.Date` | Εφαρμόστε ένα `SimpleDateFormat` για να μορφοποιήσετε τις ημερομηνίες όπως χρειάζεται. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να τροποποιήσω τις πληροφορίες των εργασιακών εβδομάδων χρησιμοποιώντας το Aspose.Tasks for Java;**  
A: Ναι. Το API παρέχει μεθόδους όπως `addWorkWeek()`, `removeWorkWeek()`, και setters ιδιοτήτων για αλλαγή ονομάτων, ημερομηνιών και ωρών εργασίας.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;**  
A: Απόλυτα. Υποστηρίζει αρχεία MPP από το Project 98 έως τις πιο πρόσφατες εκδόσεις, καθώς και αρχεία Project XML.

**Q: Μπορώ να ενσωματώσω το Aspose.Tasks με άλλα Java frameworks;**  
A: Ναι. Η βιβλιοθήκη είναι καθαρά Java, έτσι μπορείτε να τη χρησιμοποιήσετε μαζί με Spring, Jakarta EE ή οποιοδήποτε άλλο framework.

**Q: Υπάρχει δοκιμαστική έκδοση του Aspose.Tasks;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση 30 ημερών από την επίσημη ιστοσελίδα: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;**  
A: Το φόρουμ της κοινότητας Aspose είναι το καλύτερο μέρος: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Τώρα έχετε κατακτήσει **πώς να διαβάζετε τις εργασιακές εβδομάδες Java** χρησιμοποιώντας το Aspose.Tasks. Ακολουθώντας τα παραπάνω βήματα μπορείτε προγραμματιστικά να εξάγετε τους ορισμούς των εργασιακών εβδομάδων από οποιοδήποτε ημερολόγιο MS Project, να ενσωματώσετε αυτά τα δεδομένα στις εφαρμογές σας και να αυτοματοποιήσετε τις ροές εργασίας που σχετίζονται με το χρονοδιάγραμμα. Μη διστάσετε να πειραματιστείτε με τη δημιουργία ή την ενημέρωση εργασιακών εβδομάδων—το Aspose.Tasks το κάνει απλό.

---

**Τελευταία Ενημέρωση:** 2026-02-05  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}