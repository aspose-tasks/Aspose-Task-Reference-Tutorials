---
date: 2026-06-05
description: Μάθετε πώς να φιλτράρετε αρχεία MPP χρησιμοποιώντας το Aspose.Tasks για
  Java, προσαρμόστε τα κριτήρια φιλτραρίσματος και φιλτράρετε τις εργασίες κατά ημερομηνία
  για να βελτιώσετε τη διαχείριση έργων.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Πώς να φιλτράρετε αρχεία MPP χρησιμοποιώντας το Aspose.Tasks για Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να φιλτράρετε αρχεία MPP χρησιμοποιώντας το Aspose.Tasks για Java
url: /el/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Φιλτράρετε Αρχεία MPP Χρησιμοποιώντας το Aspose.Tasks για Java

## Εισαγωγή
Εάν εργάζεστε με αρχεία Microsoft Project (*.mpp*) σε μια εφαρμογή Java, συχνά θα χρειαστεί να **φιλτράρετε αρχεία MPP** για να απομονώσετε τις εργασίες, τους πόρους ή τις αναθέσεις που έχουν τη μεγαλύτερη σημασία. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα πώς να **φιλτράρετε mpp** αρχεία προγραμματιστικά με το Aspose.Tasks για Java, θα σας δείξουμε πώς να **προσαρμόσετε τα κριτήρια φίλτρου** και θα παρουσιάσουμε ένα πρακτικό σενάριο “φιλτράρισμα εργασιών κατά ημερομηνία”. Στο τέλος θα έχετε ένα έτοιμο κομμάτι κώδικα που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο Java.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “filter mpp”;** Σημαίνει την εξαγωγή ενός υποσυνόλου των δεδομένων του έργου βάσει ορισμένων συνθηκών.  
- **Ποια βιβλιοθήκη το διαχειρίζεται;** Το Aspose.Tasks για Java παρέχει ένα ολοκληρωμένο API για τη δημιουργία και την εφαρμογή φίλτρων.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να φιλτράρω εργασίες, πόρους και αναθέσεις;** Ναι – κάθε τύπος οντότητας έχει τη δική του συλλογή φίλτρων.  
- **Απαιτείται Java 8 ή νεότερη έκδοση;** Το Aspose.Tasks υποστηρίζει Java 8 και μεταγενέστερες εκδόσεις.

## Τι είναι το “how to filter mpp” σε Java;
`How to filter mpp` είναι η διαδικασία χρήσης των αντικειμένων `Filter` του Aspose.Tasks για την επιλογή μόνο εκείνων των στοιχείων του έργου που ικανοποιούν συγκεκριμένα κριτήρια όπως ημερομηνία έναρξης, κόστος ή προσαρμοσμένα πεδία. Φορτώστε ένα `Project`, ανακτήστε ένα `Filter`, και το API επιστρέφει μια συλλογή που ταιριάζει στα κριτήριά σας, επιτρέποντας εστιασμένες αναφορές ή ενσωμάτωση σε επόμενα στάδια.

## Γιατί να προσαρμόσετε τα κριτήρια φίλτρου;
Τα προσαρμοσμένα κριτήρια φίλτρου σας επιτρέπουν να στοχεύετε εργασίες υψηλού κινδύνου, καθυστερημένα στοιχεία ή πόρους με υπέρβαση προϋπολογισμού, μετατρέποντας ένα τεράστιο αρχείο έργου σε μια σύντομη, πρακτική προβολή. Το Aspose.Tasks υποστηρίζει **πάνω από 50 προκαθορισμένους τύπους φίλτρων** και σας επιτρέπει να δημιουργήσετε απεριόριστα προσαρμοσμένα φίλτρα, μειώνοντας τον χρόνο χειροκίνητης επεξεργασίας δεδομένων έως και 70 %.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το από τη [download page](https://releases.aspose.com/tasks/java/).  
3. **Ένα IDE** – IntelliJ IDEA, Eclipse ή NetBeans θα λειτουργήσουν καλά.  

## Εισαγωγή Πακέτων
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` και `Project` είναι βασικές κλάσεις που χρησιμοποιούνται για τον ορισμό και την εφαρμογή φίλτρων στα δεδομένα του έργου.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Ρύθμιση του Έργου
Πρώτα, δημιουργήστε μια παρουσία `Project` που δείχνει στο αρχείο MPP που θέλετε να αναλύσετε, και στη συνέχεια φορτώστε το στη μνήμη. Αυτό το μοναδικό βήμα προετοιμάζει ολόκληρο το μοντέλο του έργου για φιλτράρισμα, επικύρωση και περαιτέρω επεξεργασία, επιτρέποντάς σας να έχετε πρόσβαση σε εργασίες, πόρους και αναθέσεις μέσω του API.

### Πώς ρυθμίζω το έργο για να φιλτράρω αρχεία MPP;
Η κλάση `Project` φορτώνει και αντιπροσωπεύει ένα αρχείο MPP στη μνήμη. Δημιουργήστε μια παρουσία `Project` που δείχνει στο αρχείο MPP που θέλετε να αναλύσετε, και στη συνέχεια φορτώστε το στη μνήμη. Αυτό το μοναδικό βήμα προετοιμάζει ολόκληρο το μοντέλο του έργου για φιλτράρισμα, επικύρωση και περαιτέρω επεξεργασία, επιτρέποντάς σας να έχετε πρόσβαση σε εργασίες, πόρους και αναθέσεις μέσω του API.

### Πώς μπορώ να ανακτήσω και να εξετάσω ένα φίλτρο;
Τα αντικείμενα `Filter` περιλαμβάνουν τους ορισμούς φίλτρων που χρησιμοποιούνται για την επιλογή στοιχείων του έργου. Το Aspose.Tasks αποθηκεύει προκαθορισμένα φίλτρα όπως “All Tasks” ή “Critical Tasks”. Χρησιμοποιήστε `project.getTaskFilters().getByName("My Filter")` ή πρόσβαση με δείκτη για να αποκτήσετε ένα αντικείμενο `Filter`, στη συνέχεια εξετάστε τη συλλογή `FilterCriteria` του για να δείτε κάθε κανόνα και τον λογικό τελεστή (AND/OR) που τα συνδυάζει, διασφαλίζοντας ότι το φίλτρο ταιριάζει με τις απαιτήσεις σας.

### Πώς να επαναλάβετε τις σειρές ένθετων κριτηρίων;
`FilterCriteriaGroup` αντιπροσωπεύει μια ομάδα κριτηρίων φίλτρου που συνδυάζονται με λογικό τελεστή. Τα φίλτρα μπορούν να περιέχουν ομάδες κριτηρίων, κάθε μία με τον δικό της τελεστή. Επανάλαβε μέσω `filter.getCriteria().getRows()` και, για κάθε σειρά που είναι `FilterCriteriaGroup`, επανέλαβε στις θυγατρικές σειρές της. Αυτή η διέλευση σας επιτρέπει να κατανοήσετε πλήρως τη σύνθετη λογική φίλτρου όπως “(Start < today AND Cost > 1000) OR Priority = High”, και να προσαρμόσετε τα κριτήρια όπως χρειάζεται.

### Πώς να εκτυπώσω πληροφορίες κριτηρίων για αποσφαλμάτωση;
Μετά τη διέλευση του δέντρου κριτηρίων, εκτυπώστε στο κονσόλα το όνομα πεδίου, τον τελεστή ελέγχου και την τιμή κάθε σειράς. Αυτή η απλή εκτύπωση σας βοηθά να επαληθεύσετε ότι το φίλτρο ταιριάζει με τους επιθυμητούς επιχειρηματικούς κανόνες πριν το εφαρμόσετε σε μεγάλα έργα, και διευκολύνει την εντόπιση λανθασμένων τελεστών ή τιμών.

### Πώς να δημιουργήσω ένα ολοκαίνουργιο φίλτρο προγραμματιστικά;
Δημιουργήστε ένα `Filter` με `new Filter("My Filter")`, στη συνέχεια προσθέστε το στη συλλογή φίλτρων εργασιών του έργου χρησιμοποιώντας `project.getTaskFilters().add(filter)`. Μετά, γεμίστε τη συλλογή `FilterCriteria` του με τις επιθυμητές σειρές, καθορίζοντας ονόματα πεδίων, τελεστές ελέγχου και τιμές για να ορίσετε ακριβώς ποιες εργασίες θα συμπεριληφθούν όταν εφαρμοστεί το φίλτρο.

### Μπορώ να εφαρμόσω φίλτρο σε πόρους αντί για εργασίες;
Η συλλογή `ResourceFilters` περιέχει ορισμούς φίλτρων που ισχύουν για πόρους. Ναι – χρησιμοποιήστε `project.getResourceFilters()` για να εργαστείτε με φίλτρα ειδικά για πόρους με τον ίδιο τρόπο όπως τα φίλτρα εργασιών. Μετά την προσθήκη ή ανάκτηση ενός φίλτρου, διαμορφώστε το `FilterCriteria` του όπως θα κάνατε για εργασίες, και στη συνέχεια εφαρμόστε το στη συλλογή πόρων για να λάβετε το φιλτραρισμένο σύνολο πόρων.

### Είναι δυνατόν να συνδυάσετε πολλαπλά φίλτρα με λογική OR;
Δημιουργήστε μια γονική `FilterCriteriaGroup` με την ιδιότητα `Operation` ορισμένη σε `OR`, και προσθέστε μεμονωμένα αντικείμενα `FilterCriteria` ως παιδιά. Αυτή η ομάδα θα αξιολογήσει κάθε κριτήριο παιδί και θα επιστρέψει στοιχεία που ικανοποιούν οποιοδήποτε από αυτά, επιτρέποντάς σας να συνδυάσετε πολλά απλά φίλτρα σε μια ευρύτερη επιλογή.

### Υποστηρίζει το Aspose.Tasks φιλτράρισμα σε προσαρμοσμένα πεδία;
`CustomField` enum παρέχει ταυτοποιητές για προσαρμοσμένα πεδία που ορίζονται σε ένα έργο. Απόλυτα. Αναφερθείτε στα προσαρμοσμένα πεδία μέσω του enum `CustomField`, και συμπεριφέρονται όπως οποιοδήποτε ενσωματωμένο πεδίο σε εκφράσεις φίλτρου. Μπορείτε να τα συμπεριλάβετε σε σειρές `FilterCriteria`, χρησιμοποιώντας τους ίδιους τελεστές και τιμές, επιτρέποντας ισχυρά ερωτήματα σε δεδομένα που ορίζονται από τον χρήστη μαζί με τα τυπικά χαρακτηριστικά του έργου.

### Ποιος είναι ο αντίκτυπος στην απόδοση του φιλτραρίσματος σε μεγάλα αρχεία MPP;
Το φιλτράρισμα εκτελείται εξ ολοκλήρου στη μνήμη και συνήθως επεξεργάζεται ένα έργο με 1.000 εργασίες σε λιγότερο από 200 ms. Για αρχεία με χιλιάδες εργασίες, σκεφτείτε να φορτώσετε μόνο τις απαιτούμενες ενότητες χρησιμοποιώντας `ProjectReader` και να εφαρμόσετε τα φίλτρα μετά από επιλεκτική φόρτωση, κάτι που διατηρεί τη χρήση μνήμης χαμηλή και διατηρεί γρήγορους χρόνους απόκρισης ακόμη και σε πολύ μεγάλα έργα.

---

**Τελευταία Ενημέρωση:** 2026-06-05  
**Δοκιμή Με:** Aspose.Tasks for Java 24.10  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Φόρτωση Αρχείου MPP Java - Διαχείριση Ιδιοτήτων Έργου με Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Εύκολη Ανάγνωση Δεδομένων MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Ορισμός Ημερομηνίας Έναρξης Έργου στο MS Project χρησιμοποιώντας Aspose.Tasks για Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```