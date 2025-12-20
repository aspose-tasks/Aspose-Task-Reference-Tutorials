---
date: 2025-12-20
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Tasks για να εξάγετε λεπτομέρειες
  ημερολογίου έργου από αρχεία Microsoft Project χρησιμοποιώντας Java. Οδηγός βήμα‑προς‑βήμα
  με παραδείγματα κώδικα.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να χρησιμοποιήσετε το Aspose.Tasks για την ανάκτηση πληροφοριών ημερολογίου
  του MS Project
url: /el/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το Aspose.Tasks για την ανάκτηση πληροφοριών ημερολογίου MS Project

## Introduction
Σε αυτό το tutorial, **θα ανακαλύψετε πώς να χρησιμοποιήσετε το Aspose.Tasks** για να ανακτήσετε προγραμματιστικά πληροφορίες ημερολογίου από αρχεία Microsoft Project. Η πρόσβαση σε δεδομένα ημερολογίου όπως εργάσιμες ημέρες, ώρες και εξαιρέσεις είναι απαραίτητη όταν χρειάζεται να **εξάγετε λεπτομέρειες ημερολογίου έργου** για αναφορές, ενσωμάτωση ή προσαρμοσμένη λογική προγραμματισμού. Ας προχωρήσουμε βήμα προς βήμα.

## Quick Answers
- **Ποια βιβλιοθήκη χρησιμοποιεί αυτό το tutorial;** Aspose.Tasks for Java.  
- **Ποια κύρια λέξη-κλειδί καλύπτεται;** *how to use aspose.tasks*.  
- **Τι μπορείτε να εξάγετε;** Ημερολόγια έργου, συμπεριλαμβανομένων των εργάσιμων ημερών και ωρών.  
- **Χρειάζομαι άδεια;** Διατίθεται δωρεάν δοκιμή· απαιτείται άδεια για παραγωγή.  
- **Ποια έκδοση της Java υποστηρίζεται;** Java 8 ή νεότερη.

## Why extract project calendar information?
Τα ημερολόγια έργου καθορίζουν τις ημερομηνίες των εργασιών, τις κατανομές πόρων και τους υπολογισμούς του συνολικού χρονοδιαγράμματος. Με την εξαγωγή αυτών των δεδομένων μπορείτε να:
- Δημιουργήσετε προσαρμοσμένες αναφορές που αντικατοπτρίζουν τα πραγματικά ωράρια εργασίας.  
- Συγχρονίσετε τα χρονοδιαγράμματα του Microsoft Project με εξωτερικά συστήματα (ERP, BI κ.λπ.).  
- Εκτελέσετε ανάλυση what‑if τροποποιώντας τις ρυθμίσεις του ημερολογίου προγραμματιστικά.

## Prerequisites
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού Java.  
- Εγκατεστημένο Java Development Kit (JDK) στο σύστημα σας.  
- Βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να τη κατεβάσετε από [here](https://releases.aspose.com/tasks/java/).

## Import Packages
Πρώτα, εισάγετε τις απαραίτητες κλάσεις Aspose.Tasks στο έργο Java σας.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
Ορίστε το φάκελο που περιέχει το αρχείο *.mpp* σας.

```java
String dataDir = "Your Data Directory";
```

Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή προς το φάκελο όπου βρίσκεται το **project.mpp**.

## Step 2: Define Time Units
Δημιουργήστε σταθερές που βοηθούν στη μετατροπή της εσωτερικής αναπαράστασης χρόνου σε ανθρώπινα αναγνώσιμες ώρες.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Αυτές οι τιμές εκφράζονται σε μικροδευτερόλεπτα, που είναι ο τρόπος που το Aspose.Tasks αποθηκεύει τον χρόνο εσωτερικά.

## Step 3: Create Project Instance
Φορτώστε το αρχείο Microsoft Project σε ένα αντικείμενο `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Ο κατασκευαστής `Project` αναλύει το αρχείο *.mpp* και κάνει όλα τα δεδομένα του έργου, συμπεριλαμβανομένων των ημερολογίων, προσβάσιμα μέσω του API.

## Step 4: Retrieve Calendars Information
Αποκτήστε τη συλλογή των ημερολογίων που ορίζονται στο έργο.

```java
CalendarCollection alCals = project.getCalendars();
```

Ένα έργο μπορεί να περιέχει πολλαπλά ημερολόγια (πρότυπα, πόρων και προσαρμοσμένα). Αυτή η συλλογή σας δίνει πρόσβαση σε καθένα από αυτά.

## Step 5: Iterate Through Calendars
Επανάληψη σε κάθε ημερολόγιο, εμφάνιση του UID, του ονόματος και των εργάσιμων ημερών με τις αντίστοιχες ώρες.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Ο εσωτερικός βρόχος ελέγχει κάθε αντικείμενο `WeekDay`. Αν η ημέρα είναι σημειωμένη ως εργάσιμη, εκτυπώνει τον τύπο ημέρας (Monday, Tuesday, …) μαζί με τις υπολογισμένες εργάσιμες ώρες.

## Step 6: Display Completion Message
Σήμα ότι η διαδικασία εξαγωγής ολοκληρώθηκε.

```java
System.out.println("Process completed Successfully");
```

## Conclusion
Ακολουθώντας αυτά τα βήματα, **τώρα γνωρίζετε πώς να χρησιμοποιήσετε το Aspose.Tasks για την εξαγωγή ημερολογίου έργου** από ένα αρχείο MS Project χρησιμοποιώντας Java. Μπορείτε να ενσωματώσετε αυτή τη λογική σε μεγαλύτερες εφαρμογές, να αυτοματοποιήσετε αναφορές ή να συγχρονίσετε χρονοδιαγράμματα με άλλα επιχειρησιακά συστήματα.

## Frequently Asked Questions

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;**  
Α: Ναι, το Aspose.Tasks υποστηρίζει πολλαπλές πλατφόρμες και γλώσσες προγραμματισμού, συμπεριλαμβανομένων .NET, C++, Python και Java.

**Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν έκδοση δοκιμής από [here](https://releases.aspose.com/).

**Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;**  
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Ε: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks;**  
Α: Ναι, προσωρινές άδειες είναι διαθέσιμες για αγορά [here](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks;**  
Α: Μπορείτε να ανατρέξετε στην τεκμηρίωση [here](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}