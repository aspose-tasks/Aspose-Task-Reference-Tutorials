---
title: Κύριος χειρισμός δεδομένων σε χρονική φάση με Aspose.Tasks για .NET
linktitle: Χειρισμός δεδομένων χρονικής φάσης στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε το Aspose.Tasks για .NET για να χειριστείτε εύκολα δεδομένα χρονικής φάσης, να βελτιώσετε τον σχεδιασμό του έργου και να βελτιστοποιήσετε τη διαχείριση πόρων. #Aspose #Tasks #MS Project
weight: 14
url: /el/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κύριος χειρισμός δεδομένων σε χρονική φάση με Aspose.Tasks για .NET

## Εισαγωγή
Στον κόσμο της διαχείρισης έργων, ο αποτελεσματικός χειρισμός των δεδομένων χρονικής φάσης είναι ζωτικής σημασίας για την κατανομή πόρων, την εκτίμηση κόστους και τον συνολικό σχεδιασμό του έργου. Το Aspose.Tasks για .NET παρέχει μια ισχυρή λύση για απρόσκοπτη εργασία με προσαρμοσμένα δεδομένα χρονικής φάσης. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία χειρισμού δεδομένων χρονικής φάσης χρησιμοποιώντας το Aspose.Tasks, επιτρέποντάς σας να βελτιστοποιήσετε τη διαχείριση πόρων στα έργα σας.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική κατανόηση των εννοιών διαχείρισης έργου.
-  Εγκατέστησε το Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
- Ένα πρόγραμμα επεξεργασίας κώδικα, όπως το Visual Studio, για την υλοποίηση των παρεχόμενων παραδειγμάτων.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας .NET, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τις λειτουργίες του Aspose.Tasks. Προσθέστε τις ακόλουθες γραμμές στην αρχή του αρχείου κώδικα:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα για να σας καθοδηγήσουμε στον χειρισμό δεδομένων χρονικής φάσης χρησιμοποιώντας το Aspose.Tasks:
## Βήμα 1: Ρύθμιση του έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Εδώ, αρχικοποιούμε ένα νέο έργο και ορίζουμε τον τρόπο υπολογισμού του.
## Βήμα 2: Καθορισμός πόρων και εργασιών
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Δημιουργήστε πόρους εργασίας και κόστους, καθώς και μια εργασία, για την προσομοίωση μιας δομής έργου.
## Βήμα 3: Εκχώρηση πόρων στο Task
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Αναθέστε πόρους εργασίας και κόστους στην εργασία.
## Βήμα 4: Προσθήκη προσαρμοσμένων δεδομένων χρονικής φάσης
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Παρόμοια βήματα για την εκχώρηση κόστους
costAssignment.TimephasedData.Clear();
```
Προσθέστε προσαρμοσμένα δεδομένα χρονικής φάσης τόσο για εργασίες όσο και για αναθέσεις κόστους.
## Βήμα 5: Εμφάνιση δεδομένων χρονικής φάσης
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Εμφάνιση σχετικών πληροφοριών για κάθε εισαγωγή δεδομένων σε χρονική φάση
    }
}
```
Τέλος, εμφανίστε τα δεδομένα χρονικής φάσης για κάθε ανάθεση.
#
## συμπέρασμα
Ο αποτελεσματικός χειρισμός δεδομένων χρονικής φάσης στο Aspose.Tasks ανοίγει νέες δυνατότητες για λεπτομερή προγραμματισμό έργου και διαχείριση πόρων. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, έχετε μάθει πώς να χειρίζεστε δεδομένα χρονικής φάσης για να ανταποκρίνεστε στις συγκεκριμένες ανάγκες των έργων σας.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλα εργαλεία διαχείρισης έργου;
Το Aspose.Tasks έχει σχεδιαστεί κυρίως για ανάπτυξη .NET. Ωστόσο, οι λειτουργίες του μπορούν να συμπληρώσουν διάφορα εργαλεία διαχείρισης έργου.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για .NET;
 Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για .NET;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη.
### Τι είναι η προσωρινή άδεια και πώς μπορώ να αποκτήσω;
 Μάθετε για τις προσωρινές άδειες[εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Tasks για .NET;
 Ανατρέξτε στην περιεκτική[τεκμηρίωση](https://reference.aspose.com/tasks/net/) για αναλυτικές πληροφορίες.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
