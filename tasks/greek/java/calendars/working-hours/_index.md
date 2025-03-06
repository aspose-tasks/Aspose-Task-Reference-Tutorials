---
title: Λάβετε Ώρες εργασίας από το Ημερολόγιο χρησιμοποιώντας το Aspose.Tasks
linktitle: Λάβετε Ώρες εργασίας από το Ημερολόγιο χρησιμοποιώντας το Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Εξάγετε εύκολα τις ώρες εργασίας από τα ημερολόγια του MS Project με το Aspose.Tasks για Java. Απλοποιήστε τις εργασίες διαχείρισης έργου.
weight: 13
url: /el/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Λάβετε Ώρες εργασίας από το Ημερολόγιο χρησιμοποιώντας το Aspose.Tasks

## Εισαγωγή
Η διαχείριση ημερολογίων έργων και η εξαγωγή ωρών εργασίας είναι απαραίτητα για την αποτελεσματική διαχείριση του έργου. Το Aspose.Tasks για Java παρέχει ισχυρή λειτουργικότητα για την ανάκτηση ωρών εργασίας από τα ημερολόγια του MS Project χωρίς κόπο. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Η βιβλιοθήκη Aspose.Tasks για Java έγινε λήψη και προσθήκη στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Βασική κατανόηση της γλώσσας προγραμματισμού Java.
## Εισαγωγή πακέτων
Αρχικά, εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks για Java:
```java
import com.aspose.tasks.*;
```
## Βήμα 1: Φόρτωση αρχείου έργου
Ξεκινήστε φορτώνοντας το αρχείο MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Βήμα 2: Ανάκτηση πληροφοριών εργασίας και ημερολογίου
Εξαγωγή λεπτομερειών εργασίας και ημερολογίου από το έργο:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Βήμα 3: Καθορίστε ημερομηνίες έναρξης και λήξης
Ρυθμίστε ημερομηνίες έναρξης και λήξης για την εργασία:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Βήμα 4: Επανάληψη μέσω ημερομηνιών
Επαναλάβετε τις ημερομηνίες εντός της διάρκειας της εργασίας:
```java
java.util.Calendar tempDate = calStartDate;
```
## Βήμα 5: Υπολογισμός Διάρκειας
Υπολογίστε τη διάρκεια σε λεπτά, ώρες και ημέρες:
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
## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε καλύψει πώς να ανακτήσετε τις ώρες εργασίας από ένα ημερολόγιο MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τα χρονοδιαγράμματα του έργου και να υπολογίσετε τη διάρκεια εργασιών με ευκολία.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί περίπλοκες δομές έργου;
Α: Ναι, το Aspose.Tasks για Java παρέχει ολοκληρωμένη υποστήριξη για το χειρισμό πολύπλοκων δομών έργων, συμπεριλαμβανομένων εργασιών, πόρων και ημερολογίων.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές εκδόσεις του MS Project;
Α: Απολύτως, το Aspose.Tasks για Java υποστηρίζει διάφορες εκδόσεις του MS Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.
### Ε: Μπορώ να προσαρμόσω τις ώρες εργασίας και τις αργίες στα ημερολόγια έργων;
Α: Ναι, μπορείτε εύκολα να προσαρμόσετε τις ώρες εργασίας και τις αργίες σύμφωνα με τις απαιτήσεις του έργου σας χρησιμοποιώντας το Aspose.Tasks για Java API.
### Ε: Το Aspose.Tasks για Java προσφέρει υποστήριξη και τεκμηρίωση;
Α: Ναι, το Aspose.Tasks για Java παρέχει εκτενή τεκμηρίωση και ειδικά φόρουμ υποστήριξης για να βοηθήσει τους προγραμματιστές να χρησιμοποιήσουν αποτελεσματικά τις δυνατότητές του.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να αποκτήσετε πρόσβαση σε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks για Java από[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
