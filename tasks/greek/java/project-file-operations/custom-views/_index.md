---
date: 2026-05-26
description: Μάθετε πώς να προσθέσετε προβολή σε έργο χρησιμοποιώντας Aspose.Tasks
  για Java, να αποθηκεύσετε προσαρμοσμένη προβολή και να ορίσετε ιδιότητες προβολής
  για ισχυρή αναφορά MS Project.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Προσαρμοσμένες προβολές στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να προσθέσετε προβολή σε έργο με Aspose.Tasks
url: /el/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Προβολή σε Έργο με το Aspose.Tasks

## Εισαγωγή
Αν ψάχνετε για **πώς να προσθέσετε προβολή σε έργο** ώστε οι αναφορές σας να ταιριάζουν ακριβώς με τις ανάγκες των ενδιαφερόμενων, βρίσκεστε στο σωστό μέρος. Η προσαρμογή των προβολών του MS Project σας επιτρέπει να εμφανίζετε τα πιο σχετικοί δεδομένα, να αφαιρείτε το περιττό και να επιταχύνετε τη λήψη αποφάσεων. **Aspose.Tasks for Java** παρέχει ένα ισχυρό, τύπο‑ασφαλές API που σας επιτρέπει να δημιουργείτε, να διαμορφώνετε και να διατηρείτε προσαρμοσμένες προβολές απευθείας μέσα σε αρχείο MPP. Σε αυτόν τον οδηγό θα περάσουμε από κάθε βήμα — από την προετοιμασία του περιβάλλοντος μέχρι την αποθήκευση της προβολής — ώστε να παραδώσετε μια επαγγελματική, επαναλήψιμη λύση.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός;** Για να προσθέσετε προβολή σε έργο και να την αποθηκεύσετε μέσα στο αρχείο MPP χρησιμοποιώντας το Aspose.Tasks for Java.  
- **Ποια κλάση δημιουργεί μια προβολή;** `GanttChartView` (ή άλλους τύπους προβολών όπως `TaskSheetView`).  
- **Πώς κάνω την προβολή να εμφανίζεται στο μενού;** Καλέστε `view.setShowInMenu(true)` πριν από την αποθήκευση.  
- **Πώς μπορώ να αποθηκεύσω την προβολή με το έργο;** Χρησιμοποιήστε `MPPSaveOptions` με `setWriteViewData(true)`.  
- **Χρειάζομαι άδεια;** Ναι – απαιτείται έγκυρη άδεια Aspose.Tasks για παραγωγικές αναπτύξεις.

## Τι σημαίνει το “add view to project”;
*Η προσθήκη μιας προβολής σε ένα έργο* σημαίνει τη δημιουργία μιας νέας οπτικής αναπαράστασης (π.χ., διάγραμμα Gantt, φύλλο εργασιών) και την ενσωμάτωση του ορισμού της μέσα στο αρχείο MPP ώστε το Microsoft Project να μπορεί να το εμφανίσει αργότερα. Αυτή η λειτουργία είναι πλήρως προγραμματιστική με το Aspose.Tasks, εξαλείφοντας τα χειροκίνητα βήματα του UI.

## Γιατί να Χρησιμοποιήσετε Προσαρμοσμένες Προβολές;
Το Aspose.Tasks υποστηρίζει **πάνω από 50 ιδιότητες σχετικές με προβολές** και μπορεί να διαχειριστεί έργα με **εκατοντάδες χιλιάδες εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Ορίζοντας μια προβολή μία φορά και διατηρώντας την, εξασφαλίζετε συνεπή αναφορά σε όλα τα μέλη της ομάδας και μειώνετε τον κίνδυνο σφαλμάτων χειροκίνητης ρύθμισης.

## Προαπαιτούμενα
- **Java Development Kit** (JDK 8 ή νεότερο) εγκατεστημένο και ρυθμισμένο στον υπολογιστή σας.  
- **Aspose.Tasks for Java** βιβλιοθήκη – κατεβάστε την από [εδώ](https://releases.aspose.com/tasks/java/).  
- Ένα έγκυρο αρχείο άδειας **Aspose.Tasks** για παραγωγική χρήση (η δωρεάν δοκιμή λειτουργεί για αξιολόγηση).

## Εισαγωγή Πακέτων
Η `GanttChartView`, η `MPPSaveOptions` και οι σχετικές κλάσεις βρίσκονται στο namespace `com.aspose.tasks`. Εισάγετέ τες στην αρχή του αρχείου πηγαίου κώδικα:

`GanttChartView` αντιπροσωπεύει έναν ορισμό προβολής διαγράμματος Gantt.  
`MPPSaveOptions` ελέγχει πώς αποθηκεύεται ένα έργο, συμπεριλαμβανομένων των δεδομένων προβολής.  
`Project` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο MS Project.  
`View` είναι η βασική κλάση για όλους τους τύπους προβολών.  

```text
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
```

## Βήμα 1: Ρύθμιση Έργου
Δημιουργήστε ένα νέο αντικείμενο `Project` ή φορτώστε ένα υπάρχον αρχείο. Αυτό το αντικείμενο περιέχει όλα τα δεδομένα του έργου, συμπεριλαμβανομένων των εργασιών, των πόρων και των προβολών. Η `Prj` παρέχει σταθερά κλειδιά για ιδιότητες του έργου όπως το όνομα του έργου.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Βήμα 2: Δημιουργία Προβολής
`GanttChartView` είναι η αναπαράσταση του Aspose.Tasks για ένα κλασικό διάγραμμα Gantt. Σας επιτρέπει να ελέγχετε στήλες, στυλ ράβδων, χρονολογίες κ.ά.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Βήμα 3: Προσαρμογή Ιδιοτήτων Προβολής *(set view properties)*
Εδώ μπορείτε να ρυθμίσετε λεπτομερώς την εμφάνιση της προβολής: ορίστε την πρώτη ορατή στήλη, καθορίστε χρώματα ράβδων και προσαρμόστε την λεπτομέρεια της χρονολογίας. `setShowInMenu(boolean)` καθορίζει αν η προβολή εμφανίζεται στο μενού του MS Project. `setHighlightFilter(boolean)` υποδεικνύει αν το φίλτρο είναι επισημασμένο για την προβολή.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Πώς να Εμφανίσετε το Μενού Προβολής
Καλώντας `view.setShowInMenu(true)` εξασφαλίζει ότι η νεοδημιουργημένη προβολή εμφανίζεται στο μενού **View** του MS Project, δίνοντας στους τελικούς χρήστες άμεση πρόσβαση χωρίς επιπλέον ρύθμιση.

## Βήμα 4: Ρύθμιση Ρυθμίσεων Προβολής
Προηγμένες ρυθμίσεις όπως διάταξη σελίδας, επιλογές εκτύπωσης και πλάτη στηλών διαμορφώνονται σε αυτό το βήμα. Η σωστή ρύθμιση εγγυάται ότι οι εκτυπωμένες αναφορές ταιριάζουν με την προβολή στην οθόνη.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Βήμα 5: Προσθήκη Προβολής στο Έργο *(add custom view java)*
Αφού διαμορφώσετε την προβολή, προσθέστε την στη συλλογή `Views` του έργου. Η `getViews()` επιστρέφει τη συλλογή των προβολών στο έργο. Αυτό το βήμα στην πραγματικότητα **προσθέτει προβολή σε έργο** ώστε να γίνει μέρος της εσωτερικής δομής του αρχείου.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Βήμα 6: Αποθήκευση Έργου *(save project view)*
Κατά την αποθήκευση του έργου, πρέπει να ενημερώσετε το Aspose.Tasks να γράψει τα δεδομένα προβολής. Η κλάση `MPPSaveOptions` ελέγχει αυτή τη συμπεριφορά. Η `setWriteViewData(boolean)` λέει στον αποθηκευτή να ενσωματώσει τους ορισμούς προβολής.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Γιατί η Αποθήκευση της Προβολής του Έργου Είναι Σημαντική
Η ρύθμιση `options.setWriteViewData(true)` υποδεικνύει στο Aspose.Tasks να ενσωματώσει τον ορισμό της προσαρμοσμένης προβολής μέσα στο αρχείο MPP. Χωρίς αυτή τη σημαία, η προβολή θα υπήρχε μόνο στη μνήμη και θα εξαφανιζόταν μετά το κλείσιμο του αρχείου.

## Βήμα 7: Έλεγχος Ιδιοτήτων Προβολής
Μετά την αποθήκευση, μπορείτε να φορτώσετε ξανά το έργο και να επαληθεύσετε ότι η προβολή εμφανίζεται σωστά στη διεπαφή χρήστη και ότι όλες οι ιδιότητες (στήλες, στυλ ράβδων κ.ά.) διατηρούνται.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Κοινές Περιπτώσεις Χρήσης
- **Αναφορά σε Ενδιαφερόμενους:** Εμφάνιση μόνο των ορόσημων και των εργασιών κρίσιμης διαδρομής στη ανώτερη διοίκηση.  
- **Κατανομή Πόρων:** Εμφάνιση πόρων δίπλα-δίπλα με τις ανατεθειμένες εργασίες για προγραμματισμό χωρητικότητας.  
- **Στιγμιότυπα Έτοιμα για Εκτύπωση:** Διαμορφώστε το μέγεθος σελίδας, τον προσανατολισμό και την ορατότητα των στηλών για τη δημιουργία καθαρών PDF για offline ανασκόπηση.

## Συμβουλές Επίλυσης Προβλημάτων
- **Η Προβολή Δεν Εμφανίζεται στο Μενού:** Βεβαιωθείτε ότι το `view.setShowInMenu(true)` καλείται *πριν* από την αποθήκευση και ότι το `MPPSaveOptions.setWriteViewData(true)` είναι ενεργοποιημένο.  
- **Απουσία Στηλών στην Εκτύπωση:** Επαληθεύστε ότι το `setFirstColumnsCount` ταιριάζει με τον αριθμό των στηλών που ορίσατε και ενεργοποιήστε το `setPrintFirstColumnsCountOnAllPages(true)`.  
- **Εξαιρέσεις Άδειας:** Φορτώστε το αρχείο άδειας με `License license = new License(); license.setLicense("Aspose.Tasks.lic");` πριν δημιουργήσετε οποιαδήποτε αντικείμενα `Project`.

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσαρμόσω τις προβολές πέρα από τα διαγράμματα Gantt;**  
A: Ναι – το Aspose.Tasks σας επιτρέπει να δημιουργήσετε προσαρμοσμένα φύλλα εργασιών, φύλλα πόρων και ακόμη προσαρμοσμένους πίνακες, δίνοντάς σας πλήρη έλεγχο σε κάθε οπτικό στοιχείο.

**Q: Είναι το Aspose.Tasks for Java κατάλληλο για μεγάλης κλίμακας έργα;**  
A: Απόλυτα. Η βιβλιοθήκη επεξεργάζεται έργα με **500.000+ εργασίες** χρησιμοποιώντας ένα streaming API που διατηρεί τη χρήση μνήμης κάτω από 200 MB.

**Q: Υποστηρίζει το Aspose.Tasks for Java την εξαγωγή προβολών σε διαφορετικές μορφές;**  
A: Ναι – μπορείτε να εξάγετε μια προβολή σε PDF, XLSX, HTML και σε πολλές μορφές εικόνας απευθείας από το API.

**Q: Μπορώ να αυτοματοποιήσω τη δημιουργία προσαρμοσμένων προβολών χρησιμοποιώντας το Aspose.Tasks for Java;**  
A: Σίγουρα. Το API είναι πλήρως scriptable, επιτρέποντάς σας να δημιουργείτε, να τροποποιείτε και να διατηρείτε προβολές σε batch jobs ή pipelines CI.

**Q: Υπάρχει φόρουμ κοινότητας για υποστήριξη του Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να λάβετε βοήθεια από άλλους προγραμματιστές και το προσωπικό της Aspose στο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Αρχείο MPP – Δημιουργία & Αποθήκευση Κεντρικού Έργου σε Μορφή MPP με το Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Ορισμός Καταλόγου Δεδομένων για Προβολή Διαγράμματος Gantt στο Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [Φόρτωση Αρχείου MPP Java - Διαχείριση Ιδιοτήτων Έργου με το Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}