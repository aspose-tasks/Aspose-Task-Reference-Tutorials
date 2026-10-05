---
date: 2026-10-05
description: Μάθετε πώς να δημιουργήσετε ημερολόγιο έργου java και να διαμορφώσετε
  διάγραμμα Gantt java χρησιμοποιώντας το Aspose.Tasks for Java. Εκτενείς tutorials,
  examples και best practices.
keywords:
- create project calendar java
- configure gantt chart java
- aspose tasks java
- retrieve calendar data java
lastmod: 2026-10-05
linktitle: Aspose.Tasks for Java Εκπαιδευτικά προγράμματα
og_description: Μάθετε πώς να δημιουργήσετε ημερολόγιο έργου java και να διαμορφώσετε
  διάγραμμα Gantt java με το Aspose.Tasks for Java. Step‑by‑step guide, code‑free
  examples, και best practices για προγραμματιστές.
og_image_alt: Screenshot of a Java project calendar created with Aspose.Tasks
og_title: Δημιουργία ημερολογίου έργου java – Aspose.Tasks for Java εκπαιδευτικό
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create project calendar java and configure Gantt chart
    java using Aspose.Tasks for Java. Comprehensive tutorials, examples, and best
    practices.
  headline: Create project calendar java – Aspose.Tasks for Java guide
  type: TechArticle
- description: Learn how to create project calendar java and configure Gantt chart
    java using Aspose.Tasks for Java. Comprehensive tutorials, examples, and best
    practices.
  name: Create project calendar java – Aspose.Tasks for Java guide
  steps:
  - name: '**Create or load a Project** – instantiate `Project` with a file path or
      an empty constructor.'
    text: '**Create or load a Project** – instantiate `Project` with a file path or
      an empty constructor.'
  - name: '**Add a new Calendar** – call `project.getCalendars().add("MyCalendar")`.'
    text: '**Add a new Calendar** – call `project.getCalendars().add("MyCalendar")`.'
  - name: '**Configure weekdays** – use the `WeekDay` objects to mark Monday‑Friday
      as working and Saturday‑Sunday as non‑working.'
    text: '**Configure weekdays** – use the `WeekDay` objects to mark Monday‑Friday
      as working and Saturday‑Sunday as non‑working.'
  - name: '**Add exceptions** – create `CalendarException` objects for holidays or
      special work periods.'
    text: '**Add exceptions** – create `CalendarException` objects for holidays or
      special work periods.'
  - name: '**Assign the calendar to tasks** – set `task.setCalendar(myCalendar)` for
      any tasks that must follow the new schedule.'
    text: '**Assign the calendar to tasks** – set `task.setCalendar(myCalendar)` for
      any tasks that must follow the new schedule.'
  type: HowTo
- questions:
  - answer: Yes, you can use it commercially with a valid Aspose license. A free trial
      is available for evaluation.
    question: Can I use Aspose.Tasks for Java in a commercial application?
  - answer: Aspose.Tasks for Java supports Java 8, 11, and newer versions.
    question: Which Java versions are supported?
  - answer: Use the `Calendar` class to create an `Exception` object, set its start/end
      dates, and add it to the project’s calendar collection.
    question: How do I add a calendar exception programmatically?
  - answer: Absolutely—Aspose.Tasks provides the `GanttChartView` object where you
      can set bar colors, patterns, and other visual attributes.
    question: Is it possible to customize Gantt chart bar styles via code?
  - answer: The official documentation is hosted on Aspose’s website under the Aspose.Tasks
      for Java section.
    question: Where can I find the latest API documentation?
  type: FAQPage
tags:
- project calendar
- Aspose.Tasks
- Java scheduling
- Gantt chart customization
title: Δημιουργία ημερολογίου έργου java – Aspose.Tasks for Java οδηγός
url: /el/java/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία ημερολογίου έργου java – Οδηγός Aspose.Tasks για Java

Σε αυτόν τον ολοκληρωμένο οδηγό θα μάθετε πώς να **create project calendar java** χρησιμοποιώντας το Aspose.Tasks for Java. Είτε δημιουργείτε μια ολοκαίνουργια λύση διαχείρισης έργων είτε επεκτείνετε μια υπάρχουσα εφαρμογή, το API σας επιτρέπει να ορίζετε εργάσιμες ημέρες, αργίες και εξαιρέσεις ημερολογίου προγραμματιστικά. Θα δείτε επίσης πώς να **configure Gantt chart java** ρυθμίσεις ώστε οι ενδιαφερόμενοι να λαμβάνουν αμέσως ένα σαφές οπτικό χρονοδιάγραμμα.

## Γρήγορες απαντήσεις
- **What does “create project calendar java” mean?** Αναφέρεται στη χρήση του Aspose.Tasks for Java για τον ορισμό, την τροποποίηση και την ανάκτηση δεδομένων ημερολογίου σε αρχεία Microsoft Project.  
- **Do I need a license?** Διατίθεται δωρεάν δοκιμή, αλλά απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Which Java version is supported?** Το Aspose.Tasks υποστηρίζει Java 8 και νεότερες εκδόσεις.  
- **Can I configure Gantt chart java settings?** Ναι—το Aspose.Tasks σας επιτρέπει να ρυθμίζετε προγραμματιστικά τις ιδιότητες του Gantt chart, όπως τα στυλ των ράβδων και τις κλίμακες χρόνου.  
- **Where can I find sample code?** Κάθε εκπαιδευτικό υλικό που συνδέεται παρακάτω περιέχει παραδείγματα έτοιμα προς εκτέλεση που μπορείτε να προσαρμόσετε.

## Τι είναι το “create project calendar java”;
Η δημιουργία ημερολογίου έργου σε Java σημαίνει τον προγραμματιστικό ορισμό εργάσιμων ημερών, μη εργάσιμων ημερών και εξαιρέσεων ώστε το χρονοδιάγραμμα να αντανακλά τη πραγματική διαθεσιμότητα της οργάνωσής σας. Το Aspose.Tasks παρέχει ένα ευέλικτο API που αφαιρεί την υποκείμενη δομή XML των αρχείων Microsoft Project, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks for Java για τη διαχείριση ημερολογίων έργου;
Το Aspose.Tasks σας παρέχει **πλήρη έλεγχο** των εργάσιμων ημερών, των αργιών και των προσαρμοσμένων εξαιρέσεων χωρίς χειροκίνητη επεξεργασία αρχείων, **υποστήριξη πολλαπλών πλατφορμών** (Windows, Linux, macOS) και **πλούσια προσαρμογή Gantt chart** που οπτικοποιεί τα χρονοδιαγράμματα άμεσα. Η βιβλιοθήκη υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί **προγράμματα με εκατοντάδες σελίδες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας προβλέψιμη απόδοση ακόμη και σε μέτριους διακομιστές.

## Πώς να δημιουργήσετε ημερολόγιο έργου java
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project και παρέχει πρόσβαση στα ημερολόγιά του, στις εργασίες και στους πόρους. Φορτώστε ένα έργο, προσθέστε ένα νέο ημερολόγιο, ορίστε τις εργάσιμες ημέρες του και στη συνέχεια εκχωρήστε το σε εργασίες.  
**Direct answer:** Χρησιμοποιήστε την κλάση `Project` για να ανοίξετε ή να δημιουργήσετε ένα αρχείο, καλέστε `project.getCalendars().add("MyCalendar")` για να προσθέσετε ένα ημερολόγιο, διαμορφώστε τη συλλογή `WeekDays` του και τέλος ορίστε `task.setCalendar(myCalendar)`. Αυτή η ακολουθία δημιουργεί ένα πλήρως λειτουργικό ημερολόγιο με λίγες μόνο γραμμές κώδικα Java.

### Αναλυτικό σχέδιο βήμα‑βήμα
Ένα αντικείμενο `WeekDay` ορίζει την εργάσιμη ή μη εργάσιμη κατάσταση για μια συγκεκριμένη ημέρα της εβδομάδας.

1. **Create or load a Project** – δημιουργήστε μια παρουσία της `Project` με διαδρομή αρχείου ή με τον κενό κατασκευαστή.  
2. **Add a new Calendar** – καλέστε `project.getCalendars().add("MyCalendar")`.  
3. **Configure weekdays** – χρησιμοποιήστε τα αντικείμενα `WeekDay` για να σημειώσετε Δευτέρα‑Παρασκευή ως εργάσιμες και Σάββατο‑Κυριακή ως μη εργάσιμες.  
4. **Add exceptions** – δημιουργήστε αντικείμενα `CalendarException` για αργίες ή ειδικές περιόδους εργασίας.  
5. **Assign the calendar to tasks** – ορίστε `task.setCalendar(myCalendar)` για οποιεσδήποτε εργασίες που πρέπει να ακολουθούν το νέο χρονοδιάγραμμα.

## Πώς να διαμορφώσετε το Gantt chart java με το Aspose.Tasks
Η κλάση `GanttChartView` ελέγχει την οπτική εμφάνιση του Gantt chart όταν αποδίδεται ένα έργο. Προσαρμόστε τα οπτικά στοιχεία του Gantt chart απευθείας από τη Java ώστε το αποδοθέν χρονοδιάγραμμα να ταιριάζει με το εταιρικό στυλ σας.  
**Direct answer:** Ανακτήστε το `GanttChartView` από το αντικείμενο `Project`, στη συνέχεια ορίστε ιδιότητες όπως `setBarStyle`, `setTimescale` και `setShowCriticalTasks(true)`. Αυτές οι κλήσεις αλλάζουν τα χρώματα των ράβδων, τα μοτίβα των γραμμών και την λεπτομέρεια της κλίμακας χρόνου σε μια αλυσίδα κλήσεων API.

### Τυπικές προσαρμογές
- **Bar styles** – αλλάξτε τα χρώματα για κρίσιμες, ολοκληρωμένες και ορόσημο εργασίες.  
- **Timescale** – εναλλαγή μεταξύ ημερών, εβδομάδων ή μηνών ανάλογα με τη διάρκεια του έργου.  
- **Gridlines and fonts** – προσαρμόστε το πάχος, το χρώμα και το μέγεθος γραμματοσειράς για καλύτερη αναγνωσιμότητα.

## Εκπαιδευτικό για εξαιρέσεις ημερολογίου
Διαχειριστείτε, ορίστε, χειριστείτε και ανακτήστε εξαιρέσεις ημερολογίου σε έργα Java χρησιμοποιώντας το Aspose.Tasks με ευκολία. Τα βήμα‑βήμα εκπαιδευτικά μας σας δίνουν τη δυνατότητα να βελτιώσετε τις ροές εργασίας του έργου, εξασφαλίζοντας αποδοτική διαχείριση. Μάθετε περισσότερα [here](./calendar-exceptions/).

## Εκπαιδευτικό για ημερολόγια
Βελτιώστε τις δεξιότητές σας στη διαχείριση έργων Java με τα εκπαιδευτικά του Aspose.Tasks. Κατακτήστε τη διαχείριση ημερολογίων, δημιουργήστε, ορίστε εργάσιμες ημέρες και ενημερώστε τα ημερολόγια με ευκολία. Ανεβάστε τη διαχείριση του έργου σας στο επόμενο επίπεδο [here](./calendars/).

## Εκπαιδευτικό για νόμισμα
Διαχειριστείτε με ευκολία κωδικούς νομισμάτων, ψηφία και σύμβολα σε αρχεία MS Project με το Aspose.Tasks for Java. Βελτιώστε τη διαχείριση έργων με εκπαιδευτικά που είναι εύκολα στην παρακολούθηση. Εμβαθύνετε στον κόσμο της διαχείρισης νομισμάτων [here](./currency/).

## Εκπαιδευτικό για τύπους
Αναβαθμίστε τις δεξιότητές σας στη διαχείριση έργων με το Aspose.Tasks for Java. Κατακτήστε τους τύπους του MS Project, αυξήστε την παραγωγικότητα και γράψτε/διαβάστε τύπους αποδοτικά με ευκολία. Εξερευνήστε τη δύναμη των τύπων [here](./formulas/).

## Εκπαιδευτικό για ιδιότητες έργου
Αποκτήστε το δυναμικό του Aspose.Tasks for Java με τα Εκπαιδευτικά μας για Ιδιότητες Έργου. Εξάγετε, αξιοποιήστε και διαχειριστείτε πληροφορίες Microsoft Project με ευκολία. Μάθετε περισσότερα για τις ιδιότητες του έργου [here](./project-properties/).

## Εκπαιδευτικό για ιδιότητες νομίσματος
Αποκτήστε τη δύναμη των Εκπαιδευτικών του Aspose.Tasks for Java. Ανακαλύψτε οδηγούς βήμα‑βήμα για την ανάγνωση και ορισμό ιδιοτήτων νομίσματος σε αρχεία MS Project με ευκολία. Εξερευνήστε τις ιδιότητες νομίσματος [here](./currency-properties/).

## Εκπαιδευτικό για διαμόρφωση έργου
Ανακαλύψτε τη δύναμη του Aspose.Tasks for Java με τα ολοκληρωμένα μας εκπαιδευτικά. Διαμορφώστε Gantt charts, δημιουργήστε αρχεία MS Project και βελτιώστε τη διαχείριση έργων. Εμβαθύνετε στη διαμόρφωση έργου [here](./project-configuration/).

## Εκπαιδευτικό για διαχείριση έργου
Εξερευνήστε το Aspose.Tasks Java με τα ολοκληρωμένα μας εκπαιδευτικά για τη διαχείριση έργου. Από υπολογισμούς κρίσιμης διαδρομής έως ιδιότητες οικονομικού έτους, βελτιώστε τη ροή εργασίας σας. Μάθετε περισσότερα για τη διαχείριση έργου [here](./project-management/).

## Εκπαιδευτικό για ανάγνωση δεδομένων έργου
Αποκτήστε τη δύναμη του Aspose.Tasks for Java με τα εκπαιδευτικά μας! Από την ανάγνωση ορισμών ομάδων έως την εξαγωγή δεδομένων Gantt chart, κατακτήστε την αδιάλειπτη ενσωμάτωση. Εμβαθύνετε στην ανάγνωση δεδομένων έργου [here](./project-data-reading/).

## Εκπαιδευτικό για λειτουργίες αρχείου έργου
Βελτιστοποιήστε με ευκολία τις διατάξεις του MS Project με το Aspose.Tasks for Java. Μάθετε βήμα‑βήμα εκπαιδευτικά για τη μείωση κενών, την απόδοση δεδομένων, την αντικατάσταση ημερολογίων και άλλα. Εξερευνήστε τις λειτουργίες αρχείου έργου [here](./project-file-operations/).

## Εκπαιδευτικό για εκχωρήσεις πόρων
Κατακτήστε με ευκολία το Aspose.Tasks for Java με τα εκπαιδευτικά μας για εκχωρήσεις πόρων. Διαχειριστείτε την τροποποίηση του MS Project, τους προϋπολογισμούς εκχωρήσεων, τα κόστη και άλλα. Εμβαθύνετε στις εκχωρήσεις πόρων [here](./resource-assignments/).

## Εκπαιδευτικό για διαχείριση πόρων
Κατακτήστε τη διαχείριση πόρων στο MS Project με το Aspose.Tasks for Java. Μάθετε να δημιουργείτε, να επαναλαμβάνετε, να διαχειρίζεστε κόστη και άλλα. Βελτιστοποιήστε την ανάπτυξη με τα εκπαιδευτικά μας για τη διαχείριση πόρων [here](./resource-management/).

## Εκπαιδευτικό για βάσεις εργασιών
Εξερευνήστε το Aspose.Tasks Java με τα Εκπαιδευτικά μας για Βάσεις Εργασιών. Βελτιώστε τον προγραμματισμό εργασιών, δημιουργήστε βάσεις εργασιών MS Project και κατακτήστε τη διαχείριση διάρκειας βάσεων. Ανακαλύψτε τις βάσεις εργασιών [here](./task-baselines/).

## Εκπαιδευτικό για συνδέσμους εργασιών
Εξερευνήστε το Aspose.Tasks Java με τα Εκπαιδευτικά μας για Βάσεις Εργασιών. ... Βυθιστείτε στους συνδέσμους εργασιών [here](./task-links/).

## Εκπαιδευτικό για ιδιότητες εργασιών
Αναβαθμίστε τη διαχείριση έργων Java με το Aspose.Tasks. Εξερευνήστε εκπαιδευτικά για τις ιδιότητες εργασιών, από τη διαχείριση προτεραιοτήτων έως το χειρισμό κόστους. Βελτιστοποιήστε το έργο σας σήμερα! [here](./task-properties/).

## Εκπαιδευτικό για ενσωμάτωση VBA
Εξερευνήστε το Aspose.Tasks Java με ενσωμάτωση VBA. Βελτιώστε τις ροές εργασίας του έργου & την παρακολούθηση εργασιών. Εξερευνήστε ολοκληρωμένα εκπαιδευτικά για αδιάλειπτη ενσωμάτωση VBA [here](./vba-integration/).

Αποκτήστε το πλήρες δυναμικό του Aspose.Tasks for Java με τα λεπτομερή μας εκπαιδευτικά και παραδείγματα. Είτε είστε αρχάριος είτε έμπειρος προγραμματιστής, οι πόροι μας σας δίνουν τη δυνατότητα να πλοηγηθείτε στις πολυπλοκότητες της διαχείρισης έργων με ευκολία. Βυθιστείτε και βελτιστοποιήστε τα Java έργα σας σήμερα!

## Εκπαιδευτικά Aspose.Tasks για Java
### [Εξαιρέσεις Ημερολογίου](./calendar-exceptions/)
Διαχειριστείτε, ορίστε, χειριστείτε και ανακτήστε εξαιρέσεις ημερολογίου σε έργα Java χρησιμοποιώντας το Aspose.Tasks με ευκολία. Βελτιώστε τις ροές εργασίας του έργου για αποδοτική διαχείριση.
### [Ημερολόγια](./calendars/)
Βελτιώστε τις δεξιότητές σας στη διαχείριση έργων Java με τα εκπαιδευτικά του Aspose.Tasks. Κατακτήστε τη διαχείριση ημερολογίων, δημιουργήστε, ορίστε εργάσιμες ημέρες και ενημερώστε τα ημερολόγια με ευκολία.
### [Νόμισμα](./currency/)
Διαχειριστείτε με ευκολία κωδικούς νομισμάτων, ψηφία και σύμβολα σε αρχεία MS Project με το Aspose.Tasks for Java. Βελτιώστε τη διαχείριση έργων με εκπαιδευτικά που είναι εύκολα στην παρακολούθηση.
### [Τύποι](./formulas/)
Αναβαθμίστε τις δεξιότητές σας στη διαχείριση έργων με το Aspose.Tasks for Java. Κατακτήστε τους τύπους του MS Project, αυξήστε την παραγωγικότητα και γράψτε/διαβάστε τύπους αποδοτικά με ευκολία.
### [Ιδιότητες Έργου](./project-properties/)
Αποκτήστε το δυναμικό του Aspose.Tasks for Java με τα Εκπαιδευτικά μας για Ιδιότητες Έργου. Εξάγετε, αξιοποιήστε και διαχειριστείτε πληροφορίες Microsoft Project με ευκολία.
### [Ιδιότητες Νομίσματος](./currency-properties/)
Αποκτήστε τη δύναμη των Εκπαιδευτικών του Aspose.Tasks for Java. Ανακαλύψτε οδηγούς βήμα‑βήμα για την ανάγνωση και ορισμό ιδιοτήτων νομίσματος σε αρχεία MS Project με ευκολία.
### [Διαμόρφωση Έργου](./project-configuration/)
Ανακαλύψτε τη δύναμη του Aspose.Tasks for Java με τα ολοκληρωμένα μας εκπαιδευτικά. Διαμορφώστε Gantt charts, δημιουργήστε αρχεία MS Project και βελτιώστε τη διαχείριση έργων.
### [Διαχείριση Έργου](./project-management/)
Εξερευνήστε το Aspose.Tasks Java με τα ολοκληρωμένα μας εκπαιδευτικά για τη διαχείριση έργου. Από υπολογισμούς κρίσιμης διαδρομής έως ιδιότητες οικονομικού έτους, βελτιώστε τη ροή εργασίας σας.
### [Ανάγνωση Δεδομένων Έργου](./project-data-reading/)
Αποκτήστε τη δύναμη του Aspose.Tasks for Java με τα εκπαιδευτικά μας! Από την ανάγνωση ορισμών ομάδων έως την εξαγωγή δεδομένων Gantt chart, κατακτήστε την αδιάλειπτη ενσωμάτωση.
### [Λειτουργίες Αρχείου Έργου](./project-file-operations/)
Βελτιστοποιήστε με ευκολία τις διατάξεις του MS Project με το Aspose.Tasks for Java. Μάθετε βήμα‑βήμα εκπαιδευτικά για τη μείωση κενών, την απόδοση δεδομένων, την αντικατάσταση ημερολογίων και άλλα.
### [Εκχωρήσεις Πόρων](./resource-assignments/)
Κατακτήστε με ευκολία το Aspose.Tasks for Java με τα εκπαιδευτικά μας για εκχωρήσεις πόρων. Διαχειριστείτε την τροποποίηση του MS Project, τους προϋπολογισμούς εκχωρήσεων, τα κόστη και άλλα.
### [Διαχείριση Πόρων](./resource-management/)
Κατακτήστε τη διαχείριση πόρων στο MS Project με το Aspose.Tasks for Java. Μάθετε να δημιουργείτε, να επαναλαμβάνετε, να διαχειρίζεστε κόστη και άλλα.
### [Βάσεις Εργασιών](./task-baselines/)
Εξερευνήστε το Aspose.Tasks Java με τα Εκπαιδευτικά μας για Βάσεις Εργασιών. Βελτιώστε τον προγραμματισμό εργασιών, δημιουργήστε βάσεις εργασιών MS Project και κατακτήστε τη διαχείριση διάρκειας βάσεων.
### [Σύνδεσμοι Εργασιών](./task-links/)
Εξερευνήστε το Aspose.Tasks Java με τα Εκπαιδευτικά μας για Βάσεις Εργασιών. ... Βυθιστείτε στους συνδέσμους εργασιών.
### [Ιδιότητες Εργασιών](./task-properties/)
Αναβαθμίστε τη διαχείριση έργων Java με το Aspose.Tasks. Εξερευνήστε εκπαιδευτικά για τις ιδιότητες εργασιών, από τη διαχείριση προτεραιοτήτων έως το χειρισμό κόστους.
### [Ενσωμάτωση VBA](./vba-integration/)
Εξερευνήστε το Aspose.Tasks Java με ενσωμάτωση VBA. Βελτιώστε τις ροές εργασίας του έργου & την παρακολούθηση εργασιών.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java σε εμπορική εφαρμογή;**  
A: Ναι, μπορείτε να το χρησιμοποιήσετε εμπορικά με έγκυρη άδεια Aspose. Διατίθεται δωρεάν δοκιμή για αξιολόγηση.

**Q: Ποιες εκδόσεις Java υποστηρίζονται;**  
A: Το Aspose.Tasks for Java υποστηρίζει Java 8, 11 και νεότερες εκδόσεις.

**Q: Πώς μπορώ να προσθέσω μια εξαίρεση ημερολογίου προγραμματιστικά;**  
A: Χρησιμοποιήστε την κλάση `Calendar` για να δημιουργήσετε ένα αντικείμενο `Exception`, ορίστε τις ημερομηνίες έναρξης/λήξης και προσθέστε το στη συλλογή ημερολογίων του έργου.

**Q: Είναι δυνατόν να προσαρμόσετε τα στυλ των ράβδων του Gantt chart μέσω κώδικα;**  
A: Απόλυτα—το Aspose.Tasks παρέχει το αντικείμενο `GanttChartView` όπου μπορείτε να ορίσετε χρώματα ράβδων, μοτίβα και άλλα οπτικά χαρακτηριστικά.

**Q: Πού μπορώ να βρω την πιο πρόσφατη τεκμηρίωση API;**  
A: Η επίσημη τεκμηρίωση φιλοξενείται στην ιστοσελίδα της Aspose στην ενότητα Aspose.Tasks for Java.

---

**Τελευταία ενημέρωση:** 2026-10-05  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

---

## Σχετικά Εκπαιδευτικά

- [Πώς να χρησιμοποιήσετε το Aspose.Tasks για την ανάκτηση πληροφοριών ημερολογίου MS Project](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Αντικατάσταση ημερολογίου στο Aspose.Tasks – Προσθήκη ημερολογίου MS Project](/tasks/java/project-file-operations/replace-calendar/)
- [Δημιουργία νέας δραστηριότητας και ορισμός καταλόγου δεδομένων χρησιμοποιώντας το Aspose.Tasks for Java](/tasks/java/project-configuration/configure-gantt-chart/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}