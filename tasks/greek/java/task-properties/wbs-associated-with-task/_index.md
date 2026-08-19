---
date: 2026-03-03
description: Μάθετε πώς να επανααριθμείτε το WBS στο Aspose.Tasks για Java, να διαχειρίζεστε
  τη διάσπαση εργασιών και να προσαρμόζετε τους κωδικούς WBS αποδοτικά με παραδείγματα
  βήμα‑προς‑βήμα.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να επανααριθμήσετε το WBS στο Aspose.Tasks για Java
url: /el/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να επανααριθμήσετε το WBS στο Aspose.Tasks για Java

## Εισαγωγή
Αν χρειάζεστε **how to renumber WBS** σε αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks for Java, βρίσκεστε στο σωστό μέρος. Αυτό το tutorial σας καθοδηγεί στη ανάγνωση των υφιστάμενων κωδικών WBS, στην προσαρμογή τους και στη συνέχεια στην επανααρίθμηση της ιεραρχίας ώστε το έργο σας να παραμένει οργανωμένο. Είτε καθαρίζετε ένα παλιό χρονοδιάγραμμα είτε δημιουργείτε ένα νέο από το μηδέν, η κατανόηση αυτών των βημάτων θα σας βοηθήσει να **manage work breakdown** δομές με σιγουριά.

## Γρήγορες Απαντήσεις
- **Τι κάνει η επανααρίθμηση του WBS;** Επαναϋπολογίζει την ιεραρχική αρίθμηση των εργασιών ώστε να αντικατοπτρίζει τυχόν δομικές αλλαγές.  
- **Ποια κλάση εκτελεί την επανααρίθμηση;** `Project.renumberWBSCode`.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Απαιτείται έγκυρη άδεια Aspose.Tasks για χρήση σε παραγωγή.  
- **Μπορώ να προσαρμόσω τη μορφή του WBS;** Ναι—χρησιμοποιήστε `Task.set(Tsk.WBS, "...")` για να ορίσετε οποιοδήποτε string θέλετε.  
- **Ποια είναι τα κύρια προαπαιτούμενα;** Java JDK, βιβλιοθήκη Aspose.Tasks for Java και ένα έγκυρο αρχείο έργου (.mpp).

## Τι είναι η Δομή Ανάλυσης Εργασιών (WBS);
Μια Δομή Ανάλυσης Εργασιών (WBS) είναι μια ιεραρχική αναπαράσταση των παραδοτέων και των εργασιών ενός έργου. Κάθε εργασία λαμβάνει έναν κωδικό (π.χ., 1.2.3) που αντικατοπτρίζει τη θέση της στην ιεραρχία. Η επανααρίθμηση γίνεται απαραίτητη όταν προστίθενται, αφαιρούνται ή αναδιατάσσονται εργασίες, εξασφαλίζοντας ότι οι κωδικοί παραμένουν λογικοί και εύκολα αναγνώσιμοι.

## Γιατί να διαχειρίζεστε την ανάλυση εργασιών και να προσαρμόζετε τους κωδικούς WBS;
- **Διαφάνεια:** Οι σαφείς κωδικοί WBS καθιστούν εύκολο για τα ενδιαφερόμενα μέρη να εντοπίζουν τις εργασίες.  
- **Αναφορά:** Πολλά εργαλεία αναφοράς βασίζονται σε συνεπή αρίθμηση.  
- **Ευελιξία:** Προσαρμοσμένοι κωδικοί σας επιτρέπουν να ευθυγραμμίζετε τη δομή του έργου με τις εσωτερικές προδιαγραφές.  

## Προαπαιτούμενα
Πριν βυθιστούμε στον κώδικα, βεβαιωθείτε ότι έχετε τα εξής:

- Java Development Kit (JDK) εγκατεστημένο στον υπολογιστή σας.  
- Βιβλιοθήκη Aspose.Tasks for Java προστιθέμενη στο έργο σας. Μπορείτε να τη λάβετε από [here](https://releases.aspose.com/tasks/java/).  

## Εισαγωγή Πακέτων
Βεβαιωθείτε ότι εισάγετε τα απαραίτητα πακέτα για να ξεκινήσετε το έργο σας:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Ανάγνωση Κωδικών WBS
Αρχικά, θα διαβάσουμε τους υπάρχοντες κωδικούς WBS ώστε να δείτε με τι εργάζεστε.

### Βήμα 1: Φόρτωση του Έργου
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Βήμα 2: Συλλογή Εργασιών
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Βήμα 3: Ανάλυση και Προσαρμογή
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Το παραπάνω απόσπασμα εκτυπώνει το τρέχον WBS και το επίπεδο κάθε εργασίας, και στη συνέχεια δείχνει **customize wbs codes** με την ανάθεση ενός νέου string.

## Επανααρίθμηση Κωδικών WBS Εργασιών
Τώρα ας επανααριθμήσουμε πραγματικά την ιεραρχία του WBS.

### Βήμα 1: Φόρτωση του Έργου (Παράδειγμα Επανααρίθμησης)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Βήμα 2: Επιλογή Όλων των Εργασιών
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Βήμα 3: Έξοδος Αρχικών Κωδικών WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Βήμα 4: Επανααρίθμηση Κωδικών WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Βήμα 5: Έξοδος Ενημερωμένων Κωδικών WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Ακολουθώντας αυτά τα βήματα, θα μπορείτε αποτελεσματικά **how to renumber wbs** για οποιοδήποτε σύνολο εργασιών στο αρχείο του έργου σας.

## Κοινά Προβλήματα και Λύσεις
- **Το WBS δεν αλλάζει μετά την κλήση `set`:** Βεβαιωθείτε ότι εργάζεστε με τη σωστή παρουσία εργασίας και ότι το έργο αποθηκεύεται μετά τις τροποποιήσεις.  
- `renumberWBSCode` πετάει εξαίρεση:** Επαληθεύστε ότι η λίστα των IDs ταιριάζει με τον αριθμό των εργασιών κορυφαίου επιπέδου· διαφορετικά η μέθοδος δεν μπορεί να αντιστοιχίσει σωστά τους νέους αριθμούς.  
- **Λείπουν τιμές WBS:** Ορισμένες εργασίες μπορεί να έχουν `null` WBS εάν εισήχθησαν από αρχείο που δεν ορίζει τέτοιο. Χρησιμοποιήστε εναλλακτική τιμή πριν την εκτύπωση.  

## Συχνές Ερωτήσεις

**Q: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Tasks for Java;**  
A: Η τεκμηρίωση είναι διαθέσιμη [here](https://reference.aspose.com/tasks/java/).

**Q: Πώς μπορώ να κατεβάσω το Aspose.Tasks for Java;**  
A: Μπορείτε να το κατεβάσετε [here](https://releases.aspose.com/tasks/java/).

**Q: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή [here](https://releases.aspose.com/).

**Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;**  
A: Επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για υποστήριξη.

**Q: Μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks for Java;**  
A: Ναι, αποκτήστε προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/).

**Q: Μπορώ να μετονομάσω τη μορφή του WBS μετά την επανααρίθμηση;**  
A: Απολύτως. Μετά την κλήση `renumberWBSCode`, μπορείτε να επαναλάβετε τις εργασίες και να εφαρμόσετε `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` ώστε να ταιριάζει με τις ονομαστικές σας προτιμήσεις.

**Q: Επηρεάζει η επανααρίθμηση τις εξαρτήσεις των εργασιών;**  
A: Όχι. Η μέθοδος ενημερώνει μόνο το string του WBS· οι συνδέσεις και οι περιορισμοί των εργασιών παραμένουν αμετάβλητοι.

---

**Τελευταία Ενημέρωση:** 2026-03-03  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (latest)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}