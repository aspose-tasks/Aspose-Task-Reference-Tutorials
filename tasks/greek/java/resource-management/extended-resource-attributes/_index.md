---
date: 2026-06-10
description: Μάθετε πώς να δημιουργήσετε extended attribute σε Java, να φορτώσετε
  ένα αρχείο Microsoft Project, να ορίσετε numeric values και να αποθηκεύσετε το έργο
  ως XML χρησιμοποιώντας Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Διαχείριση Extended Resource Attributes στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να δημιουργήσετε extended attribute σε Java με Aspose.Tasks
url: /el/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε εκτεταμένο χαρακτηριστικό σε Java με Aspose.Tasks

## Εισαγωγή
Σε αυτόν τον πρακτικό οδηγό θα **δημιουργήσετε εκτεταμένο χαρακτηριστικό σε Java** για ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks. Θα περάσουμε από τη φόρτωση ενός υπάρχοντος έργου, τον ορισμό ενός νέου αριθμητικού χαρακτηριστικού, την ανάθεση μιας τιμής σε έναν πόρο και, τελικά, την αποθήκευση των αλλαγών ως αρχείο XML. Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο πρότυπο κώδικα που μπορεί να ενσωματωθεί σε οποιαδήποτε λύση διαχείρισης έργων βασισμένη σε Java.

## Γρήγορες Απαντήσεις
- **Τι είναι ένα εκτεταμένο χαρακτηριστικό;**  
  Ένα πεδίο ορισμένο από τον χρήστη (π.χ., Ηλικία, Επίπεδο Δεξιοτήτων) που αποθηκεύει πρόσθετα δεδομένα για πόρους ή εργασίες.  
- **Ποιο API το δημιουργεί;**  
  Το Aspose.Tasks for Java παρέχει την κλάση `ExtendedAttributeDefinition` για τον ορισμό και τη διαχείριση προσαρμοσμένων χαρακτηριστικών.  
- **Χρειάζομαι άδεια;**  
  Μια προσωρινή άδεια αξιολόγησης λειτουργεί για ανάπτυξη· απαιτείται πλήρης άδεια για παραγωγικές εγκαταστάσεις.  
- **Μπορώ να αποθηκεύσω αριθμούς;**  
  Ναι – χρησιμοποιήστε `setNumericValue(BigDecimal)` για να ορίσετε ακριβείς δεκαδικές τιμές.  
- **Πώς αποθηκεύω τις αλλαγές;**  
  Καλέστε `project.save("output.xml", SaveFileFormat.Xml)` για να γράψετε το ενημερωμένο έργο σε μορφή XML.

## Τι είναι ένα προσαρμοσμένο χαρακτηριστικό;
Ένα **προσαρμοσμένο χαρακτηριστικό** (γνωστό επίσης ως εκτεταμένο χαρακτηριστικό) είναι μια πρόσθετη στήλη που μπορείτε να προσθέσετε σε πόρους ή εργασίες στο Microsoft Project. Σας επιτρέπει να καταγράψετε δεδομένα που δεν καλύπτονται από τα ενσωματωμένα πεδία, όπως η ηλικία των υπαλλήλων, το επίπεδο πιστοποίησης ή οποιοδήποτε επιχειρηματικό μέτρο.

## Γιατί να δημιουργήσετε εκτεταμένο χαρακτηριστικό σε Java;
Η δημιουργία εκτεταμένου χαρακτηριστικού σε Java σας επιτρέπει να εμπλουτίζετε προγραμματιστικά τα δεδομένα του έργου, εξασφαλίζοντας συνέπεια μεταξύ των αρχείων και επιτρέποντας αυτοματοποιημένες αναφορές. Ορίζοντας το χαρακτηριστικό μία φορά, μπορείτε να το εφαρμόσετε σε οποιονδήποτε αριθμό πόρων ή εργασιών χωρίς χειροκίνητη εισαγωγή, εξοικονομώντας χρόνο και μειώνοντας τα σφάλματα.

- **Προσαρμόστε τα δεδομένα στην οργάνωσή σας** – αποθηκεύστε οποιοδήποτε μέτρο που σας ενδιαφέρει χωρίς χειροκίνητες παρακάμψεις του Excel.  
- **Ενεργοποιήστε πιο πλούσιες αναφορές** – ερωτήστε το προσαρμοσμένο πεδίο αργότερα για πίνακες ελέγχου ή αναλύσεις.  
- **Διατηρήστε τη συνέπεια** – εφαρμόστε προγραμματιστικά τον ίδιο ορισμό σε δεκάδες έργα, εξαλείφοντας τα ανθρώπινα λάθη.  
- **Δοκιμασμένη απόδοση** – το Aspose.Tasks επεξεργάζεται έργα με έως και 10.000 εργασίες και 5.000 πόρους χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, σύμφωνα με τα benchmarks του προϊόντος.

## Προαπαιτούμενα
1. **Java Development Kit** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java** – κατεβάστε την τελευταία έκδοση από [εδώ](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA ή οποιοδήποτε περιβάλλον ανάπτυξης συμβατό με Java.  

## Πώς να δημιουργήσετε εκτεταμένο χαρακτηριστικό σε Java;
Φορτώστε το έργο σας, ορίστε το χαρακτηριστικό, συνδέστε το με έναν πόρο και αποθηκεύστε το αρχείο – όλα σε λίγα απλά βήματα. Οι παρακάτω ενότητες χωρίζουν κάθε βήμα σε μια σύντομη εξήγηση, ακολουθούμενη από το placeholder όπου βρίσκεται ο πραγματικός κώδικάς σας.

### Οδηγός Βήμα‑Βήμα

#### Εισαγωγή Πακέτων
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` και οι σχετικές κλάσεις βρίσκονται στο namespace `com.aspose.tasks`. Εισάγετέ τις στην αρχή του αρχείου Java.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Βήμα 1: Ορισμός Καταλόγου Δεδομένων
`Paths` είναι μια βοηθητική κλάση που παρέχει μεθόδους για την απόκτηση διαδρομής συστήματος αρχείων με ανεξάρτητο από την πλατφόρμα τρόπο.

```java
String dataDir = "Your Data Directory";
```

#### Βήμα 2: Φόρτωση Αρχείου Microsoft Project
`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη, επιτρέποντας ανάγνωση και εγγραφή των περιεχομένων του.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Βήμα 3: Ορισμός του Προσαρμοσμένου Χαρακτηριστικού
`ExtendedAttributeDefinition` ορίζει το σχήμα ενός νέου προσαρμοσμένου πεδίου που μπορεί να προσαρτηθεί σε πόρους ή εργασίες.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Βήμα 4: Ορισμός Αριθμητικής Τιμής σε Java
`ExtendedAttributeResource` περιέχει την τιμή ενός προσαρμοσμένου χαρακτηριστικού για ένα συγκεκριμένο παράδειγμα πόρου.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Βήμα 5: Προσθήκη Πόρου και Σύνδεση του Προσαρμοσμένου Χαρακτηριστικού
`Resource` μοντελοποιεί έναν πόρο του έργου όπως άτομο, εξοπλισμό ή υλικό.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Βήμα 6: Αποθήκευση Έργου ως XML
`SaveFileFormat` απαριθμεί τις υποστηριζόμενες μορφές εξόδου για την αποθήκευση ενός έργου, συμπεριλαμβανομένου του XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Βήμα 7: Εμφάνιση Αποτελέσματος
`System.out.println` εκτυπώνει μια γραμμή κειμένου στην τυπική έξοδο της κονσόλας.

```java
System.out.println("Process completed Successfully");
```

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές
- **Συγκρούσεις ID χαρακτηριστικού:** Πάντα καλέστε `project.getExtendedAttributes().getById(id)` πριν δημιουργήσετε νέο ορισμό για να αποτρέψετε διπλότυπα αναγνωριστικά.  
- **Διαχείριση ακρίβειας:** Προτιμήστε `BigDecimal` αντί για `float`/`double` για ακριβείς αριθμητικές τιμές· αυτό αποτρέπει σφάλματα στρογγυλοποίησης στις αναφορές.  
- **Αξιοπιστία διαδρομής αρχείου:** Χρησιμοποιήστε `Paths.get(...).toAbsolutePath()` ή ρυθμίστε τον κατάλογο εργασίας του IDE σας για να εξαλείψετε το `FileNotFoundException`.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να δημιουργήσω προσαρμοσμένα χαρακτηριστικά για εργασίες καθώς και για πόρους;**  
A: Ναι – χρησιμοποιήστε `ExtendedAttributeTask` αντί για `ExtendedAttributeResource` όταν ορίζετε το σχήμα του χαρακτηριστικού.

**Q: Μπορεί να προστεθούν πολλαπλά προσαρμοσμένα χαρακτηριστικά ταυτόχρονα;**  
A: Απόλυτα. Δημιουργήστε ξεχωριστά αντικείμενα `ExtendedAttributeDefinition` για κάθε χαρακτηριστικό και συνδέστε τα με τους επιθυμητούς πόρους ή εργασίες.

**Q: Σε ποιες μορφές μπορώ να αποθηκεύσω το έργο;**  
A: Το Aspose.Tasks υποστηρίζει XML, MPP, PDF, HTML και περισσότερες από 30 επιπλέον μορφές. Σε αυτό το παράδειγμα χρησιμοποιήσαμε το `SaveFileFormat.Xml`.

**Q: Χρειάζομαι άδεια για εκδόσεις ανάπτυξης;**  
A: Μια προσωρινή άδεια αξιολόγησης είναι επαρκής για δοκιμές. Για οποιαδήποτε παραγωγική εγκατάσταση απαιτείται πλήρης εμπορική άδεια.

**Q: Πώς μπορώ να διαβάσω ξανά τις τιμές του προσαρμοσμένου χαρακτηριστικού αργότερα;**  
A: Καλέστε `resource.getExtendedAttributes()` και επαναλάβετε τη συλλογή· ανακτήστε την αποθηκευμένη τιμή με `getNumericValue()` ή `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Πόρους – Διαχείριση Πόρων με Aspose.Tasks for Java](/tasks/java/resource-management/)
- [Δημιουργία προσαρμοσμένου πεδίου Aspose - Διαχείριση εκτεταμένων χαρακτηριστικών](/tasks/java/project-management/extended-attributes/)
- [Πώς να Δημιουργήσετε Έργο – Ορισμός Νέων Χαρακτηριστικών Εργασιών με Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}