---
title: Διαβάστε τις Εβδομάδες Εργασίας από το MS Project Calendar με το Aspose.Tasks
linktitle: Διαβάστε τις Εβδομάδες Εργασίας από το Ημερολόγιο με το Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαβάζετε εργάσιμες εβδομάδες από το ημερολόγιο MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Λάβετε οδηγίες βήμα προς βήμα σε αυτό το περιεκτικό σεμινάριο.
weight: 15
url: /el/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε τις Εβδομάδες Εργασίας από το MS Project Calendar με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χρησιμοποιήσετε το Aspose.Tasks για Java για την ανάγνωση πληροφοριών εβδομάδων εργασίας από ένα ημερολόγιο Microsoft Project. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που σας επιτρέπει να χειρίζεστε και να διαχειρίζεστε έγγραφα του Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Λήψη και εγκατάσταση του Aspose.Tasks για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα για να ξεκινήσουμε με τον κώδικά μας:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Βήμα 1: Ρύθμιση του καταλόγου δεδομένων σας
Ρυθμίστε τη διαδρομή καταλόγου όπου βρίσκεται το αρχείο MS Project:
```java
String dataDir = "Your Data Directory";
```
## Βήμα 2: Δημιουργία παρουσίας έργου και πρόσβαση στο Ημερολόγιο
Δημιουργήστε μια νέα παρουσία της τάξης Project και αποκτήστε πρόσβαση στη συλλογή ημερολογίου και εβδομάδων εργασίας:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Βήμα 3: Επανάληψη κατά τη διάρκεια των εβδομάδων εργασίας
Επαναλάβετε τη συλλογή των εβδομάδων εργασίας και εμφανίστε τις πληροφορίες τους:
```java
for (WorkWeek workWeek : collection) {
    // Εμφάνιση ονόματος εβδομάδας εργασίας, από και έως ημερομηνίες
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Πρόσβαση σε εβδομαδιαίες ώρες και ώρες εργασίας
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Περαιτέρω χρόνοι εργασίας διαδικασίας, εάν χρειάζεται
    }
}
```
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαβάζουμε πληροφορίες εργάσιμων εβδομάδων από ένα ημερολόγιο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η ισχυρή βιβλιοθήκη επιτρέπει την απρόσκοπτη διαχείριση των αρχείων Project, επιτρέποντας στους προγραμματιστές να αυτοματοποιούν αποτελεσματικά διάφορες εργασίες.
## Συχνές ερωτήσεις
### Μπορώ να τροποποιήσω τις πληροφορίες εργάσιμων εβδομάδων χρησιμοποιώντας το Aspose.Tasks για Java;
Ναι, το Aspose.Tasks παρέχει API για τροποποίηση, προσθήκη ή διαγραφή εβδομάδων εργασίας και των σχετικών πληροφοριών τους.
### Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP και XML.
### Μπορώ να ενσωματώσω το Aspose.Tasks με άλλα πλαίσια Java;
Οπωσδήποτε, το Aspose.Tasks μπορεί να ενσωματωθεί απρόσκοπτα με άλλα πλαίσια Java και βιβλιοθήκες για βελτιωμένη λειτουργικότητα.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;
Μπορείτε να βρείτε υποστήριξη και βοήθεια στο φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
