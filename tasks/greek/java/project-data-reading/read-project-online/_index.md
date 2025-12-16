---
date: 2025-12-15
description: Μάθετε πώς να διαβάζετε δεδομένα του MS Project Online χρησιμοποιώντας
  το Aspose Tasks Java. Αυτός ο οδηγός δείχνει πώς να ανακτήσετε τη λίστα έργων, να
  εμφανίσετε τα έργα του SharePoint και να λάβετε τον αριθμό των πόρων.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks Java - Απρόσκοπτη ανάγνωση δεδομένων MS Project Online'
url: /el/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Εύκολη Ανάγνωση Δεδομένων MS Project Online

## Εισαγωγή
Στον χώρο της διαχείρισης έργων, η αποδοτική διαχείριση των δεδομένων Microsoft Project Online είναι κρίσιμη για ομαλές λειτουργίες. **aspose tasks java** παρέχει ένα ισχυρό, εύχρηστο API που σας επιτρέπει να διαβάζετε δεδομένα Project Online χωρίς να ασχολείστε με χαμηλού επιπέδου κλήσεις HTTP. Σε αυτό το tutorial θα δούμε πώς να ανακτήσετε μια λίστα έργων, να απαριθμήσετε τα έργα SharePoint και να λάβετε τον αριθμό πόρων από κάθε έργο — όλα με λίγες μόνο γραμμές κώδικα Java.

## Γρήγορες Απαντήσεις
- **Τι κάνει το aspose tasks java;** Διαβάζει και επεξεργάζεται αρχεία Microsoft Project και δεδομένα Project Online προγραμματιστικά.  
- **Χρειάζεται άδεια για δοκιμή;** Διατίθεται δωρεάν δοκιμή· απαιτείται άδεια για παραγωγική χρήση.  
- **Ποια διαπιστευτήρια απαιτούνται;** Domain SharePoint, όνομα χρήστη και κωδικός πρόσβασης (ή token Azure AD).  
- **Μπορώ να απαριθμήσω έργα SharePoint;** Ναι – χρησιμοποιήστε `ProjectServerManager.getProjectList()` για να τα ανακτήσετε.  
- **Πώς λαμβάνω τον αριθμό πόρων;** Φορτώστε κάθε αντικείμενο `Project` και καλέστε `project.getResources().size()`.

## Τι είναι το aspose tasks java;
**aspose tasks java** είναι μια βιβλιοθήκη προσανατολισμένη στους προγραμματιστές που αφαιρεί τις πολυπλοκότητες των μορφότυπων αρχείων Microsoft Project και των REST API του Project Server. Σας επιτρέπει να διαβάζετε, δημιουργείτε και τροποποιείτε δεδομένα έργων απευθείας από εφαρμογές Java, καθιστώντας την ενσωμάτωση με υπάρχοντα επιχειρησιακά συστήματα απλή.

## Γιατί να χρησιμοποιήσετε το aspose tasks java για την ανάγνωση του MS Project Online;
- **Χωρίς χειροκίνητη διαχείριση HTTP** – η βιβλιοθήκη αναλαμβάνει τον έλεγχο ταυτότητας και τις κλήσεις REST.  
- **Ισχυρή ασφάλεια τύπων** – εργάζεστε με `Project`, `ProjectInfo` και άλλα POJO αντί για ακατέργαστο JSON.  
- **Cross‑platform** – λειτουργεί σε οποιοδήποτε περιβάλλον συμβατό με JVM.  
- **Πλούσιο σύνολο λειτουργιών** – εκτός από την ανάγνωση, μπορείτε επίσης να ενημερώσετε εργασίες, πόρους και χρονοδιαγράμματα.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java library** – κατεβάστε το από [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – με δικαιώματα ανάγνωσης έργων.  
4. **SharePoint domain address** – όπου βρίσκεται η εγκατάσταση Project Online.  
5. **Username and password** – ή κατάλληλα διαπιστευτήρια Azure AD για έλεγχο ταυτότητας.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις Aspose.Tasks που θα χρησιμοποιήσουμε σε όλο το tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Βήμα 1: Ορισμός Domain SharePoint, Όνομα Χρήστη και Κωδικός Πρόσβασης
Ορίστε τα στοιχεία σύνδεσης για το περιβάλλον Project Online. Αντικαταστήστε τις τιμές placeholder με τα δικά σας διαπιστευτήρια.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Βήμα 2: Έλεγχος Ταυτότητας με Διαπιστευτήρια Project Server
Δημιουργήστε ένα αντικείμενο `ProjectServerCredentials` και αρχικοποιήστε έναν `ProjectServerManager`. Αυτός ο διαχειριστής θα χειρίζεται όλες τις επόμενες κλήσεις στο Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Βήμα 3: Ανάκτηση Λίστας Έργων και Εμφάνιση Πληροφοριών
Χρησιμοποιήστε τον διαχειριστή για **ανάκτηση λίστας έργων** (list SharePoint projects) και εκτυπώστε βασικές λεπτομέρειες όπως όνομα, ημερομηνία δημιουργίας και ημερομηνία τελευταίας αποθήκευσης.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Βήμα 4: Φόρτωση Μεμονωμένων Έργων και Εμφάνιση Αριθμού Πόρων
Για κάθε έργο που επιστράφηκε στο προηγούμενο βήμα, φορτώστε το πλήρες αντικείμενο `Project` και εμφανίστε τον **αριθμό πόρων**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Κοινά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Αποτυχία Επαλήθευσης** | Λάθος domain, όνομα χρήστη ή κωδικός πρόσβασης. | Επαληθεύστε τα διαπιστευτήρια και βεβαιωθείτε ότι ο λογαριασμός έχει δικαιώματα ανάγνωσης στο Project Online. |
| **SSLHandshakeException** | Η Java runtime δεν διαθέτει την απαιτούμενη έκδοση TLS. | Ενημερώστε το JDK στην τελευταία έκδοση ή ενεργοποιήστε TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | Ο λογαριασμός δεν έχει πρόσβαση σε κανένα έργο. | Ελέγξτε τα δικαιώματα στο Project Online ή χρησιμοποιήστε λογαριασμό διαχειριστή. |
| **Large projects cause OutOfMemoryError** | Η φόρτωση πολλών έργων ταυτόχρονα καταναλώνει μνήμη. | Φορτώστε τα έργα ένα προς ένα και απελευθερώστε τις αναφορές μετά τη χρήση. |

## Συχνές Ερωτήσεις
### Μ: Μπορώ να χρησιμοποιήσω το aspose tasks java για την τροποποίηση δεδομένων MS Project Online;
Α: Ναι, το Aspose.Tasks παρέχει εκτενείς δυνατότητες τόσο για ανάγνωση **όσο και** για τροποποίηση των δεδομένων Project Online προγραμματιστικά.

### Μ: Υποστηρίζει το Aspose.Tasks άλλα μορφότυπα αρχείων διαχείρισης έργων;
Α: Απόλυτα. Υποστηρίζει MPP, XML, Primavera και πολλά άλλα, εξασφαλίζοντας συμβατότητα σε διαφορετικά οικοσυστήματα έργων.

### Μ: Υπάρχει δωρεάν δοκιμή για το Aspose.Tasks for Java;
Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή από [here](https://releases.aspose.com/) για να εξερευνήσετε τις δυνατότητες και τις λειτουργίες του Aspose.Tasks.

### Μ: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks for Java;
Α: Μπορείτε να ανατρέξετε στην αναλυτική τεκμηρίωση [here](https://reference.aspose.com/tasks/java/) για πλήρη καθοδήγηση σχετικά με τη χρήση του Aspose.Tasks στα Java projects σας.

### Μ: Ποιες επιλογές υποστήριξης είναι διαθέσιμες για το Aspose.Tasks for Java;
Α: Εάν αντιμετωπίσετε προβλήματα ή έχετε ερωτήσεις, μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Τελευταία Ενημέρωση:** 2025-12-15  
**Δοκιμή με:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}