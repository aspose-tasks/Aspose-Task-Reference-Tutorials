---
date: 2025-12-25
description: Εξερευνήστε αυτό το σεμινάριο Aspose Tasks Java για να μάθετε πώς να
  προσδιορίσετε την έκδοση του έργου σε αρχεία MS Project. Οδηγός βήμα‑βήμα με παραδείγματα
  κώδικα.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Εκμάθηση Aspose Tasks Java: Προσδιορισμός Έκδοσης MS Project'
url: /el/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java Tutorial: Προσδιορισμός Έκδοσης MS Project

## Introduction
Σε αυτό το **aspose tasks java tutorial** θα μάθετε πώς να εντοπίζετε προγραμματιστικά την έκδοση ενός αρχείου Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Η γνώση της έκδοσης του αρχείου βοηθά στην αντιμετώπιση προβλημάτων συμβατότητας, στην επιβολή πολιτικών μετεγκατάστασης ή απλώς στην καταγραφή της έκδοσης του Project που δημιούργησε το αρχείο. Θα περάσουμε από κάθε βήμα — από τη ρύθμιση του περιβάλλοντος μέχρι την εκτύπωση της έκδοσης και της ημερομηνίας τελευταίας αποθήκευσης — ώστε να μπορείτε να ενσωματώσετε αυτόν τον έλεγχο σε οποιαδήποτε εφαρμογή Java με σιγουριά.

## Quick Answers
- **Τι καλύπτει αυτό το tutorial;** Προσδιορισμός της έκδοσης αρχείου MS Project με Aspose.Tasks για Java.  
- **Χρειάζεται να έχω εγκατεστημένο το Microsoft Project;** Όχι, το Aspose.Tasks λειτουργεί ανεξάρτητα.  
- **Ποιες μορφές αρχείων υποστηρίζονται;** Αρχεία Project βασισμένα σε XML (MPP, XML κ.λπ.).  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 5‑10 λεπτά για έναν βασικό έλεγχο.  
- **Απαιτείται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται άδεια για παραγωγή.

## What is Aspose Tasks Java Tutorial?
Ένα **aspose tasks java tutorial** παρέχει πρακτική καθοδήγηση για τη χρήση του API Aspose.Tasks σε έργα Java. Δείχνει πώς να διαβάζετε, να τροποποιείτε και να αναλύετε δεδομένα Microsoft Project χωρίς την ανάγκη του ίδιου του Microsoft Project.

## Why use Aspose.Tasks to determine project version?
- **Χωρίς εξάρτηση από το Microsoft Project** – ιδανικό για αυτοματισμούς στο διακομιστή.  
- **Ακριβή μεταδεδομένα έκδοσης** – ανάκτηση των πεδίων SAVE_VERSION και LAST_SAVED.  
- **Διαπλατφορμική** – λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java.  
- **Υψηλή απόδοση** – ελαφρύ parsing κατάλληλο για επεξεργασία παρτίδων.

## Prerequisites
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Java Development Kit (JDK)** – οποιοδήποτε πρόσφατο JDK (8 ή νεότερο).  
2. **Aspose.Tasks for Java JAR** – κατεβάστε το από την [website](https://releases.aspose.com/tasks/java/) και προσθέστε το στο classpath του έργου σας.  
3. **MS Project file** – ένα αρχείο Project βασισμένο σε XML (π.χ., `input.xml`) που θέλετε να εξετάσετε.  

> **Pro tip:** Κρατήστε το αρχείο Project σε έναν αφιερωμένο φάκελο `data` για να απλοποιήσετε τη διαχείριση διαδρομών.

## Import Packages
Πρώτα, εισάγετε τις βασικές κλάσεις του Aspose.Tasks:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Set Up the Project Directory
Ορίστε το φάκελο που περιέχει το αρχείο Project.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη ή σχετική διαδρομή όπου βρίσκεται το `input.xml`.

## Step 2: Load the Project
Δημιουργήστε ένα αντικείμενο `Project` φορτώνοντας το αρχείο XML.

```java
Project project = new Project(dataDir + "input.xml");
```

Αν το αρχείο σας έχει διαφορετικό όνομα, προσαρμόστε το `"input.xml"` αναλόγως.

## Step 3: How to Determine Project Version
Ανακτήστε τις πληροφορίες έκδοσης και την ημερομηνία τελευταίας αποθήκευσης.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Η ιδιότητα `Prj.SAVE_VERSION` υποδεικνύει την έκδοση του Microsoft Project που χρησιμοποιήθηκε για την αποθήκευση του αρχείου (π.χ., 12 για Project 2010). Η `Prj.LAST_SAVED` επιστρέφει την ημερομηνία/ώρα της πιο πρόσφατης αποθήκευσης.

## Step 4: Display Result
Δείξτε ότι ο έλεγχος έκδοσης ολοκληρώθηκε επιτυχώς.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | File not found or path incorrect | Verify `dataDir` and file name; use absolute path for testing. |
| Unexpected version number (e.g., 0) | Loading a non‑Project XML file | Ensure the file is a valid Microsoft Project file (MPP/XML). |
| License exception | Using the trial without a valid license in production | Apply your Aspose.Tasks license (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

### Q: Can I use Aspose.Tasks with other programming languages?
A: Yes, Aspose.Tasks supports multiple languages including .NET, Java, and C++.

### Q: Is Aspose.Tasks suitable for large‑scale projects?
A: Absolutely, Aspose.Tasks is designed to handle projects of any size with ease.

### Q: Can I customize project data using Aspose.Tasks?
A: Yes, you can manipulate project data, modify tasks, resources, and much more using Aspose.Tasks.

### Q: Does Aspose.Tasks require Microsoft Project installation?
A: No, Aspose.Tasks works independently and does not require Microsoft Project to be installed.

### Q: Is technical support available for Aspose.Tasks?
A: Yes, you can get technical support from the Aspose.Tasks forum at [here](https://forum.aspose.com/c/tasks/15).

### Additional Q&A

**Q: How do I retrieve other project properties (e.g., author, company)?**  
A: Use `project.get(Prj.AUTHOR)` or `project.get(Prj.COMPANY)` similarly to the version example.

**Q: Can I check the version of an MPP file (binary format)?**  
A: Yes, Aspose.Tasks can load `.mpp` files directly; the same `Prj.SAVE_VERSION` property works.

**Q: Is there a way to programmatically upgrade an older project file to a newer version?**  
A: Load the older file, then save it using `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks writes it in the latest format by default.

## Conclusion
Έχετε ολοκληρώσει τώρα ένα σύντομο **aspose tasks java tutorial** που δείχνει **πώς να προσδιορίσετε την έκδοση του project** αρχείων MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ενσωματώστε αυτό το απόσπασμα σε μεγαλύτερα ροές αυτοματισμού, εργαλεία αναφοράς ή βοηθήματα μετεγκατάστασης ώστε να γνωρίζετε πάντα την ακριβή έκδοση του Project με την οποία εργάζεστε.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}