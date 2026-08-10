---
date: 2026-06-15
description: Μάθετε πώς να εξάγετε δεδομένα χρονοδιαγράμματος από πόρους του MS Project
  χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα‑βήμα για τη λήψη πόρου με
  id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Ανάγνωση δεδομένων χρονοδιαγράμματος για πόρους στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ανάγνωση δεδομένων χρονοδιαγράμματος για πόρους στο Aspose.Tasks – λήψη πόρου
  με id
url: /el/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε Δεδομένα Χρονικής Φάσης για Πόρους στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial, θα μάθετε **how to get resource by id** και θα διαβάσετε τα χρονικά δεδομένα του χρησιμοποιώντας το Aspose.Tasks for Java. Θα περάσουμε βήμα-βήμα από τη ρύθμιση του φακέλου του έργου μέχρι την εκτύπωση των χρονικών τιμών εργασίας και κόστους—ώστε να μπορείτε να εξάγετε πολύτιμες πληροφορίες χρονοπρογραμματισμού από οποιοδήποτε αρχείο Microsoft Project προγραμματιστικά. Το Aspose.Tasks for Java είναι ένα ολοκληρωμένο API που επιτρέπει στους προγραμματιστές να δημιουργούν, διαβάζουν, τροποποιούν και μετατρέπουν αρχεία Microsoft Project χωρίς να απαιτείται εγκατάσταση του Microsoft Project, υποστηρίζοντας ένα ευρύ φάσμα λειτουργιών και μορφών διαχείρισης έργων.

## Γρήγορες Απαντήσεις
- **Τι κάνει το “get resource by id”;** Επιστρέφει ένα συγκεκριμένο αντικείμενο `Resource` από ένα `Project` χρησιμοποιώντας το μοναδικό του αναγνωριστικό.  
- **Ποια βιβλιοθήκη διαχειρίζεται τα χρονικά δεδομένα;** Το Aspose.Tasks for Java παρέχει το API `Resource.getTimephasedData`.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να διαβάσω μεγάλα έργα;** Ναι—το Aspose.Tasks μπορεί να επεξεργαστεί αρχεία με έως και 10.000 εργασίες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.  
- **Ποια έκδοση της Java απαιτείται;** Java 8 ή νεότερη· η βιβλιοθήκη είναι συμβατή με όλα τα κύρια JDK.

## Τι είναι το “get resource by id”;
`get resource by id` είναι μια κλήση μεθόδου που φέρνει ένα αντικείμενο `Resource` από ένα φορτωμένο `Project` χρησιμοποιώντας το αριθμητικό ID του πόρου. Αυτή η λειτουργία επιτρέπει ακριβή πρόσβαση στις λεπτομερείς ιδιότητες ενός πόρου, όπως οι εκχωρήσεις, τα ημερολόγια και τα προσαρμοσμένα πεδία του, και είναι απαραίτητη για την εξαγωγή χρονικών δεδομένων εργασίας ή κόστους που σχετίζονται με αυτόν τον συγκεκριμένο πόρο.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για χρονικά δεδομένα;
Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** (MPP, XML, CSV κ.λπ.) και μπορεί να εξάγει χρονικές τιμές εργασίας και κόστους για πόρους που καλύπτουν πολυετή χρονοδιαγράμματα, διατηρώντας χαμηλή χρήση μνήμης. Το API επιστρέφει δεδομένα σε διαστήματα 15 λεπτών από προεπιλογή, παρέχοντάς σας λεπτομερή εικόνα για αναφορές ή προσαρμοσμένες αναλύσεις.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκατεστημένο το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από την [ιστοσελίδα](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) και να ακολουθήσετε τις οδηγίες εγκατάστασης.  
2. Βιβλιοθήκη Aspose.Tasks for Java: Κατεβάστε τη βιβλιοθήκη Aspose.Tasks for Java από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

## Εισαγωγή Πακέτων
Το πρώτο βήμα είναι η εισαγωγή των απαιτούμενων κλάσεων Aspose.Tasks στο αρχείο πηγαίου κώδικα Java.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Βήμα 1: Ρύθμιση Καταλόγου Δεδομένων
Πρώτα, ορίστε τον κατάλογο όπου βρίσκεται το αρχείο MS Project σας. Η διατήρηση του φακέλου δεδομένων ξεχωριστά από τον πηγαίο κώδικα καθιστά το έργο πιο εύκολο στη συντήρηση.

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Ανάγνωση Αρχείου Προτύπου MS Project
Καθορίστε το όνομα του αρχείου προτύπου MS Project σας. Η χρήση προτύπου εξασφαλίζει συνεπείς ρυθμίσεις στηλών μεταξύ διαφορετικών έργων.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Βήμα 3: Ανάγνωση Αρχείου Εισόδου ως Project
Η κλάση `Project` είναι το βασικό αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη. Η φόρτωση του αρχείου σας παρέχει προγραμματιστική πρόσβαση σε εργασίες, πόρους και χρονοδιαγράμματα.

```java
Project project = new Project(dataDir + fileName);
```

## Βήμα 4: Λήψη Πόρου με ID
Για να λάβετε έναν συγκεκριμένο πόρο, καλέστε τη μέθοδο `getResources().getById(id)`. Αυτή είναι η ακριβής λειτουργία που αναφέρεται από τη βασική λέξη-κλειδί.

```java
Resource resource = project.getResources().getByUid(1);
```

## Βήμα 5: Εκτύπωση Χρονικών Δεδομένων για Εργασία Πόρου
Μόλις έχετε το αντικείμενο `Resource`, μπορείτε να καλέσετε `resource.getTimephasedData(ResourceTimephasedDataType.Work)` για να λάβετε τις κατανομές εργασίας με την πάροδο του χρόνου. Η επιστρεφόμενη συλλογή περιέχει αντικείμενα `TimephasedData` που περιλαμβάνουν την ημερομηνία έναρξης, την ημερομηνία λήξης και την ποσότητα εργασίας για κάθε διάστημα.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Βήμα 6: Εκτύπωση Χρονικών Δεδομένων για Κόστος Πόρου
Ανάλογα, το `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` επιστρέφει πληροφορίες κόστους διαχωρισμένες κατά τα ίδια χρονικά διαστήματα. Αυτό είναι χρήσιμο για αναφορές προϋπολογισμού και παρακολούθησης κόστους.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Πώς να Λάβετε Πόρο με ID σε Μία Γραμμή;
Φορτώστε το έργο, στη συνέχεια καλέστε `project.getResources().getById(5)`—αντικαταστήστε το **5** με το πραγματικό ID του πόρου που χρειάζεστε. Αυτή η ενιαία κλήση επιστρέφει το αντικείμενο `Resource`, μετά το οποίο μπορείτε να ερωτήσετε τα χρονικά του δεδομένα, τις εκχωρήσεις ή τα προσαρμοσμένα πεδία. Η μέθοδος εκτελείται σε χρόνο O(1) επειδή οι πόροι είναι εσωτερικά ευρετηριασμένοι.

## Συνηθισμένα Προβλήματα και Λύσεις
- **Resource not found** – Βεβαιωθείτε ότι το ID υπάρχει στο αρχείο του έργου· τα IDs ξεκινούν από 1 και είναι μοναδικά ανά πόρο.  
- **Empty timephased data** – Επαληθεύστε ότι ο πόρος έχει εκχωρήσεις εργασίας ή κόστους· διαφορετικά η συλλογή θα είναι κενή.  
- **Large file performance** – Χρησιμοποιήστε `Project.setLoadOptions(LoadOptions.fromFile(...))` για να ενεργοποιήσετε τη lazy φόρτωση για έργα μεγαλύτερα από 500 MB.

## Συχνές Ερωτήσεις

**Q: Μπορεί το Aspose.Tasks να χειριστεί άλλους τύπους αρχείων έργου εκτός από το Microsoft Project;**  
A: Ναι, το Aspose.Tasks υποστηρίζει MPP, XML, CSV και αρκετές άλλες μορφές, επιτρέποντάς σας να διαβάζετε και να γράφετε μεταξύ διαφορετικών προτύπων.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικά περιβάλλοντα ανάπτυξης Java;**  
A: Απολύτως. Η βιβλιοθήκη λειτουργεί με όλα τα κύρια IDE (IntelliJ IDEA, Eclipse, NetBeans) και εργαλεία κατασκευής (Maven, Gradle).

**Q: Μπορώ να χειριστώ τα δεδομένα του έργου χρησιμοποιώντας το Aspose.Tasks;**  
A: Ναι, μπορείτε να δημιουργήσετε, τροποποιήσετε και διαγράψετε εργασίες, πόρους, εκχωρήσεις και ακόμη προσαρμοσμένα πεδία μέσω του API.

**Q: Είναι το Aspose.Tasks κατάλληλο για έργα επιπέδου επιχείρησης;**  
A: Ναι. Οι επιχειρήσεις βασίζονται στο Aspose.Tasks για επεξεργασία μεγάλου όγκου, μαζικές μετατροπές και αναφορές από την πλευρά του διακομιστή, επειδή δεν απαιτεί εγκατάσταση του Microsoft Project.

**Q: Πού μπορώ να βρω υποστήριξη εάν αντιμετωπίσω προβλήματα κατά τη χρήση του Aspose.Tasks;**  
A: Μπορείτε να επισκεφθείτε το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για βοήθεια από την κοινότητα και την ομάδα υποστήριξης.

## Συμπέρασμα
Σε αυτό το tutorial, μάθαμε πώς να **get resource by id** και να διαβάσουμε τα χρονικά δεδομένα εργασίας και κόστους του χρησιμοποιώντας το Aspose.Tasks for Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να εξάγετε αποδοτικά πολύτιμες πληροφορίες χρονοπρογραμματισμού από τα αρχεία του έργου σας και να τις ενσωματώσετε σε προσαρμοσμένες αναφορές ή pipelines ανάλυσης.

---

**Τελευταία ενημέρωση:** 2026-06-15  
**Δοκιμάστηκε με:** Aspose.Tasks 24.11 for Java  
**Συγγραφέας:** Aspose

## Σχετικά Tutorials

- [Προσθήκη πόρου στο έργο με Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Διαχείριση Κόστους Πόρων MS Project με Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Ανάγνωση Εβδομάδων Εργασίας Java από το Ημερολόγιο MS Project με Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}