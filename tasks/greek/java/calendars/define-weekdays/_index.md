---
date: 2025-12-02
description: Μάθετε πώς να ορίζετε το ημερολόγιο, να καθορίζετε τις εργάσιμες ημέρες
  στο MS Project και να ορίζετε προσαρμοσμένες εργάσιμες ημέρες χρησιμοποιώντας το
  Aspose.Tasks για Java. Αποθηκεύστε το έργο ως XML με λίγες μόνο γραμμές κώδικα.
language: el
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να ορίσετε το ημερολόγιο και να καθορίσετε τις ημέρες της εβδομάδας στο
  MS Project με το Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Ορίσετε Ημερολόγιο και Ημέρες Εβδομάδας στο MS Project με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε **πώς να ορίσετε ρυθμίσεις ημερολογίου** προγραμματιστικά και να ορίσετε τις ημέρες της εβδομάδας σε ένα αρχείο Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε χρειάζεστε να δημιουργήσετε μια τυπική εργάσιμη εβδομάδα, να προσθέσετε εργάσιμες ημέρες Σαββατοκύριακου, είτε να διαμορφώσετε ένα σύντομο πρόγραμμα Παρασκευής, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα—from τη δημιουργία του έργου μέχρι την αποθήκευση του αρχείου ως XML.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java  
- **Μπορώ να προσθέσω εργάσιμες ημέρες Σαββατοκύριακου;** Ναι – απλώς προσθέστε Σάββατο και Κυριακή ως εργάσιμες ημέρες.  
- **Πώς αποθηκεύω το έργο;** Χρησιμοποιήστε `prj.save(..., SaveFileFormat.Xml)`.  
- **Χρειάζεται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται άδεια για παραγωγή.  
- **Ποια έκδοση Java απαιτείται;** Java 8 ή νεότερη.

## Τι σημαίνει “πώς να ορίσετε ημερολόγιο” στο πλαίσιο του MS Project;
Η ρύθμιση ενός ημερολογίου στο MS Project σημαίνει τον ορισμό των εργάσιμων ημερών, των ημερήσιων ωρών εργασίας και τυχόν εξαιρέσεων όπως αργίες. Αυτό το ημερολόγιο καθοδηγεί τον προγραμματισμό εργασιών, την κατανομή πόρων και τις συνολικές χρονικές γραμμές του έργου.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για τη διαχείριση ημερολογίου;
- **Πλήρης έλεγχος** – δημιουργήστε, τροποποιήστε ή διαγράψτε ημερολόγια προγραμματιστικά χωρίς να ανοίξετε το UI.  
- **Διαπλατφορμικό** – λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java.  
- **Υποστηρίζει όλες τις μορφές αρχείων** – MPP, MPT και XML, ώστε να μπορείτε *να αποθηκεύσετε το έργο ως XML* για εύκολη ενσωμάτωση με άλλα συστήματα.  
- **Χωρίς εξαρτήσεις COM** – σε αντίθεση με τη βιβλιοθήκη Microsoft Project Interop.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK) 8+** – κατεβάστε το από την [ιστοσελίδα της Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – αποκτήστε το τελευταίο JAR από τη [σελίδα λήψης Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Ένα IDE ή εργαλείο κατασκευής (Maven/Gradle) για να προσθέσετε το JAR του Aspose.Tasks στο classpath του έργου σας.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Αυτές οι εισαγωγές σας δίνουν πρόσβαση σε αντικείμενα project, calendar και working‑time.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Δημιουργία Αντικειμένου Project
Δημιουργήστε ένα νέο αντικείμενο `Project`. Αυτό το αντικείμενο αντιπροσωπεύει το αρχείο MS Project που θα επεξεργαστείτε.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Βήμα 2: Ορισμός Νέου Ημερολογίου
Προσθέστε ένα φρέσκο ημερολόγιο στο έργο. Η ανάθεση ενός σαφούς ονόματος βοηθά όταν έχετε πολλά ημερολόγια.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Βήμα 3: Προσθήκη Τυπικών Εργάσιμων Ημερών (Δευτέρα‑Πέμπτη)
Χρησιμοποιήστε τη βοηθητική μέθοδο `WeekDay.createDefaultWorkingDay` για να ορίσετε το προεπιλεγμένο πρόγραμμα 9 π.‑5 μ. για την κύρια εργάσιμη εβδομάδα.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Βήμα 4: Προσθήκη Εργάσιμων Ημερών Σαββατοκύριακου
Αν το έργο σας λειτουργεί και τα Σαββατοκύριακα, απλώς προσθέστε Σάββατο και Κυριακή ως κανονικές εργάσιμες ημέρες. Αυτό δείχνει **προσθήκη εργάσιμων ημερών Σαββατοκύριακου**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Βήμα 5: Ορισμός Προσαρμοσμένης Σύντομης Εργάσιμης Ημέρας (Παρασκευή)
Εδώ **ορίζουμε προσαρμοσμένες εργάσιμες ημέρες** για την Παρασκευή: μια πρωινή βάρδια (9 π.‑12 μ.) και μια απογευματινή βάρδια (1 μ.‑4 μ.).

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

### Βήμα 6: Αποθήκευση του Έργου ως XML
Τέλος, αποθηκεύστε τις αλλαγές. Η επιλογή `SaveFileFormat.Xml` σας επιτρέπει να **αποθηκεύσετε το έργο ως XML**, κάτι που είναι χρήσιμο για ενσωμάτωση με άλλα εργαλεία.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Συνηθισμένα Προβλήματα & Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Οι ώρες εργασίας δεν εφαρμόζονται** | Βεβαιωθείτε ότι καλείται `setDayWorking(true)` στο προσαρμοσμένο `WeekDay`. |
| **Το αρχείο δεν βρέθηκε κατά την αποθήκευση** | Επαληθεύστε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι η εφαρμογή έχει δικαιώματα εγγραφής. |
| **Το ημερολόγιο δεν αντικατοπτρίζεται στις εργασίες** | Αναθέστε το νέο ημερολόγιο σε πόρους ή εργασίες χρησιμοποιώντας `task.setCalendar(cal)`. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να ορίσω προσαρμοσμένες μη‑εργάσιμες ημέρες χρησιμοποιώντας το Aspose.Tasks for Java;**  
Α: Ναι. Ορίστε την ιδιότητα `DayWorking` σε `false` για οποιοδήποτε `WeekDay` θέλετε να θεωρήσετε μη‑εργάσιμη ημέρα.

**Ε: Πώς μπορώ να προσθέσω αργίες ή εταιρικές εξαιρέσεις;**  
Α: Δημιουργήστε αντικείμενα `CalendarException`, καθορίστε τις ημερομηνίες εξαίρεσης και προσθέστε τα στο `cal.getExceptions()`.

**Ε: Είναι η βιβλιοθήκη συμβατή με παλαιότερες εκδόσεις του MS Project;**  
Α: Απόλυτα. Το Aspose.Tasks υποστηρίζει μορφές MPP, MPT και XML σε πολλαπλές εκδόσεις του Project.

**Ε: Μπορώ να τροποποιήσω υπάρχον ημερολόγιο σε εισαγόμενο έργο;**  
Α: Φορτώστε το έργο με `new Project("existing.mpp")`, ανακτήστε το επιθυμητό ημερολόγιο, κάντε τις αλλαγές και αποθηκεύστε.

**Ε: Το Aspose.Tasks διαχειρίζεται και επαναλαμβανόμενες εργασίες;**  
Α: Ναι, μπορείτε να δημιουργήσετε και να επεξεργαστείτε επαναλαμβανόμενες εργασίες χρησιμοποιώντας την κλάση `RecurringTask`.

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να ορίσετε ρυθμίσεις ημερολογίου**, **πώς να ορίσετε ημέρες εβδομάδας στο MS Project**, να προσθέσετε εργάσιμες ημέρες Σαββατοκύριακου και να δημιουργήσετε ένα σύντομο πρόγραμμα Παρασκευής—όλα με το Aspose.Tasks for Java. Αποθηκεύστε το αποτέλεσμα ως XML και ενσωματώστε τη λογική του ημερολογίου σε οποιαδήποτε λύση διαχείρισης έργων βασισμένη σε Java.

---

**Τελευταία Ενημέρωση:** 2025-12-02  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}