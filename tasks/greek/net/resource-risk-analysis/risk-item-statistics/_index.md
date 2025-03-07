---
title: Στατιστικά στοιχεία για στοιχεία κινδύνου στο Aspose.Tasks
linktitle: Στατιστικά στοιχεία για στοιχεία κινδύνου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ξεκλειδώστε τη δύναμη της ανάλυσης κινδύνου σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Αποκτήστε γνώσεις, μετριάστε τις αβεβαιότητες και οδηγήστε την επιτυχία του έργου χωρίς κόπο.
weight: 21
url: /el/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Στατιστικά στοιχεία για στοιχεία κινδύνου στο Aspose.Tasks

## Εισαγωγή
Θέλετε να βελτιώσετε τις ικανότητές σας στη διαχείριση έργων χρησιμοποιώντας το Aspose.Tasks για .NET; Εμβαθύνετε στη σφαίρα της ανάλυσης κινδύνου με το βήμα προς βήμα σεμινάριο μας σχετικά με τη λήψη στατιστικών στοιχείων για στοιχεία κινδύνου σε αρχεία MS Project. Αξιοποιώντας τις ισχυρές δυνατότητες του Aspose.Tasks, μπορείτε να αποκτήσετε ανεκτίμητες γνώσεις σχετικά με τις αβεβαιότητες του έργου και να λάβετε τεκμηριωμένες αποφάσεις για τον αποτελεσματικό μετριασμό των κινδύνων.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το ταξίδι, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από το[Aspose.Tasks για τεκμηρίωση .NET](https://reference.aspose.com/tasks/net/). Αυτή η βιβλιοθήκη σάς εξοπλίζει με ισχυρά εργαλεία για τον προγραμματισμό των αρχείων του MS Project.
2. .NET Development Environment: Ρυθμίστε το περιβάλλον ανάπτυξης .NET, συμπεριλαμβανομένου του Visual Studio ή οποιουδήποτε άλλου IDE της επιλογής σας, για να διευκολύνετε την απρόσκοπτη ενσωμάτωση του Aspose.Tasks στα έργα σας.

## Εισαγωγή χώρων ονομάτων
Ενσωματώστε τους απαραίτητους χώρους ονομάτων στο έργο σας για να αξιοποιήσετε τις λειτουργίες του Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Βήμα 1: Ορισμός καταλόγου δεδομένων
```csharp
String DataDir = "Your Document Directory";
```
 Φροντίστε να αντικαταστήσετε`"Your Document Directory"` με τη διαδρομή προς τον κατάλογο εγγράφων σας όπου βρίσκονται τα αρχεία MS Project.
## Βήμα 2: Διαμόρφωση ρυθμίσεων ανάλυσης κινδύνου
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Ρυθμίστε το`IterationsCount`παράμετρος που βασίζεται στις απαιτήσεις του έργου σας για τον έλεγχο της ακρίβειας της ανάλυσης κινδύνου.
## Βήμα 3: Φορτώστε το αρχείο MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Φορτώστε το επιθυμητό αρχείο MS Project στο`project` αντικείμενο για περαιτέρω ανάλυση.
## Βήμα 4: Καθορίστε την εργασία και αρχικοποιήστε το μοτίβο κινδύνου
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Καθορίστε την εργασία για την ανάλυση κινδύνου και διαμορφώστε το πρότυπο κινδύνου με κατάλληλες παραμέτρους όπως ο τύπος διανομής, οι αισιόδοξες και απαισιόδοξες διάρκειες και το επίπεδο εμπιστοσύνης.
## Βήμα 5: Αναλύστε τους κινδύνους του έργου
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Ξεκινήστε τη διαδικασία ανάλυσης κινδύνου χρησιμοποιώντας τις καθορισμένες ρυθμίσεις και τα δεδομένα του έργου.
## Βήμα 6: Ανάκτηση και εμφάνιση στατιστικών στοιχείων
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Ανακτήστε και εμφανίστε διάφορες στατιστικές μετρήσεις που σχετίζονται με στοιχεία κινδύνου στο αρχείο MS Project, συμπεριλαμβανομένων της αναμενόμενης τιμής, της τυπικής απόκλισης, των εκατοστημόνων, των ελάχιστων και των μέγιστων τιμών.

## συμπέρασμα
Συμπερασματικά, η εξοικείωση με την ανάλυση κινδύνου σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET ανοίγει ένα πεδίο δυνατοτήτων για τους διαχειριστές έργων και τους ενδιαφερόμενους. Ακολουθώντας το ολοκληρωμένο σεμινάριο μας, μπορείτε να πλοηγηθείτε στις αβεβαιότητες με σιγουριά, διασφαλίζοντας επιτυχημένα αποτελέσματα του έργου.
## Συχνές ερωτήσεις
### Μπορώ να ενσωματώσω το Aspose.Tasks με άλλες βιβλιοθήκες .NET για εκτεταμένη λειτουργικότητα;
Απολύτως! Το Aspose.Tasks ενσωματώνεται απρόσκοπτα με διάφορες βιβλιοθήκες .NET, επιτρέποντάς σας να ενισχύσετε τις δυνατότητές του σύμφωνα με τις απαιτήσεις του έργου σας.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;
 Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Tasks μεταβαίνοντας στο[δωρεάν δοκιμή](https://releases.aspose.com/) διαθέσιμο στην ιστοσελίδα μας.
### Πόσο συχνά κυκλοφορούν ενημερώσεις και βελτιώσεις για το Aspose.Tasks;
Προσπαθούμε να βελτιώνουμε συνεχώς το Aspose.Tasks δημοσιεύοντας ενημερώσεις και βελτιώσεις περιοδικά, διασφαλίζοντας ότι έχετε πάντα πρόσβαση στις πιο πρόσφατες δυνατότητες και βελτιστοποιήσεις.
### Μπορώ να αποκτήσω τεχνική υποστήριξη για το Aspose.Tasks;
Σίγουρα! Η ειδική ομάδα υποστήριξής μας είναι άμεσα διαθέσιμη στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για να σας βοηθήσει με τυχόν απορίες ή προκλήσεις που μπορεί να συναντήσετε κατά τη διάρκεια της διαδρομής υλοποίησης.
### Προσφέρετε προσωρινές άδειες για βραχυπρόθεσμα έργα;
 Ναι, εάν χρειάζεστε Aspose.Tasks για ένα βραχυπρόθεσμο έργο, μπορείτε να επωφεληθείτε από το βολικό μας[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) επιλογή να εκπληρώσετε τις ανάγκες αδειοδότησης χωρίς μακροπρόθεσμες δεσμεύσεις.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
