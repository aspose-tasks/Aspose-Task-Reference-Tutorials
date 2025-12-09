---
date: 2025-12-05
description: Μάθετε πώς να προσδιορίζετε τις εργάσιμες ημέρες και να υπολογίζετε τη
  διάρκεια των εργασιών εξάγοντας τις εργάσιμες ώρες από τα ημερολόγια του MS Project
  χρησιμοποιώντας το Aspose.Tasks για Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Καθορίστε τις εργάσιμες ημέρες και τις εργάσιμες ώρες με το Aspose.Tasks
url: /el/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσδιορισμός Ημερών Εργασίας & Ωρών Εργασίας με το Aspose.Tasks

## Εισαγωγή
Η διαχείριση των ημερολογίων έργου αποτελεί βασικό μέρος της επιτυχημένης προγραμματισμού έργου. Σε αυτό το σεμινάριο θα **προσδιορίσετε τις ημέρες εργασίας** για οποιαδήποτε εργασία και θα **εξάγετε τις ώρες εργασίας** από ένα ημερολόγιο MS Project χρησιμοποιώντας το Aspose.Tasks for Java. Στο τέλος του οδηγού θα μπορείτε να **υπολογίσετε τη διάρκεια της εργασίας**, να προσαρμόσετε τις ώρες εργασίας και να **φορτώσετε αξιόπιστα ένα αρχείο MPP** για να ανακτήσετε τα δεδομένα που χρειάζεστε.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “determine working days”;** Σημαίνει την αναγνώριση των ημερομηνιών στο ημερολόγιο που θεωρούνται εργάσιμες ημέρες για μια συγκεκριμένη εργασία.  
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Το Aspose.Tasks for Java παρέχει ένα πλήρες API για εργασία με αρχεία MS Project.  
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως 10–15 λεπτά για μια βασική εξαγωγή.  
- **Χρειάζομαι άδεια;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Μπορώ να προσαρμόσω τις ώρες εργασίας;** Ναι – μπορείτε να τροποποιήσετε τα ημερολόγια, να προσθέσετε αργίες και να ορίσετε προσαρμοσμένα χρονικά διαστήματα εργασίας.

## Τι είναι το “determine working days”;
Όταν προγραμματίζεται μια εργασία, το ημερολόγιο του έργου ορίζει ποιες ημέρες είναι εργάσιμες και ποιες μη‑εργάσιμες (Σαββατοκύριακα, αργίες). Ο προσδιορισμός των ημερών εργασίας σημαίνει την ερώτηση σε αυτό το ημερολόγιο για να γνωρίζουμε ακριβώς πότε μπορεί να γίνει εργασία, κάτι που είναι ουσιώδες για ακριβείς υπολογισμούς **calculate task duration**.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για την ανάκτηση ωρών εργασίας;
- **Δεν απαιτείται Microsoft Project** – εργασία με αρχεία .MPP σε οποιαδήποτε πλατφόρμα.  
- **Πλήρης υποστήριξη ημερολογίων** – περιλαμβάνει προεπιλεγμένα, πόρων και εργασιών ημερολόγια.  
- **Υψηλή απόδοση** – επεξεργασία μεγάλων έργων γρήγορα.  
- **Εκτενής τεκμηρίωση** – παραδείγματα και αναφορά API είναι άμεσα διαθέσιμα.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το τελευταίο JAR από [here](https://releases.aspose.com/tasks/java/).  
3. Βασικές γνώσεις προγραμματισμού Java.  

## Εισαγωγή Πακέτων
First, import the core Aspose.Tasks namespace:

```java
import com.aspose.tasks.*;
```

## Βήμα 1: Φόρτωση του αρχείου MPP
Load your project file (the **load mpp file** step) so you can work with its calendars:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Βήμα 2: Ανάκτηση Πληροφοριών Εργασίας και Ημερολογίου
Pick the task you want to analyse and get its associated calendar. This is where we **retrieve working hours** for the task:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Βήμα 3: Ορισμός Ημερομηνιών Έναρξης και Λήξης
Set up the time window for which you want to **determine working days**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Βήμα 4: Επανάληψη Μέσω Ημερομηνιών
Loop through each date in the task’s duration. This loop will help us **customize working hours** later if needed:

```java
java.util.Calendar tempDate = calStartDate;
```

## Βήμα 5: Υπολογισμός Διάρκειας
During the iteration we check whether each day is a working day, sum the working hours, and finally compute the task’s duration in minutes, hours, and days:

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Task returns `null` for calendar** | Βεβαιωθείτε ότι η εργασία έχει πραγματικά ένα ημερολόγιο ανατεθειμένο· διαφορετικά κληρονομεί το προεπιλεγμένο ημερολόγιο του έργου. |
| **Incorrect duration because of holidays** | Επαληθεύστε ότι οι αργίες έχουν οριστεί στο ημερολόγιο της εργασίας ή στο βασικό ημερολόγιο του έργου. |
| **Time zone mismatch** | Χρησιμοποιήστε το `java.util.TimeZone` για να ευθυγραμμίσετε τη ζώνη ώρας του ημερολογίου με το σύστημά σας, εάν χρειάζεται. |

## Συχνές Ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks for Java να διαχειριστεί σύνθετες δομές έργου;
Α: Ναι, το Aspose.Tasks for Java παρέχει ολοκληρωμένη υποστήριξη για τη διαχείριση σύνθετων δομών έργου, συμπεριλαμβανομένων εργασιών, πόρων και ημερολογίων.

### Ε: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις του MS Project;
Α: Απόλυτα, το Aspose.Tasks for Java υποστηρίζει διάφορες εκδόσεις του MS Project, εξασφαλίζοντας συμβατότητα σε διαφορετικά περιβάλλοντα.

### Ε: Μπορώ να προσαρμόσω τις ώρες εργασίας και τις αργίες στα ημερολόγια του έργου;
Α: Ναι, μπορείτε εύκολα να προσαρμόσετε τις ώρες εργασίας και τις αργίες σύμφωνα με τις απαιτήσεις του έργου σας χρησιμοποιώντας τα APIs του Aspose.Tasks for Java.

### Ε: Παρέχει το Aspose.Tasks for Java υποστήριξη και τεκμηρίωση;
Α: Ναι, το Aspose.Tasks for Java παρέχει εκτενή τεκμηρίωση και αφιερωμένα φόρουμ υποστήριξης για να βοηθήσει τους προγραμματιστές να αξιοποιήσουν αποτελεσματικά τις δυνατότητές του.

### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks for Java;
Α: Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks for Java από [here](https://releases.aspose.com/).

## Συμπέρασμα
Σε αυτόν τον οδηγό δείξαμε πώς να **determine working days**, **retrieve working hours**, και **calculate task duration** από ένα ημερολόγιο MS Project χρησιμοποιώντας το Aspose.Tasks for Java. Ακολουθώντας τα παραπάνω βή μπορείτε να αυτοματοποιήσετε την ανάλυση του χρονοδιαγράμματος, να προσαρμόσετε τα ημερολόγια και να διατηρήσετε τα σχέδια του έργου σας ακριβή και ενημερωμένα.

---

**Τελευταία Ενημέρωση:** 2025-12-05  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}