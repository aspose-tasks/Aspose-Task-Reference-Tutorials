---
date: 2026-02-18
description: Μάθετε πώς να διαβάζετε δεδομένα του MS Project Online χρησιμοποιώντας
  το Aspose.Tasks Java. Αυτός ο οδηγός δείχνει πώς να ανακτήσετε τη λίστα έργων, τη
  λίστα έργων SharePoint και να λάβετε τον αριθμό πόρων.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Απρόσκοπτη ανάγνωση δεδομένων MS Project Online'
url: /el/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Απρόσκοπτη Ανάγνωση Δεδομένων MS Project Online

## Introduction
Στον χώρο της διαχείρισης έργων, η αποτελεσματική διαχείριση των δεδομένων του Microsoft Project Online είναι κρίσιμη για ομαλές λειτουργίες. **aspose tasks java** παρέχει ένα ισχυρό, εύχρηστο API που σας επιτρέπει να διαβάζετε δεδομένα Project Online χωρίς να ασχολείστε με χαμηλού επιπέδου κλήσεις HTTP. Σε αυτό το tutorial θα δούμε πώς να ανακτήσετε μια λίστα έργων, **να εμφανίσετε τα έργα SharePoint**, και **να λάβετε τον αριθμό πόρων** από κάθε έργο—όλα με λίγες γραμμές κώδικα Java.

## Quick Answers
- **Τι κάνει το aspose tasks java;** Διαβάζει και χειρίζεται προγραμματιστικά αρχεία Microsoft Project και δεδομένα Project Online.  
- **Χρειάζομαι άδεια για δοκιμή;** Διατίθεται δωρεάν δοκιμή· απαιτείται άδεια για χρήση σε παραγωγή.  
- **Ποια διαπιστευτήρια απαιτούνται;** Το domain του SharePoint, όνομα χρήστη και κωδικός (ή token Azure AD).  
- **Μπορώ να εμφανίσω τα έργα SharePoint;** Ναι – χρησιμοποιήστε `ProjectServerManager.getProjectList()` για να τα ανακτήσετε.  
- **Πώς λαμβάνω τον αριθμό πόρων;** Φορτώστε κάθε αντικείμενο `Project` και καλέστε `project.getResources().size()`.

## What is aspose tasks java?
**aspose tasks java** είναι μια βιβλιοθήκη προσανατολισμένη στους προγραμματιστές που αφαιρεί τις πολυπλοκότητες των μορφών αρχείων του Microsoft Project και του Project Server REST API. Σας επιτρέπει να διαβάζετε, δημιουργείτε και τροποποιείτε δεδομένα έργων απευθείας από εφαρμογές Java, καθιστώντας την ενσωμάτωση με υπάρχοντα συστήματα επιχείρησης απλή.

## Why use aspose tasks java for reading MS Project Online?
- **Καμία χειροκίνητη διαχείριση HTTP** – η βιβλιοθήκη αναλαμβάνει τον έλεγχο ταυτότητας και τις κλήσεις REST.  
- **Ισχυρή ασφάλεια τύπων** – εργασία με `Project`, `ProjectInfo` και άλλα POJO αντί για ακατέργαστο JSON.  
- **Διαπλατφορμική** – εκτελείται σε οποιοδήποτε περιβάλλον συμβατό με JVM.  
- **Πλούσιο σύνολο λειτουργιών** – εκτός από ανάγνωση, μπορείτε επίσης να ενημερώσετε εργασίες, πόρους και χρονοδιαγράμματα.  
- **Εσωτερικά αξιοποιεί το Project Server REST API**, έτσι έχετε ένα σταθερό, υποστηριζόμενο επίπεδο επικοινωνίας.

## Prerequisites
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java library** – κατεβάστε το από [εδώ](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – με δικαιώματα ανάγνωσης έργων.  
4. **SharePoint domain address** – όπου βρίσκεται η εγκατάσταση του Project Online.  
5. **Username and password** – ή τα κατάλληλα διαπιστευτήρια Azure AD για έλεγχο ταυτότητας.

## Import Packages
Πρώτα, εισάγετε τις απαραίτητες κλάσεις Aspose.Tasks που θα χρησιμοποιήσουμε σε όλο το tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Step 1: Set SharePoint Domain, Username, and Password
Ορίστε τις λεπτομέρειες σύνδεσης για το περιβάλλον Project Online. Αντικαταστήστε τις τιμές placeholder με τα δικά σας διαπιστευτήρια.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Step 2: Authenticate with Project Server Credentials
Δημιουργήστε ένα αντικείμενο `ProjectServerCredentials` και αρχικοποιήστε ένα `ProjectServerManager`. Αυτός ο διαχειριστής θα διαχειρίζεται όλες τις επόμενες κλήσεις στο Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Step 3: Retrieve Project List and Display Information
Χρησιμοποιήστε τον διαχειριστή για **να ανακτήσετε τη λίστα έργων** (δηλαδή, να εμφανίσετε τα έργα SharePoint) και εκτυπώστε βασικές λεπτομέρειες όπως όνομα, ημερομηνία δημιουργίας και ημερομηνία τελευταίας αποθήκευσης.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Step 4: Load Individual Projects and Output Resource Count
Για κάθε έργο που επιστράφηκε στο προηγούμενο βήμα, φορτώστε το πλήρες αντικείμενο `Project`—αυτή η κλήση **φορτώνει τα δεδομένα του έργου** για το συγκεκριμένο ID—και εμφανίστε τον **αριθμό πόρων**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Common Issues and Solutions
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Αποτυχία ελέγχου ταυτότητας** | Λανθασμένο domain, όνομα χρήστη ή κωδικός. | Επαληθεύστε τα διαπιστευτήρια και βεβαιωθείτε ότι ο λογαριασμός έχει δικαιώματα ανάγνωσης στο Project Online. |
| **SSLHandshakeException** | Το Java runtime δεν διαθέτει την απαιτούμενη έκδοση TLS. | Ενημερώστε το JDK στην τελευταία έκδοση ή ενεργοποιήστε TLS 1.2+. |
| `reader.getProjectList()` επιστρέφει κενό | Ο λογαριασμός δεν έχει πρόσβαση σε κανένα έργο. | Ελέγξτε τα δικαιώματα στο Project Online ή χρησιμοποιήστε λογαριασμό διαχειριστή. |
| Μεγάλα έργα προκαλούν OutOfMemoryError | Η φόρτωση πολλών έργων ταυτόχρονα καταναλώνει μνήμη. | Φορτώστε τα έργα ένα προς ένα και απελευθερώστε τις αναφορές μετά τη χρήση. |

## Frequently Asked Questions
**Q:** Can I use aspose tasks java to modify MS Project Online data?  
**A:** Yes, Aspose.Tasks provides extensive capabilities for both reading **and** modifying Project Online data programmatically.

**Q:** Does Aspose.Tasks support other project management file formats?  
**A:** Absolutely. It supports MPP, XML, Primavera, and many more, ensuring compatibility across diverse project ecosystems.

**Q:** Is there a free trial available for Aspose.Tasks for Java?  
**A:** Yes, you can avail of a free trial from [εδώ](https://releases.aspose.com/) to explore the features and functionalities of Aspose.Tasks.

**Q:** Where can I find comprehensive documentation for Aspose.Tasks for Java?  
**A:** You can refer to the detailed documentation [εδώ](https://reference.aspose.com/tasks/java/) for comprehensive guidance on utilizing Aspose.Tasks in your Java projects.

**Q:** What support options are available for Aspose.Tasks for Java?  
**A:** If you encounter any issues or have queries, you can seek assistance from the Aspose.Tasks community forum [εδώ](https://forum.aspose.com/c/tasks/15).

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}