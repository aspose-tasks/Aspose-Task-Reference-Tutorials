---
title: Mastering Timephased Data Collection στο Aspose.Tasks
linktitle: Συλλογή δεδομένων χρονικής φάσης στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε τη συλλογή δεδομένων χρονικής φάσης στο Aspose.Tasks για .NET. Οδηγός βήμα προς βήμα, συχνές ερωτήσεις και πολλά άλλα. Βελτιώστε τις δυνατότητες διαχείρισης του έργου σας σήμερα!
type: docs
weight: 15
url: /el/net/text-view-configuration/timephased-data-collection/
---
## Εισαγωγή
Θέλετε να αξιοποιήσετε τη δύναμη των δεδομένων χρονικής φάσης στις εφαρμογές σας .NET χρησιμοποιώντας το Aspose.Tasks; Μην ψάχνετε άλλο! Αυτός ο περιεκτικός οδηγός θα σας καθοδηγήσει στη διαδικασία συλλογής δεδομένων χρονικής φάσης με το Aspose.Tasks για .NET, διασφαλίζοντας ότι θα αξιοποιήσετε στο έπακρο αυτήν την ισχυρή βιβλιοθήκη.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από[Aspose.Tasks .NET Documentation](https://reference.aspose.com/tasks/net/).
2. Περιβάλλον ανάπτυξης .NET: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα λειτουργικό περιβάλλον ανάπτυξης .NET.
3. Ο Κατάλογος εγγράφων σας: Αντικαταστήστε το σύμβολο κράτησης θέσης "Ο Κατάλογος εγγράφων σας" στα αποσπάσματα κώδικα με τη διαδρομή προς τον κατάλογο εγγράφων σας.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας .NET, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τις λειτουργίες Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Δημιουργήστε ένα έργο και πόρους
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Προσθέστε Εργασίες στο Έργο
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Ορισμός ιδιοτήτων εργασίας...
var task2 = project.RootTask.Children.Add("Task 2");
// Ορισμός ιδιοτήτων task2...
```
## 3. Αναθέστε πόρους σε εργασίες
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Ορισμός ιδιοτήτων ανάθεσης...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Ορισμός ιδιοτήτων ανάθεσης2...
```
## 4. Εργαστείτε με δεδομένα χρονικής φάσης
```csharp
// Ορισμός περιγράμματος εργασίας
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Ελέγξτε εάν η συλλογή δεδομένων σε χρονική φάση είναι μόνο για ανάγνωση
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Διαγραφή δεδομένων χρονικής φάσης που δημιουργούνται
assignment.TimephasedData.Clear();
// Δημιουργήστε και προσθέστε δεδομένα χρονικής φάσης
var td = new TimephasedData
{
    // Ορισμός ιδιοτήτων δεδομένων χρονικής φάσης...
};
assignment.TimephasedData.Add(td);
// Προσθέστε μια λίστα δεδομένων χρονικής φάσης
var list = new List<TimephasedData>();
// Προσθέστε περισσότερα στοιχεία δεδομένων χρονικής φάσης στη λίστα...
assignment.TimephasedData.AddRange(list);
// Φιλτράρετε δεδομένα χρονικής φάσης κατά τύπο και εύρος ημερομηνιών
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Εκτύπωση φιλτραρισμένων δεδομένων χρονικής φάσης...
```
## 5. Χειριστείτε τα δεδομένα χρονικής φάσης
```csharp
//Προσθέστε ένα λάθος στοιχείο δεδομένων χρονικής φάσης και, στη συνέχεια, διαγράψτε το
var td4 = new TimephasedData
{
    // Ορισμός λανθασμένων ιδιοτήτων δεδομένων χρονικής φάσης...
};
assignment.TimephasedData.Add(td4);
// Διαγράψτε το λάθος στοιχείο δεδομένων χρονικής φάσης
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Επανάληψη σε όλα τα στοιχεία χρονικής φάσης
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Εκτύπωση στοιχείων σε χρονική φάση...
}
```
## 6. Αντιγράψτε τα δεδομένα χρονικής φάσης σε άλλη εργασία
```csharp
// Αντιγράψτε δεδομένα χρονικής φάσης σε άλλη εργασία
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Μετατρέψτε τη συλλογή σε μια απλή λίστα
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Καταργήστε τα στοιχεία δεδομένων χρονικής φάσης ένα προς ένα
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## συμπέρασμα
Συμπερασματικά, αυτό το σεμινάριο παρέχει μια λεπτομερή περιγραφή της συλλογής δεδομένων χρονικής φάσης χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να ενσωματώσετε απρόσκοπτα αυτή τη λειτουργία στα έργα σας, επιτρέποντας την αποτελεσματική παρακολούθηση χρόνου και διαχείριση πόρων.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με άλλα εργαλεία διαχείρισης έργου;
Ναι, το Aspose.Tasks για .NET έχει σχεδιαστεί για να λειτουργεί με δημοφιλή εργαλεία διαχείρισης έργων και υποστηρίζει διάφορες μορφές αρχείων.
### Υπάρχει όριο στον αριθμό των πόρων και των εργασιών που μπορώ να διαχειριστώ με το Aspose.Tasks;
Το Aspose.Tasks χειρίζεται έργα διαφορετικών μεγεθών και δεν υπάρχει αυστηρός περιορισμός στον αριθμό των πόρων και των εργασιών.
### Πώς μπορώ να λάβω υποστήριξη για τυχόν ζητήματα ή ερωτήματα που σχετίζονται με το Aspose.Tasks για .NET;
 Για υποστήριξη, επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για να συνδεθείτε με την κοινότητα και να λάβετε βοήθεια.
### Μπορώ να δοκιμάσω το Aspose.Tasks για .NET πριν το αγοράσω;
 Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Tasks για .NET μεταβαίνοντας στο[δωρεάν δοκιμή](https://releases.aspose.com/).
### Πού μπορώ να αγοράσω άδεια χρήσης για το Aspose.Tasks για .NET;
 Μπορείτε να αγοράσετε μια άδεια χρήσης για το Aspose.Tasks για .NET[εδώ](https://purchase.aspose.com/buy).