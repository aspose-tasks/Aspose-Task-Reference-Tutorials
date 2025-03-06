---
title: Ανάκτηση πληροφοριών ημερολογίου έργου MS στο Aspose.Tasks
linktitle: Ανάκτηση πληροφοριών ημερολογίου στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ανακτάτε πληροφορίες ημερολογίου MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα προς βήμα για πρόσβαση σε λεπτομέρειες ημερολογίου μέσω προγραμματισμού.
weight: 14
url: /el/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάκτηση πληροφοριών ημερολογίου έργου MS στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να ανακτήσετε πληροφορίες ημερολογίου από αρχεία Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Το Aspose.Tasks παρέχει ισχυρές δυνατότητες για τον χειρισμό δεδομένων έργου, συμπεριλαμβανομένης της πρόσβασης σε λεπτομέρειες ημερολογίου, όπως εργάσιμες ημέρες και ώρες.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
- Βασικές γνώσεις προγραμματισμού Java.
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
-  Aspose.Tasks για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα στον κώδικα Java σας για να χρησιμοποιήσετε τις λειτουργίες Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Τώρα ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα για καλύτερη κατανόηση.
## Βήμα 1: Ορισμός καταλόγου δεδομένων
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο αρχείων του έργου σας.
## Βήμα 2: Καθορισμός μονάδων χρόνου
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Αυτές οι σταθερές αντιπροσωπεύουν μονάδες χρόνου σε μικροδευτερόλεπτα.
## Βήμα 3: Δημιουργία παρουσίας έργου
```java
Project project = new Project(dataDir + "project.mpp");
```
 Αυτή η γραμμή δημιουργεί ένα παράδειγμα του`Project` κλάση, αρχικοποιώντας την με τη διαδρομή προς το αρχείο του έργου (`project.mpp`).
## Βήμα 4: Ανάκτηση πληροφοριών ημερολογίων
```java
CalendarCollection alCals = project.getCalendars();
```
Εδώ, ανακτούμε μια συλλογή από ημερολόγια που υπάρχουν στο αρχείο του έργου.
## Βήμα 5: Επανάληψη μέσω ημερολογίων
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Πληροφορίες Ημερολογίου
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Επανάληψη κατά τη διάρκεια της εβδομάδας
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Χρόνος σε χιλιοστά του δευτερολέπτου
            double time = ts / (OneHour); // Μετατροπή σε ώρες
            if (wd.getDayWorking()) {
                // Εμφάνιση εργάσιμων ημερών και ωρών
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Αυτός ο βρόχος επαναλαμβάνεται σε κάθε ημερολόγιο και εκτυπώνει το UID, το όνομα και τις εργάσιμες ημέρες με τις αντίστοιχες ώρες εργασίας.
## Βήμα 6: Εμφάνιση μηνύματος ολοκλήρωσης
```java
System.out.println("Process completed Successfully");
```
Τέλος, εμφανίζεται ένα μήνυμα που υποδεικνύει την ολοκλήρωση της διαδικασίας.
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ανακτούμε πληροφορίες ημερολογίου από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να έχετε αποτελεσματική πρόσβαση και να χειρίζεστε δεδομένα έργου στις εφαρμογές σας Java.

## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
Α: Ναι, το Aspose.Tasks υποστηρίζει πολλές πλατφόρμες και γλώσσες προγραμματισμού, συμπεριλαμβανομένων των .NET, C++, Python και Java.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης από[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια για το Aspose.Tasks;
 Α: Ναι, οι προσωρινές άδειες είναι διαθέσιμες για αγορά[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks;
 Α: Μπορείτε να ανατρέξετε στην τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
