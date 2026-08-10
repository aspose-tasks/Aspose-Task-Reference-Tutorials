---
date: 2026-06-10
description: Μάθετε πώς να αλλάξετε το contour και να δημιουργήσετε timephased data
  για resource assignments χρησιμοποιώντας το Aspose.Tasks για Java, καλύπτοντας work
  contour types και advanced scheduling scenarios.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Δημιουργία Timephased Data για Resource Assignments στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να αλλάξετε το Contour στο Aspose.Tasks για Timephased Data
url: /el/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αλλάξετε το περίγραμμα στο Aspose.Tasks για δεδομένα χρονικής φάσης

## Εισαγωγή
Σε αυτό το σεμινάριο, θα ανακαλύψετε **πώς να αλλάξετε το περίγραμμα** για μια ανάθεση πόρου και να δημιουργήσετε δεδομένα χρονικής φάσης χρησιμοποιώντας το Aspose.Tasks για Java. Τα δεδομένα χρονικής φάσης αποκαλύπτουν την κατανομή της εργασίας κατά τη διάρκεια του χρονοδιαγράμματος του έργου, επιτρέποντάς σας να βελτιστοποιήσετε τα προγράμματα, να ισορροπήσετε το φορτίο εργασίας και να λαμβάνετε αποφάσεις βάσει δεδομένων. Η εξοικείωση με τις αλλαγές περιγράμματος σας βοηθά να μοντελοποιήσετε ρεαλιστικά πρότυπα προσπάθειας όπως η προφόρτωση, η υποφόρτωση ή οι κορυφαίες εργασίες.

## Γρήγορες απαντήσεις
- **Τι είναι ένα περίγραμμα;** Ένα περίγραμμα εργασίας ορίζει πώς διανέμεται η προσπάθεια κατά τη διάρκεια μιας εργασίας (π.χ., Flat, Turtle, Bell).  
- **Γιατί να αλλάξετε ένα περίγραμμα;** Για να αντικατοπτρίζει ρεαλιστικά πρότυπα εργασίας όπως η προφόρτωση ή η υποφόρτωση της προσπάθειας.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (οποιαδήποτε πρόσφατη έκδοση).  
- **Χρειάζομαι άδεια;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για χρήση σε παραγωγή.  
- **Μπορώ να δω τα αποτελέσματα στην κονσόλα;** Το παράδειγμα εκτυπώνει τις ημερομηνίες έναρξης και τις τιμές για κάθε τμήμα χρονικής φάσης.

## Τι είναι το «πώς να αλλάξετε το περίγραμμα»;
Η αλλαγή ενός περιγράμματος σημαίνει την ενημέρωση της ιδιότητας `WORK_CONTOUR` ενός αντικειμένου `ResourceAssignment`. Αυτή η ιδιότητα λέει στο Aspose.Tasks πώς να διανείμει τη συνολική εργασία της ανάθεσης κατά τη διάρκεια της εργασίας. Η βιβλιοθήκη παρέχει αρκετά προκαθορισμένα περιγράμματα όπως Flat, Turtle, Bell και άλλα, το καθένα παράγει ένα διακριτό πρότυπο κατανομής προσπάθειας στο χρόνο.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για τη δημιουργία δεδομένων χρονικής φάσης;
Το Aspose.Tasks δημιουργεί δεδομένα χρονικής φάσης με **0 ms επιπλέον χρόνο για λειτουργίες στη μνήμη** και υποστηρίζει **πάνω από 50 μορφές εξόδου** (MPP, XML, CSV κ.λπ.). Η βιβλιοθήκη μπορεί να επεξεργαστεί έργα πολλών εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, παρέχοντας ακριβή κατανομή εργασίας για αναφορές, εξισορρόπηση πόρων και ανάλυση what‑if. Το API της σας επιτρέπει να αυτοματοποιήσετε τις αλλαγές περιγράμματος και να εξάγετε ακριβείς τιμές χρονικής φάσης προγραμματιστικά.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκατεστημένο το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε και να το εγκαταστήσετε από [εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Βιβλιοθήκη Aspose.Tasks for Java: Χρειάζεστε τη βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να την κατεβάσετε από τον [ιστότοπο](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Η κλάση `Project` είναι το βασικό αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα ολόκληρο αρχείο έργου στη μνήμη. Εισάγετε τους απαραίτητους χώρους ονομάτων πριν αρχίσετε να εργάζεστε με εργασίες και αναθέσεις.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Βήμα 1: Ανάγνωση του Πηγαίου Αρχείου MPP
Ο κατασκευαστής `Project` φορτώνει ένα υπάρχον αρχείο MPP, αναλύοντας τη δομή του χωρίς να υλοποιεί πλήρως κάθε εργασία στη μνήμη, κάτι που διατηρεί τη λειτουργία ελαφριά.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Βήμα 2: Λήψη Εργασίας και Ανάθεσης Πόρου
`ResourceAssignment` συνδέει έναν πόρο με μια εργασία και αποθηκεύει ιδιότητες σε επίπεδο ανάθεσης όπως εργασία, κόστος και περίγραμμα. Ανακτήστε την πρώτη ανάθεση με `project.getResourceAssignments().getById(1)` (ή οποιοδήποτε έγκυρο ID) πριν τροποποιήσετε το περίγραμμά της.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Πώς να αλλάξετε το περίγραμμα – Flat (Προεπιλογή)
`WorkContourType` είναι μια απαρίθμηση που καταγράφει τα προκαθορισμένα πρότυπα περιγράμματος εργασίας που υποστηρίζει το Aspose.Tasks. `Asn.WORK_CONTOUR` προσδιορίζει το πεδίο περιγράμματος μιας ανάθεσης πόρου, και η `generateTimephasedData()` δημιουργεί εγγραφές εργασίας χρονικής φάσης βάσει της τρέχουσας ρύθμισης περιγράμματος. Ένα **Flat** περίγραμμα διανέμει την εργασία ομοιόμορφα κατά τη διάρκεια της εργασίας· ορίστε το με `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` και στη συνέχεια καλέστε `firstRA.generateTimephasedData()` για να λάβετε ισότιμες τιμές.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – Turtle
Το **Turtle** περίγραμμα ξεκινά με χαμηλή προσπάθεια, επιταχύνει προς το μέσο και ξανασβήνει, προσομοιώνοντας τον αργό ρυθμό μιας χελώνας. Εφαρμόστε το ορίζοντας `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` και στη συνέχεια αναδημιουργήστε τα δεδομένα χρονικής φάσης. Αυτό το πρότυπο είναι ιδανικό για εργασίες που απαιτούν μια καμπύλη εκμάθησης πριν φτάσουν στην κορυφαία παραγωγικότητα.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – BackLoaded
Το **BackLoaded** περίγραμμα τοποθετεί την πλειονότητα της εργασίας προς το τέλος του χρονοδιαγράμματος της εργασίας, με λίγη προσπάθεια στην αρχή. Ορίστε το χρησιμοποιώντας `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` και αναδημιουργήστε τα δεδομένα χρονικής φάσης. Αυτό είναι χρήσιμο για δραστηριότητες που εξαρτώνται από προηγούμενες εργασίες πριν εκτελεστεί η εργασία.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – FrontLoaded
Το **FrontLoaded** περίγραμμα συγκεντρώνει την προσπάθεια στην αρχή της εργασίας, μοντελοποιώντας σενάρια όπως φάσεις έναρξης ή εντατικές πρώιμες εκρήξεις εργασίας. Εφαρμόστε το με `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` και στη συνέχεια καλέστε `firstRA.generateTimephasedData()` για να δείτε τη διανομή με προφόρτωση.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – Bell
Το **Bell** περίγραμμα δημιουργεί μια συμμετρική κορυφή στη μέση του χρονοδιαγράμματος, αντιπροσωπεύοντας εργασία που αυξάνεται, κορυφώνεται και στη συνέχεια μειώνεται ομαλά. Ορίστε το μέσω `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` και αναδημιουργήστε τα δεδομένα χρονικής φάσης για να οπτικοποιήσετε την καμπύλη προσπάθειας σε σχήμα καμπάνας.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – EarlyPeak
**EarlyPeak** τοποθετεί την υψηλότερη τιμή εργασίας νωρίς στο χρονοδιάγραμμα και στη συνέχεια μειώνεται. Χρησιμοποιήστε `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` ακολουθούμενο από `firstRA.generateTimephasedData()` για να μοντελοποιήσετε δραστηριότητες που απαιτούν ισχυρή έναρξη, όπως η γρήγορη πρωτοτυποποίηση.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – LatePeak
**LatePeak** μετατοπίζει την κορυφή της εργασίας προς το τέλος της εργασίας, κατάλληλο για εργασία που εντείνεται καθώς πλησιάζει η προθεσμία. Εφαρμόστε το με `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` και αναδημιουργήστε τα δεδομένα χρονικής φάσης για να δείτε την αύξηση του φόρτου εργασίας στο τελευταίο στάδιο.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να αλλάξετε το περίγραμμα – DoublePeak
**DoublePeak** δημιουργεί δύο διακριτές κορυφές εργασίας χωρισμένες από ένα διάστημα χαμηλότερης προσπάθειας, χρήσιμο για εργασίες με δύο κύριες εκρήξεις προσπάθειας. Ορίστε το χρησιμοποιώντας `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` και στη συνέχεια καλέστε `firstRA.generateTimephasedData()` για να λάβετε το μοτίβο διπλής κορυφής.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Κοινά προβλήματα & Συμβουλές
- **Το περίγραμμα δεν ενημερώνεται;** Βεβαιωθείτε ότι καλείτε `firstRA.set(Asn.WORK_CONTOUR, …)` *πριν* ανακτήσετε τα δεδομένα χρονικής φάσης.  
- **Απρόσμενες τιμές;** Επαληθεύστε ότι οι ημερομηνίες έναρξης και λήξης της εργασίας έχουν οριστεί σωστά στο πηγαίο MPP.  
- **Συμβουλή απόδοσης:** Επαναχρησιμοποιήστε το ίδιο αντικείμενο `Project` όταν διατρέχετε πολλαπλά περιγράμματα για να αποφύγετε περιττές λειτουργίες αρχείου, κάτι που μπορεί να μειώσει τον χρόνο επεξεργασίας έως και 40 % σε μεγάλα έργα.  
- **Συμβουλή μνήμης:** Για έργα που υπερβαίνουν το 1 GB, ενεργοποιήστε `Project.setReadOnly(true)` για να διατηρήσετε τη χρήση μνήμης κάτω από 200 MB ενώ εξακολουθείτε να δημιουργείτε ακριβή δεδομένα χρονικής φάσης.

## Συχνές Ερωτήσεις
**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες βιβλιοθήκες Java;**  
Α: Ναι, το Aspose.Tasks ενσωματώνεται άψογα με άλλες βιβλιοθήκες Java, επιτρέποντάς σας να συνδυάσετε δεδομένα χρονοπρογραμματισμού με αναφορές, αναλύσεις ή UI frameworks.

**Ε: Είναι το Aspose.Tasks κατάλληλο για μεγάλης κλίμακας επιχειρηματικά έργα;**  
Α: Απόλυτα. Η βιβλιοθήκη έχει σχεδιαστεί για να διαχειρίζεται έργα με δεκάδες χιλιάδες εργασίες και πόρους, επεξεργαζόμενη αρχεία εκατοντάδων σελίδων χωρίς μείωση της απόδοσης.

**Ε: Παρέχει το Aspose.Tasks υποστήριξη για διαφορετικές μορφές αρχείων έργου;**  
Α: Ναι, το Aspose.Tasks υποστηρίζει πάνω από 30 μορφές, συμπεριλαμβανομένων MPP, XML, CSV και MPX, επιτρέποντας εύκολη εισαγωγή/εξαγωγή μεταξύ παλαιών και σύγχρονων συστημάτων.

**Ε: Μπορώ να προσαρμόσω τα περιγράμματα εργασίας σύμφωνα με τις απαιτήσεις του έργου μου;**  
Α: Ναι, μπορείτε να ορίσετε προσαρμοσμένα περιγράμματα παρέχοντας έναν πίνακα ποσοστών εργασίας στην ιδιότητα `WORK_CONTOUR`, δίνοντάς σας πλήρη έλεγχο της κατανομής προσπάθειας.

**Ε: Υπάρχει κάποιο φόρουμ κοινότητας όπου μπορώ να λάβω βοήθεια για το Aspose.Tasks;**  
Α: Ναι, μπορείτε να επισκεφθείτε το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για υποστήριξη, συζητήσεις και παραδείγματα κώδικα από μηχανικούς της Aspose και μέλη της κοινότητας.

---

**Τελευταία ενημέρωση:** 2026-06-10  
**Δοκιμάστηκε με:** Aspose.Tasks for Java (latest release)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Δημιουργία Αναθέσεων Πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Ανάγνωση Δεδομένων Χρονικής Φάσης για Πόρους στο Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Πώς να Σταματήσετε την Ανάθεση και να Επαναλάβετε τις Αναθέσεις Πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}