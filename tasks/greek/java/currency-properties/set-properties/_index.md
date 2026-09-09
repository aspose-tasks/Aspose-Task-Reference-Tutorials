---
date: 2026-09-09
description: Μάθετε πώς να αλλάξετε το currency symbol σε έργα Aspose.Tasks Java,
  να ορίσετε currency codes, να προσαρμόσετε symbols και να εφαρμόσετε custom formats
  για αρχεία Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Ορίστε τις Currency Properties σε έργα Aspose.Tasks
og_description: Πώς να αλλάξετε το currency symbol σε Aspose.Tasks χρησιμοποιώντας
  Java. Ανακαλύψτε οδηγίες βήμα‑βήμα, προαπαιτούμενα και συμβουλές για την προσαρμογή
  της μορφοποίησης κόστους του έργου.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Πώς να αλλάξετε το currency symbol σε Aspose.Tasks – οδηγός Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Πώς να αλλάξετε το currency symbol σε έργα Aspose.Tasks – οδηγός Java
url: /el/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αλλάξετε το σύμβολο νομίσματος στο Aspose.Tasks – Οδηγός Java

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε **πώς να αλλάξετε το σύμβολο νομίσματος** για ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks Java API. Είτε ετοιμάζετε εκθέσεις για έναν πελάτη στο εξωτερικό, ενοποιείτε προϋπολογισμούς σε πολλές περιοχές, ή απλώς χρειάζεται να ταιριάξετε τα λογιστικά πρότυπα της εταιρείας σας, η προσαρμογή του συμβόλου νομίσματος εξασφαλίζει ότι κάθε πεδίο σχετικό με κόστος εμφανίζει το σωστό χρηματικό σύμβολο. Ο οδηγός περνάει από κάθε βήμα, από τη ρύθμιση του περιβάλλοντος ανάπτυξης μέχρι την αποθήκευση των αλλαγών σε νέο ή υπάρχον αρχείο έργου.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java.  
- **Μπορώ να αλλάξω το σύμβολο νομίσματος;** Ναι – ορίστε `Prj.CURRENCY_SYMBOL` και επιλέξτε `CurrencySymbolPositionType`.  
- **Ποια μορφές αρχείων υποστηρίζονται;** XML, MPP και πολλές άλλες μέσω `SaveFileFormat`.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται άδεια για παραγωγή.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 5‑10 λεπτά για μια βασική ρύθμιση.

## Πώς να αλλάξετε το σύμβολο νομίσματος στο Aspose.Tasks χρησιμοποιώντας Java;
Φορτώστε το στοχευόμενο έργο (ή δημιουργήστε ένα νέο), ορίστε τις επιθυμητές ιδιότητες νομίσματος και αποθηκεύστε το αρχείο. Η ολόκληρη λειτουργία αποτελείται από τρεις κλήσεις API: δημιουργία ή φόρτωση ενός αντικειμένου `Project`, ανάθεση του κωδικού, του συμβόλου και της θέσης του νομίσματος, και στη συνέχεια κλήση του `project.save`. Αυτή η προσέγγιση λειτουργεί τόσο για νέα έργα όσο και για υπάρχοντα αρχεία χωρίς την ανάγκη εγκατάστασης του Microsoft Project.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για αλλαγή νομίσματος;
Το Aspose.Tasks παρέχει **πλήρη κάλυψη API για 30+ ιδιότητες σχετικές με το νόμισμα**, επιτρέποντάς σας να ορίσετε κωδικό, σύμβολο, δεκαδικά ψηφία και θέση σε ένα μέρος. Η βιβλιοθήκη επεξεργάζεται αρχεία Project εκατοντάδων σελίδων σε λιγότερο από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή, και λειτουργεί σε Windows, Linux και macOS χωρίς επιπλέον εξαρτήσεις.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK) 8 ή νεότερο** – το API απαιτεί τουλάχιστον JDK 8.  
2. **Aspose.Tasks for Java** – κατεβάστε το τελευταίο JAR από τη [σελίδα λήψης Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Ένα IDE** – Eclipse, IntelliJ IDEA ή οποιονδήποτε επεξεργαστή που υποστηρίζει Java.  
4. **Ένας φάκελος με δικαιώματα εγγραφής** – όπου θα αποθηκευτεί το παραγόμενο αρχείο έργου.

## Εισαγωγή πακέτων
Οι παρακάτω κλάσεις σας δίνουν πρόσβαση στις ιδιότητες του έργου, στη διαχείριση αρχείων και στις ρυθμίσεις νομίσματος.  

`Project` – αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη.  
`Prj` – περιέχει σταθερές για όλες τις ιδιότητες επιπέδου έργου, συμπεριλαμβανομένων των πεδίων νομίσματος.  
`CurrencySymbolPositionType` – απαριθμεί τις πιθανές θέσεις για το σύμβολο νομίσματος (πριν ή μετά το ποσό).  

Αυτές οι εισαγωγές απαιτούνται πριν οποιοσδήποτε κώδικας μπορεί να χειριστεί ένα έργο.

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ορισμός του καταλόγου δεδομένων
Επιλέξτε έναν φάκελο που περιέχει τα αρχεία πηγής σας και όπου θα γραφτεί το αποτέλεσμα. Βεβαιωθείτε ότι ο φάκελος υπάρχει και η διαδικασία Java έχει δικαίωμα εγγραφής.

### Βήμα 2: Δημιουργία νέας παρουσίας έργου
Η κλάση `Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα μοναδικό αρχείο Project στη μνήμη. Η δημιουργία της παράγει ένα κενό έργο έτοιμο για διαμόρφωση.

### Βήμα 3: Ορισμός ιδιοτήτων νομίσματος
Εδώ διαμορφώνετε τον κωδικό νομίσματος, τον αριθμό δεκαδικών ψηφίων, το ίδιο το σύμβολο και τη θέση του συμβόλου.  

- **Κωδικός νομίσματος** – ένας τριψήφιος κωδικός ISO 4217 όπως `AUD` ή `USD`.  
- **Δεκαδικά ψηφία** – συνήθως 2 για τα περισσότερα νομίσματα.  
- **Σύμβολο νομίσματος** – ο χαρακτήρας ή η συμβολοσειρά που εμφανίζεται με τα ποσά, π.χ., `$` ή `€`.  
- **Θέση συμβόλου** – `CurrencySymbolPositionType.Before` τοποθετεί το σύμβολο πριν από τον αριθμό· `After` το τοποθετεί μετά.  

Αυτές οι ρυθμίσεις επηρεάζουν κάθε πεδίο σχετικό με κόστος (τιμές πόρων, προϋπολογισμούς εργασιών κ.λπ.) στο έργο.

> **Pro tip:** Εάν χρειάζεται να αλλάξετε το νόμισμα για ένα υπάρχον αρχείο, φορτώστε το με `new Project("file.mpp")` πριν εφαρμόσετε τις παραπάνω ρυθμίσεις.

### Βήμα 4: Αποθήκευση του ενημερωμένου έργου
Γράψτε το έργο πίσω στο δίσκο χρησιμοποιώντας τη μορφή που επιθυμείτε. Η μορφή XML είναι αναγνώσιμη από άνθρωπο, ενώ το `SaveFileFormat.MPP` διατηρεί πλήρη συμβατότητα με το Microsoft Project.

### Βήμα 5: Επιβεβαίωση επιτυχίας
Εκτυπώστε ένα σύντομο μήνυμα ή καταγράψτε μια εγγραφή ώστε να γνωρίζετε ότι η λειτουργία ολοκληρώθηκε χωρίς σφάλματα. Αυτό είναι ιδιαίτερα χρήσιμο σε αυτοματοποιημένες αλυσίδες.

## Συχνά προβλήματα & λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **`NullPointerException` on `project.save`** | `dataDir` δεν είναι έγκυρη διαδρομή ή δεν έχει δικαιώματα εγγραφής. | Βεβαιωθείτε ότι ο φάκελος υπάρχει και η διαδικασία Java έχει δικαιώματα εγγραφής. |
| **Currency symbol not showing** | Η θέση του συμβόλου έχει οριστεί λανθασμένα για την περιοχή σας. | Χρησιμοποιήστε `CurrencySymbolPositionType.Before` εάν το σύμβολο πρέπει να προηγείται του ποσού. |
| **Project file does not open in MS Project** | Αποθήκευση σε παλαιότερη μορφή με ασυμβίβαστες ρυθμίσεις. | Αποθηκεύστε χρησιμοποιώντας `SaveFileFormat.MPP` για πλήρη συμβατότητα με τις πρόσφατες εκδόσεις του MS Project. |

## Συχνές ερωτήσεις

**Q:** Μπορώ να ορίσω πολλαπλά νομίσματα σε ένα μόνο έργο χρησιμοποιώντας Aspose.Tasks;  
**A:** Ναι, μπορείτε να αναθέσετε διαφορετικές ρυθμίσεις νομίσματος σε μεμονωμένους πόρους ή εργασίες τροποποιώντας τα αντίστοιχα πεδία κόστους μετά τον ορισμό του νομίσματος επιπέδου έργου.

**Q:** Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;  
**A:** Απόλυτα. Η βιβλιοθήκη υποστηρίζει αρχεία MPP από το Project 2000 έως τις πιο πρόσφατες εκδόσεις, καθώς και XML και άλλες μορφές ανταλλαγής.

**Q:** Παρέχει το Aspose.Tasks υποστήριξη για προσαρμοσμένες μορφές νομίσματος;  
**A:** Ναι, μπορείτε να ορίσετε προσαρμοσμένα σύμβολα, δεκαδικά ψηφία και θέση για να καλύψετε οποιαδήποτε περιφερειακή απαίτηση, και αυτές οι ρυθμίσεις αποθηκεύονται στο αρχείο.

**Q:** Μπορώ να ενσωματώσω το Aspose.Tasks με άλλα Java frameworks;  
**A:** Φυσικά. Το API είναι καθαρά Java, επομένως λειτουργεί άψογα με Spring, Hibernate, Maven, Gradle και άλλα οικοσυστήματα.

**Q:** Πού μπορώ να βρω επιπλέον βοήθεια ή παραδείγματα;  
**A:** Επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για βοήθεια από την κοινότητα ή συμβουλευτείτε την επίσημη τεκμηρίωση για λεπτομερείς αναφορές API.

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να αλλάξετε το σύμβολο νομίσματος** σε έργα Aspose.Tasks χρησιμοποιώντας Java, πώς να ορίσετε τον κωδικό νομίσματος, να προσαρμόσετε τα δεκαδικά ψηφία και να εφαρμόσετε ένα προσαρμοσμένο σύμβολο. Αυτές οι δυνατότητες σας επιτρέπουν να δημιουργείτε αναφορές κόστους προσαρμοσμένες στην περιοχή, να ευθυγραμμίζετε τους προϋπολογισμούς έργου με τα λογιστικά πρότυπα της περιοχής και να διατηρείτε τα αρχεία Microsoft Project συνεπή σε παγκόσμιες ομάδες.

---

**Τελευταία ενημέρωση:** 2026-09-09  
**Δοκιμή με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Σχετικές οδηγίες

- [ιδιότητες έργου java – Εξαγωγή συμβόλου νομίσματος από MPP χρησιμοποιώντας Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Ανάγνωση ιδιοτήτων νομίσματος Java με Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Διαχείριση κωδικών νομισμάτων Java με Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}