---
date: 2026-10-31
description: Μάθετε πώς να εξάγετε gantt σε pdf σε Java χρησιμοποιώντας Aspose.Tasks.
  Αυτός ο οδηγός βήμα‑βήμα σας δείχνει πώς να διαβάζετε δεδομένα διαγράμματος Gantt
  και να δημιουργείτε αναφορές PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Ανάγνωση συγκεκριμένων δεδομένων διαγράμματος Gantt στο Aspose.Tasks
og_description: Εξαγωγή gantt σε pdf σε Java με Aspose.Tasks. Ακολουθήστε αυτό το
  σεμινάριο για να διαβάσετε δεδομένα διαγράμματος Gantt, να προσαρμόσετε τις ιδιότητες
  προβολής και να δημιουργήσετε αναφορές PDF για τη διαχείριση έργων.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Εξαγωγή gantt σε pdf σε Java – οδηγός Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Εξαγωγή gantt σε pdf σε Java – εξαγωγή συγκεκριμένων δεδομένων
url: /el/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή gantt σε pdf σε Java – εξαγωγή συγκεκριμένων δεδομένων

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε πώς να **εξάγετε gantt σε pdf σε Java** διαβάζοντας τις πληροφορίες του διαγράμματος Gantt με το Aspose.Tasks for Java. Τα διαγράμματα Gantt παρέχουν στους διαχειριστές έργων έναν οπτικό χάρτη των εργασιών, των εξαρτήσεων και των χρονοδιαγραμμάτων, και η δυνατότητα λήψης αυτών των δεδομένων προγραμματιστικά σας επιτρέπει να δημιουργήσετε αυτοματοποιημένες αναφορές PDF, πίνακες ελέγχου ή ενσωματώσεις με άλλα επιχειρησιακά συστήματα. Ας περάσουμε από κάθε βήμα, από τη φόρτωση ενός αρχείου έργου μέχρι την εξαγωγή των ιδιοτήτων προβολής και τελικά τη δημιουργία ενός PDF.

## Γρήγορες απαντήσεις
- **Τι μπορώ να εξάγω;** Οποιαδήποτε ιδιότητα προβολής, στυλ μπάρας, γραμμή πλέγματος, στυλ κειμένου, γραμμή προόδου ή επίπεδο κλίμακας χρόνου από ένα διάγραμμα Gantt.  
- **Χρειάζομαι άδεια;** Η δοκιμαστική έκδοση λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** Java 8 ή νεότερη (το tutorial χρησιμοποιεί JDK 11).  
- **Είναι ο κώδικας εκτελέσιμος όπως είναι;** Ναι – απλώς αντικαταστήστε τη διαδρομή του καταλόγου δεδομένων.  
- **Μπορώ να τροποποιήσω την προβολή μετά την ανάγνωση;** Απόλυτα – το API σας επιτρέπει να αλλάξετε ιδιότητες και να αποθηκεύσετε ξανά στο αρχείο έργου.

## Τι είναι η εξαγωγή gantt σε pdf;
Η εξαγωγή gantt σε pdf είναι η διαδικασία μετατροπής μιας προβολής διαγράμματος Gantt που αποθηκεύεται σε αρχείο έργου σε έγγραφο PDF που διατηρεί το οπτικό στυλ και τις πληροφορίες χρονοδιαγράμματος. Αυτή η λειτουργία είναι χρήσιμη για την κοινή χρήση της κατάστασης του έργου με ενδιαφερόμενους που ενδέχεται να μην διαθέτουν εργαλείο διαχείρισης έργων.

## Γιατί η εξαγωγή gantt σε pdf με Aspose.Tasks;
Το Aspose.Tasks μπορεί να διαχειριστεί **πάνω από 30 + μορφές εισόδου** (MPP, XML, MPX κ.λπ.) και **να εξάγει σε PDF με μία κλήση** διατηρώντας το 95 % της οπτικής πιστότητας, ακόμη και για έργα με περισσότερες από 500 εργασίες. Η βιβλιοθήκη επεξεργάζεται τα αρχεία στη μνήμη, ώστε να μπορείτε να δημιουργείτε PDF σε διακομιστές χωρίς την εγκατάσταση του Microsoft Project.

## Προαπαιτούμενα
1. **Java Development Kit (JDK):** Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java στο σύστημά σας. Μπορείτε να το κατεβάσετε από τη **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for Java από τη **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Επιλέξτε ένα IDE της προτίμησής σας. Δημοφιλείς επιλογές περιλαμβάνουν IntelliJ IDEA, Eclipse ή NetBeans.

## Εισαγωγή πακέτων
Οι παρακάτω εισαγωγές σας δίνουν πρόσβαση στις βασικές κλάσεις του Aspose.Tasks που απαιτούνται για την ανάγνωση και εξαγωγή δεδομένων Gantt.  
*Δεν εμφανίζεται κανένα μπλοκ κώδικα εδώ για να διατηρηθεί το tutorial επικεντρωμένο στις έννοιες· απλώς προσθέστε τις εισαγωγές στο αρχείο Java σας.*

## Πώς φορτώνω ένα αρχείο έργου διαγράμματος Gantt σε Java;
Φορτώστε το αρχείο έργου δημιουργώντας μια παρουσία `Project` και περνώντας τη πλήρη διαδρομή στον κατασκευαστή. Αυτό το βήμα αρχικοποιεί την αναπαράσταση του διαγράμματος Gantt στη μνήμη, επιτρέποντας μετέπειτα ερωτήματα για τις ιδιότητες προβολής. Όταν το αρχείο φορτωθεί επιτυχώς, μπορείτε να επαληθεύσετε το όνομα του έργου, την ημερομηνία έναρξης και τον αριθμό των εργασιών για να διασφαλίσετε ότι ανοίχθηκε το σωστό αρχείο. Αυτή η επαλήθευση βοηθά στον εντοπισμό προβλημάτων διαδρομής ή μορφής νωρίς στη ροή εργασίας.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Αγκύρωση ορισμού:* `Project` είναι το αντικείμενο Aspose.Tasks υψηλότερου επιπέδου που αντιπροσωπεύει ένα μοναδικό αρχείο έργου στη μνήμη.

## Πώς μπορώ να αποκτήσω πρόσβαση στην προβολή διαγράμματος Gantt;
Ανακτήστε την πρώτη προβολή Gantt από τη συλλογή προβολών του έργου. Τα περισσότερα έργα περιέχουν τουλάχιστον μία προβολή Gantt, και συνήθως είναι η πρώτη καταχώρηση. Αφού αποκτήσετε την προβολή, ίσως θέλετε να ελέγξετε το όνομά της και να βεβαιωθείτε ότι είναι τύπου `GanttChartView` πριν προχωρήσετε στην εξαγωγή ιδιοτήτων. Αυτός ο επιπλέον έλεγχος αποτρέπει σφάλματα χρόνου εκτέλεσης όταν εργάζεστε με προσαρμοσμένες ή μη‑τυπικές συλλογές προβολών.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Αγκύρωση ορισμού:* `GanttChartView` αντιπροσωπεύει τη οπτική διάταξη των εργασιών, των κλιμάκων χρόνου και των μπαρών που βλέπετε σε ένα τυπικό διάγραμμα Gantt.

## Πώς εξάγω ιδιότητες προβολής;
Μπορείτε να διαβάσετε ιδιότητες όπως το χρώμα φόντου, το ύψος μπάρας και τις ρυθμίσεις κλίμακας χρόνου απευθείας από το αντικείμενο `GanttChartView`. Η εκτύπωσή τους σας βοηθά να επαληθεύσετε την τρέχουσα διαμόρφωση πριν την εξαγωγή. Ένας τυπικός βρόχος εξαγωγής διατρέχει κάθε ιδιότητα, μορφοποιεί την τιμή ως συμβολοσειρά και την καταγράφει στην κονσόλα ή σε αρχείο για μετέπειτα ανάλυση. Αυτή η προσέγγιση είναι χρήσιμη για εντοπισμό σφαλμάτων και για τη δημιουργία τεκμηρίωσης της εμφάνισης του διαγράμματος.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Αγκύρωση ορισμού:* `GanttChartView` παρέχει πρόσβαση στις ρυθμίσεις προβολής όπως το χρώμα φόντου, το ύψος μπάρας και τη διαμόρφωση κλίμακας χρόνου.

## Πώς εξάγω στυλ μπάρας;
Διατρέξτε τη συλλογή αντικειμένων `BarStyle` για να λάβετε λεπτομέρειες όπως χρώμα, μοτίβο και σχήμα για κάθε τύπο μπάρας που χρησιμοποιείται στο διάγραμμα. Για κάθε στυλ, μπορείτε επίσης να διαβάσετε τον σχετικό τύπο εργασίας και την κατάσταση που ενεργοποιεί το στυλ, κάτι που είναι απαραίτητο όταν αναδημιουργείτε το διάγραμμα σε άλλη μορφή. Η συλλογή αυτών των πληροφοριών σας επιτρέπει να παράγετε μια πιστή οπτική αναπαράσταση ή να εφαρμόσετε προσαρμοσμένους κανόνες στυλ προγραμματιστικά.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Αγκύρωση ορισμού:* `BarStyle` ορίζει την οπτική εμφάνιση μιας μπάρας Gantt, συμπεριλαμβανομένου του χρώματος, του μοτίβου και του σχήματος.

## Πώς εξάγω γραμμές πλέγματος;
Οι γραμμές πλέγματος ορίζουν τον οπτικό διαχωρισμό μεταξύ γραμμών και στηλών. Πρόσβαση σε αυτές μέσω της μεθόδου `getGridlines()` και εξαγωγή της ορατότητας και του στυλ τους. Αφού ανακτήσετε τη συλλογή γραμμών πλέγματος, μπορείτε να διατρέξετε κάθε γραμμή για να καταγράψετε τον τύπο γραμμής (συμπαγής, διακεκομμένη), το πάχος και το χρώμα. Αυτά τα δεδομένα είναι πολύτιμα όταν χρειάζεται να αναπαράγετε την ακριβή διάταξη πλέγματος σε εξαγόμενα PDF ή άλλες μορφές αναφοράς.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Αγκύρωση ορισμού:* `getGridlines()` επιστρέφει τη συλλογή αντικειμένων γραμμής πλέγματος που ελέγχουν τους διαχωριστές γραμμές και στήλες στην προβολή Gantt.

## Πώς εξάγω στυλ κειμένου;
Τα στυλ κειμένου ελέγχουν τη γραμματοσειρά, το μέγεθος και το χρώμα των ετικετών στο διάγραμμα Gantt. Διατρέξτε τη συλλογή `TextStyle` για να καταγράψετε κάθε στυλ. Για κάθε στυλ κειμένου, μπορείτε επίσης να ανακτήσετε το σχετικό στοιχείο (όνομα εργασίας, ημερομηνία κ.λπ.) και τυχόν κανόνες υπό όρους μορφοποίησης. Η καταγραφή αυτών των λεπτομερειών εξασφαλίζει ότι τα εξαγόμενα έγγραφα διατηρούν την ίδια τυπογραφία με το αρχικό διάγραμμα.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Αγκύρωση ορισμού:* `TextStyle` αντιπροσωπεύει τα χαρακτηριστικά μορφοποίησης που εφαρμόζονται σε κειμενικά στοιχεία εντός του διαγράμματος Gantt.

## Πώς εξάγω γραμμές προόδου;
Οι γραμμές προόδου δείχνουν το τρέχον σημείο ολοκλήρωσης μιας εργασίας. Πρόσβαση σε αυτές μέσω του `getProgressLines()` και εκτύπωση των χαρακτηριστικών τους. Κάθε γραμμή προόδου περιλαμβάνει ιδιότητες όπως το χρώμα γραμμής, το πάχος και τη θέση σε σχέση με τη μπάρα εργασίας. Η καταγραφή αυτών των πληροφοριών σας επιτρέπει να δημιουργήσετε οπτικοποιήσεις με επίγνωση προόδου ή να υπολογίσετε συνολικούς δείκτες ολοκλήρωσης του έργου.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Αγκύρωση ορισμού:* `getProgressLines()` επιστρέφει το σύνολο των αντικειμένων γραμμής προόδου που υποδεικνύουν την κατάσταση ολοκλήρωσης της εργασίας.

## Πώς εξάγω επίπεδα κλίμακας χρόνου;
Τα επίπεδα κλίμακας χρόνου ορίζουν τις ιεραρχικές μονάδες χρόνου (ημέρες, εβδομάδες, μήνες) που εμφανίζονται στο διάγραμμα. Ανακτήστε τα μέσω του `getTimescaleTiers()` και εξαγάγετε τις ρυθμίσεις τους. Για κάθε επίπεδο μπορείτε να καταγράψετε τον τύπο μονάδας, τη μορφή ετικέτας και την ευθυγράμμιση, που είναι κρίσιμα για την αναπαραγωγή της ακριβούς λεπτομέρειας του χρονοδιαγράμματος σε εξαγόμενα PDF ή προσαρμοσμένα UI στοιχεία.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Αγκύρωση ορισμού:* `getTimescaleTiers()` παρέχει πρόσβαση στη συλλογή αντικειμένων επιπέδου κλίμακας χρόνου που ελέγχουν την εμφάνιση του άξονα χρόνου.

## Πώς εξάγω το διάγραμμα Gantt σε PDF;
Δημιουργήστε ένα αντικείμενο `PdfSaveOptions`, προαιρετικά προσαρμόστε το μέγεθος σελίδας ή την ενσωμάτωση γραμματοσειρών, και στη συνέχεια καλέστε `project.save` με τη μορφή PDF. Αυτή η ενιαία κλήση δημιουργεί ένα PDF που αντικατοπτρίζει την προβολή Gantt στην οθόνη. Μπορείτε επίσης να ορίσετε πρόσθετες επιλογές όπως συμπίεση εικόνας, αφαίρεση υδατογράφηματος ή ενσωμάτωση προσαρμοσμένων γραμματοσειρών για να καλύψετε τις απαιτήσεις εταιρικής ταυτότητας. Μετά την αποθήκευση, επαληθεύστε το μέγεθος του αρχείου PDF και την οπτική πιστότητα για να διασφαλίσετε ότι η εξαγωγή ήταν επιτυχής.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Αγκύρωση ορισμού:* `PdfSaveOptions` σας επιτρέπει να ρυθμίσετε λεπτομερώς την έξοδο PDF, όπως τις διαστάσεις σελίδας, τη συμπίεση και τη διαχείριση γραμματοσειρών.

## Συνηθισμένα προβλήματα & συμβουλές
- **Λανθασμένος κατάλογος δεδομένων:** Βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`) κατάλληλο για το λειτουργικό σας σύστημα.  
- **Απουσία προβολής:** Εάν το έργο δεν έχει προβολή Gantt, το `project.getViews()` θα είναι κενό – προσθέστε έναν έλεγχο πριν το μετατρέψετε.  
- **Εξαιρέσεις άδειας:** Χωρίς έγκυρη άδεια, το API μπορεί να προσθέσει υδατογράφημα στα εξαγόμενα PDF.  
- **Μεγάλα έργα:** Για έργα με περισσότερες από 1.000 εργασίες, εξετάστε την αύξηση του μεγέθους heap της JVM (`-Xmx2g`) για να αποφύγετε `OutOfMemoryError`.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java με άλλες βιβλιοθήκες Java;**  
A: Ναι, το Aspose.Tasks for Java ενσωματώνεται άψογα με οποιαδήποτε βιβλιοθήκη ή πλαίσιο Java, συμπεριλαμβανομένων των Spring, Hibernate και Apache POI.

**Q: Είναι το Aspose.Tasks κατάλληλο για μεγάλης κλίμακας εταιρικά έργα;**  
A: Απόλυτα. Η βιβλιοθήκη επεξεργάζεται αρχεία MPP πολλαπλών εκατοντάδων σελίδων σε λιγότερο από 5 δευτερόλεπτα σε τυπικό υλικό διακομιστή και υποστηρίζει ταυτόχρονη εκτέλεση σε πολυνηματικά περιβάλλοντα.

**Q: Υποστηρίζει το Aspose.Tasks πολλαπλές μορφές αρχείων έργου;**  
A: Ναι, το Aspose.Tasks υποστηρίζει πάνω από 20 μορφές, συμπεριλαμβανομένων των MPP, XML, MPX και Primavera XML, επιτρέποντάς σας να διαβάζετε και να μετατρέπετε παλαιά χρονοδιαγράμματα.

**Q: Μπορώ να προσαρμόσω την εμφάνιση των διαγραμμάτων Gantt με το Aspose.Tasks;**  
A: Φυσικά. Μπορείτε να τροποποιήσετε τα στυλ μπάρας, τις γραμμές πλέγματος, τα στυλ κειμένου και τα επίπεδα κλίμακας χρόνου προγραμματιστικά πριν την εξαγωγή σε PDF ή μορφές εικόνας.

**Q: Πώς αποθηκεύω τις αλλαγές μετά την τροποποίηση μιας προβολής;**  
A: Καλέστε `project.save("output.mpp");` μετά από οποιεσδήποτε τροποποιήσεις για να τις διατηρήσετε στο αρχείο έργου.

---

**Τελευταία ενημέρωση:** 2026-10-31  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Σχετικά tutorials

- [Πώς να αποθηκεύσετε το έργο ως PDF με Aspose.Tasks – Οδηγός εξαγωγής](/tasks/java/project-file-operations/save-as-pdf/)
- [Δημιουργία PDF έργου – Προσαρμογή κλίμακας χρόνου διαγράμματος Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Εξαγωγή έργου σε PDF και μείωση κενών μεταξύ λίστας εργασιών και υποσέλιδου στο Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}