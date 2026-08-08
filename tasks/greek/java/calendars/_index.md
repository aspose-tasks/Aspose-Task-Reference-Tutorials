---
date: 2026-08-08
description: Μάθετε πώς να ορίζετε τις εργάσιμες ημέρες στα ημερολόγια του MS Project
  χρησιμοποιώντας το Aspose.Tasks για Java. Αυτός ο οδηγός σας δείχνει πώς να τροποποιήσετε
  το ημερολόγιο του MS Project, να δημιουργήσετε προσαρμοσμένο ημερολόγιο Java και
  να προγραμματίσετε τις εργάσιμες ημέρες αποτελεσματικά.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Ημερολόγια
og_description: Μάθετε πώς να ορίζετε τις εργάσιμες ημέρες στα ημερολόγια του MS Project
  χρησιμοποιώντας το Aspose.Tasks για Java. Κατακτήστε το προσαρμοσμένο ημερολόγιο
  Java, τροποποιήστε το ημερολόγιο του MS Project και προγραμματίστε τις εργάσιμες
  ημέρες αποτελεσματικά.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Πώς να ορίσετε τις εργάσιμες ημέρες στα ημερολόγια του MS Project – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Πώς να ορίσετε τις εργάσιμες ημέρες στα ημερολόγια του MS Project – Aspose.Tasks
  Java
url: /el/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ημερολόγια

## Εισαγωγή

Αν είστε προγραμματιστής Java που θέλει να **ορίσετε weekdays** στο χρονοδιάγραμμα του έργου σας, βρίσκεστε στο σωστό μέρος. Σε αυτό το κέντρο συγκεντρώνουμε όλα τα tutorials Aspose.Tasks for Java που δείχνουν **πώς να ορίσετε weekdays** μέσα σε ημερολόγια MS Project, να προσαρμόσετε τις ώρες εργασίας και να διατηρήσετε τα χρονοδιαγράμματα σας kristall‑clear. Είτε δημιουργείτε μια νέα μηχανή προγραμματισμού είτε τροποποιείτε ένα υπάρχον σχέδιο, η κατάκτηση του ορισμού weekdays σας δίνει ακριβή έλεγχο πάνω σε μοτίβα εργάσιμων ημερών, διακοπές και προσαρμοσμένες βάρδιες. Αυτός ο οδηγός εξηγεί επίσης **πώς να τροποποιήσετε τις ρυθμίσεις ημερολογίου MS Project** προγραμματιστικά, ώστε να μπορείτε να αυτοματοποιήσετε τη δημιουργία ημερολογίων σε δεκάδες έργα.

## Γρήγορες απαντήσεις
- **Ποιος είναι ο κύριος σκοπός του ορισμού weekdays;**  
  Για να ενημερώσετε το MS Project ποιες ημέρες είναι εργάσιμες και ποιες είναι οι εργάσιμες ώρες τους.
- **Ποια βιβλιοθήκη διαχειρίζεται τον ορισμό weekdays σε Java;**  
  Το Aspose.Tasks for Java παρέχει ένα ευέλικτο API για τη διαχείριση ημερολογίων.
- **Χρειάζομαι άδεια;**  
  Μια δωρεάν άδεια αξιολόγησης λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.
- **Μπορώ να ορίσω πολλαπλά ημερολόγια για διαφορετικές ομάδες;**  
  Ναι – κάθε έργο μπορεί να περιέχει πολλά ημερολόγια, το καθένα με τις δικές του ρυθμίσεις weekdays.
- **Υπάρχει δείγμα έργου για εκκίνηση;**  
  Το tutorial “Define Weekdays in Calendar” που συνδέεται παρακάτω περιλαμβάνει ένα έτοιμο παράδειγμα.

## Πώς ορίζω weekdays σε ημερολόγια MS Project;

The `Project` class represents an MS Project file and provides access to its data structures. A `Calendar` object stores working time definitions and exceptions for a project. Load your project with `new Project("myproject.mpp")`, retrieve (or create) a `Calendar` object, and then call `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. That single line creates a Monday work‑day entry with an 8‑hour shift. Repeat for other days, and finally save the project with `project.save("updated.mpp")`. This concise pattern lets you define, modify, or delete weekdays in just a few API calls, eliminating the need for manual UI interaction.

## Τι είναι το αντικείμενο WeekDay;

A `WeekDay` object represents a single day‑of‑the‑week entry inside an Aspose.Tasks calendar, storing its working status and working‑time intervals. You can configure start/end times, set it as non‑working, or attach overtime periods. It can hold multiple `WorkingTime` intervals to model split shifts, and it supports flags for default working days. Use the `WeekDay` API to enable or disable a day, assign regular hours, or specify overtime rules for advanced scheduling scenarios.

## Γιατί να χρησιμοποιήσετε Aspose.Tasks for Java για τον ορισμό weekdays;

- **Πλήρης έλεγχος API** – Χωρίς περιορισμούς UI· μπορείτε προγραμματιστικά να δημιουργήσετε, τροποποιήσετε ή διαγράψετε εγγραφές weekday.  
- **Cross‑platform** – Λειτουργεί σε οποιοδήποτε περιβάλλον συμβατό με JVM, από εφαρμογές επιφάνειας εργασίας έως υπηρεσίες cloud.  
- **Precision** – Ορίστε διαφορετικές ώρες εργασίας για κάθε weekday, προσθέστε εξαιρέσεις για διακοπές και συγχρονίστε τα ημερολόγια μεταξύ πολλαπλών έργων.  
- **Performance** – Επεξεργαστείτε έργα με έως και 500+ εργασίες και ημερολόγια που περιέχουν 100+ εβδομάδες χωρίς φόρτωση ολόκληρης της UI, επιτυγχάνοντας χρόνους μετατροπής κάτω από 2 δευτερόλεπτα σε τυπικό διακομιστή 2.5 GHz (βάσει μετρήσεων Aspose).  

## Προαπαιτούμενα
- Java 8 ή νεότερη εγκατεστημένη.  
- Βιβλιοθήκη Aspose.Tasks for Java (λήψη από τον ιστότοπο Aspose ή προσθήκη μέσω Maven/Gradle).  
- Έγκυρη άδεια Aspose.Tasks (η άδεια αξιολόγησης λειτουργεί για εκμάθηση).  

## Διαχείριση ιδιοτήτων ημερολογίου MS Project στο Aspose.Tasks

Αποκτήστε το πλήρες δυναμικό της διαχείρισης ιδιοτήτων ημερολογίου MS Project σε Java με το Aspose.Tasks. Το tutorial μας σας οδηγεί μέσα από τις λεπτομέρειες της διαχείρισης ημερολογίου, προσφέροντας πολύτιμες γνώσεις για προσαρμογή και βελτιστοποίηση. Από την προσαρμογή ωρών εργασίας μέχρι τον ορισμό ειδικών ημερομηνιών, θα τα κατακτήσετε όλα.

Ready to take control of your project timelines? [Explore the tutorial here](./properties/).

## Δημιουργία ημερολογίων MS Project χρησιμοποιώντας Aspose.Tasks

Απλοποιήστε τη διαχείριση έργων σας με τη δημιουργία ημερολογίων MS Project χρησιμοποιώντας Aspose.Tasks for Java. Το tutorial μας απλοποιεί τη διαδικασία, εξασφαλίζοντας ότι μπορείτε να ρυθμίσετε ημερολόγια προσαρμοσμένα στις μοναδικές ανάγκες του έργου σας. Κάντε το πρώτο βήμα προς την αποδοτική προγραμματιστική και οργανωτική διαχείριση.

Ready to create calendars with ease? [Check out the tutorial](./create/).

## Ορισμός weekdays σε ημερολόγιο με Aspose.Tasks

Προσαρμόστε τα ημερολόγια MS Project ορίζοντας weekdays χρησιμοποιώντας Aspose.Tasks for Java. Αυτό το tutorial σας καθοδηγεί στη διαδικασία προσαρμογής εργάσιμων ημερών και ωρών, προσφέροντας την ευελιξία που χρειάζεστε για επιτυχημένη διαχείριση έργου. Κάντε τα ημερολόγια σας να δουλεύουν για εσάς.

Ready to define weekdays effortlessly? [Get started here](./define-weekdays/).

Καθώς προχωράτε στα tutorials, θα ανακαλύψετε επιπλέον θέματα που καλύπτουν εξαγωγή ωρών εργασίας, δημιουργία τυπικού ημερολογίου, ανάγνωση εβδομάδων εργασίας και ενημέρωση ημερολογίων σε μορφή MPP. Κάθε tutorial έχει σχεδιαστεί για να σας παρέχει πρακτική γνώση, εξασφαλίζοντας ότι μπορείτε να εφαρμόσετε ό,τι μάθετε απευθείας στα Java projects σας.

## Λήψη ωρών εργασίας από το ημερολόγιο χρησιμοποιώντας Aspose.Tasks

Απλοποιήστε τις εργασίες διαχείρισης έργου εξάγοντας τις ώρες εργασίας από ημερολόγια MS Project με το Aspose.Tasks for Java. Αυτό το tutorial σας εξοπλίζει με τις δεξιότητες που χρειάζεστε για βέλτιστη βελτιστοποίηση των χρονοδιαγραμμάτων του έργου σας.

Ready to extract working hours effortlessly? [Explore the tutorial](./working-hours/).

## Δημιουργία τυπικού ημερολογίου στο Aspose.Tasks

Ενισχύστε τις δυνατότητες διαχείρισης έργου μαθαίνοντας πώς να δημιουργήσετε ένα τυπικό ημερολόγιο MS Project σε Java με το Aspose.Tasks. Αυτό το βήμα‑βήμα tutorial εξασφαλίζει ότι μπορείτε να εφαρμόσετε μια τυποποιημένη προσέγγιση στα χρονοδιαγράμματα του έργου σας.

Ready to create a standard calendar? [Check out the tutorial](./make-standard/).

## Ανάγνωση εβδομάδων εργασίας από το ημερολόγιο MS Project με Aspose.Tasks

Αποκτήστε πλήρη εικόνα για την ανάγνωση εβδομάδων εργασίας από ημερολόγια MS Project χρησιμοποιώντας Aspose.Tasks for Java. Αυτό το tutorial προσφέρει λεπτομερείς οδηγίες, δίνοντάς σας τη δυνατότητα να διαχειρίζεστε αποτελεσματικά τα χρονοδιαγράμματα του έργου σας.

Ready to read work weeks effortlessly? [Get started here](./read-work-weeks/).

## Ενημέρωση ημερολογίων MS Project σε μορφή MPP με Aspose.Tasks

Ενημερώστε εύκολα τα ημερολόγια MS Project σε μορφή MPP χρησιμοποιώντας Aspose.Tasks for Java. Αυτό το tutorial παρέχει μια απρόσκοπτη προσέγγιση για να διασφαλίσετε ότι τα δεδομένα του έργου σας είναι στη σωστή μορφή για βέλτιστη συμβατότητα.

Ready to update calendars to MPP format? [Explore the tutorial](./update-to-mpp/).

Αποκτήστε το πλήρες δυναμικό του Aspose.Tasks for Java και ανεβάστε τις δεξιότητές σας στη διαχείριση έργων. Κάθε tutorial έχει σχεδιαστεί για προγραμματιστές όλων των επιπέδων, εξασφαλίζοντας μια ομαλή εμπειρία μάθησης. Βυθιστείτε και επαναπροσδιορίστε τη διαχείριση Java έργων σας σήμερα!

## Tutorials ημερολογίων
### [Διαχείριση ιδιοτήτων ημερολογίου MS Project στο Aspose.Tasks](./properties/)
Μάθετε πώς να διαχειρίζεστε ιδιότητες ημερολογίου MS Project σε Java χρησιμοποιώντας Aspose.Tasks. Παρέχει βήμα‑βήμα καθοδήγηση για το ημερολόγιο στις Java εφαρμογές σας.
### [Δημιουργία ημερολογίων MS Project χρησιμοποιώντας Aspose.Tasks](./create/)
Μάθετε πώς να δημιουργείτε ημερολόγια MS Project χρησιμοποιώντας Aspose.Tasks for Java. Απλοποιήστε τη διαχείριση έργων με ευκολία.
### [Ορισμός weekdays σε ημερολόγιο με Aspose.Tasks](./define-weekdays/)
Μάθετε πώς να ορίζετε weekdays σε ημερολόγιο MS Project χρησιμοποιώντας Aspose.Tasks for Java. Προσαρμόστε εργάσιμες ημέρες και ώρες χωρίς κόπο.
### [Λήψη ωρών εργασίας από το ημερολόγιο χρησιμοποιώντας Aspose.Tasks](./working-hours/)
Εξάγετε ώρες εργασίας από ημερολόγια MS Project εύκολα με Aspose.Tasks for Java. Απλοποιήστε τις εργασίες διαχείρισης έργου.
### [Δημιουργία τυπικού ημερολογίου στο Aspose.Tasks](./make-standard/)
Μάθετε πώς να δημιουργήσετε τυπικό ημερολόγιο MS Project σε Java χρησιμοποιώντας Aspose.Tasks. Ενισχύστε τις δυνατότητες διαχείρισης έργου με αυτό το βήμα‑βήμα tutorial.
### [Ανάγνωση εβδομάδων εργασίας από το ημερολόγιο MS Project με Aspose.Tasks](./read-work-weeks/)
Μάθετε πώς να διαβάζετε εβδομάδες εργασίας από ημερολόγιο MS Project χρησιμοποιώντας Aspose.Tasks for Java. Λάβετε βήμα‑βήμα οδηγίες σε αυτό το ολοκληρωμένο tutorial.
### [Ενημέρωση ημερολογίων MS Project σε μορφή MPP με Aspose.Tasks](./update-to-mpp/)
Μάθετε πώς να ενημερώσετε ημερολόγια MS Project σε μορφή MPP εύκολα χρησιμοποιώντας Aspose.Tasks for Java.

## Συχνές ερωτήσεις

**Ε: Μπορώ να ορίσω διαφορετικές ώρες εργασίας για κάθε weekday;**  
Α: Ναι. Το Aspose.Tasks σας επιτρέπει να ορίσετε ξεχωριστές ώρες έναρξης και λήξης για κάθε ημέρα από Δευτέρα έως Κυριακή.

**Ε: Πώς διαχειρίζομαι διακοπές ή μη εργάσιμες ημέρες;**  
Α: Αφού ορίσετε weekdays, μπορείτε να προσθέσετε εξαιρέσεις (ημερομηνίες) για να σημειώσετε διακοπές ή προσαρμοσμένες μη εργάσιμες περιόδους.

**Ε: Είναι δυνατόν να αντιγράψω έναν ορισμό weekday από ένα ημερολόγιο σε άλλο;**  
Α: Απόλυτα. Μπορείτε να ανακτήσετε ένα αντικείμενο `WeekDay` από υπάρχον ημερολόγιο και να το προσθέσετε σε άλλο ημερολόγιο.

**Ε: Πρέπει να επαναφορτώσω το έργο μετά την ενημέρωση των weekdays;**  
Α: Όχι. Οι αλλαγές εφαρμόζονται απευθείας στο αντικείμενο `Project` στη μνήμη· απλώς αποθηκεύστε το έργο όταν τελειώσετε.

**Ε: Ποια έκδοση του Aspose.Tasks απαιτείται για τη διαχείριση weekdays;**  
Α: Όλες οι πρόσφατες εκδόσεις (20.10 και μετά) υποστηρίζουν πλήρη API weekdays. Συνιστούμε τη χρήση της πιο πρόσφατης σταθερής έκδοσης για βέλτιστη απόδοση.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Σχετικά Tutorials

- [Προσθήκη ημερολογίου στο έργο με Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Καθορισμός εργάσιμων ημερών & ωρών εργασίας με Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Δημιουργία προσαρμοσμένων εξαιρέσεων ημερολογίου με Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}