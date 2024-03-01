---
title: Καθορίστε τις καθημερινές στο Ημερολόγιο με το Aspose.Tasks
linktitle: Καθορίστε τις καθημερινές στο Ημερολόγιο με το Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ορίζετε τις καθημερινές στο MS Project Calendar χρησιμοποιώντας το Aspose.Tasks για Java. Προσαρμόστε τις εργάσιμες ημέρες και τις ώρες χωρίς κόπο.
type: docs
weight: 12
url: /el/java/calendars/define-weekdays/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία καθορισμού των εργάσιμων ημερών σε ένα Ημερολόγιο Έργου MS χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το[Ιστοσελίδα Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) αν δεν το έχεις κάνει ήδη.
2.  Aspose.Tasks for Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/). Ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα που απαιτούνται για την εργασία με το Aspose.Tasks στο έργο σας Java:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Βήμα 1: Δημιουργήστε μια παρουσία έργου
Δημιουργήστε ένα αντικείμενο Project, το οποίο αντιπροσωπεύει το αρχείο MS Project με το οποίο θα εργαστείτε:
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Βήμα 2: Ορισμός Ημερολογίου
Δημιουργήστε μια νέα παρουσία ημερολογίου και προσθέστε την στο έργο:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Βήμα 3: Προσθήκη εργάσιμων ημερών
Καθορίστε τις εργάσιμες ημέρες προσθέτοντας από Δευτέρα έως Πέμπτη με προεπιλεγμένους χρόνους:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Βήμα 4: Ορίστε προσαρμοσμένη εργάσιμη ημέρα
Ορίστε το Σάββατο και την Κυριακή ως εργάσιμες ημέρες:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Βήμα 5: Ορίστε τη σύντομη εργάσιμη ημέρα
Ορίστε την Παρασκευή ως σύντομη εργάσιμη ημέρα με προσαρμοσμένες ώρες εργασίας:
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
## Βήμα 6: Αποθηκεύστε το έργο
Αποθηκεύστε το τροποποιημένο έργο σε ένα αρχείο XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## συμπέρασμα
Συγχαρητήρια! Έχετε ορίσει με επιτυχία τις καθημερινές σε ένα Ημερολόγιο Έργου MS χρησιμοποιώντας το Aspose.Tasks για Java. Τώρα μπορείτε να ενσωματώσετε αυτήν τη λειτουργία στις εφαρμογές σας Java για να χειρίζεστε αρχεία MS Project μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να ορίσω προσαρμοσμένες μη εργάσιμες ημέρες χρησιμοποιώντας το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να ορίσετε προσαρμοσμένες μη εργάσιμες ημέρες ορίζοντας το`DayWorking` ιδιοκτησία σε`false` για την αντίστοιχη καθημερινή.
### Ε2: Πώς μπορώ να προσθέσω αργίες στο ημερολόγιο;
 Α: Μπορείτε να προσθέσετε αργίες δημιουργώντας παρουσίες του`CalendarExceptions`και προσδιορίζοντας τις μη εργάσιμες ημερομηνίες.
### Ε3: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων MS Project;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Ε4: Μπορώ να τροποποιήσω τα υπάρχοντα ημερολόγια σε ένα αρχείο MS Project;
Α: Ναι, μπορείτε να φορτώσετε ένα υπάρχον έργο με ημερολόγια, να κάνετε τροποποιήσεις και, στη συνέχεια, να αποθηκεύσετε τις αλλαγές πίσω στο αρχικό αρχείο.
### Ε5: Το Aspose.Tasks παρέχει υποστήριξη για επαναλαμβανόμενες εργασίες;
Α: Ναι, το Aspose.Tasks σάς επιτρέπει να εργάζεστε με επαναλαμβανόμενες εργασίες, συμπεριλαμβανομένου του καθορισμού των μοτίβων και της διάρκειάς τους επανάληψης.