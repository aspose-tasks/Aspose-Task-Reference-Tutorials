---
date: 2026-10-15
description: Μάθετε πώς να προσθέσετε custom property και να διαχειριστείτε custom
  project properties στο Aspose.Tasks για .NET, ενισχύοντας τον έλεγχο του project
  metadata σας.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Διαχείριση της συλλογής Custom Project Property στο Aspose.Tasks
og_description: Προσθέστε custom property στα αρχεία του project σας με το Aspose.Tasks
  για .NET. Αυτός ο οδηγός δείχνει πώς να διαχειριστείτε custom properties, να τα
  διαβάσετε και να προσθέσετε boolean ή string τιμές αποδοτικά.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Προσθήκη custom property χρησιμοποιώντας το Aspose.Tasks .NET API για έργα
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Πώς να προσθέσετε custom property στο Aspose.Tasks για .NET
url: /el/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε προσαρμοσμένη ιδιότητα στο Aspose.Tasks για .NET

## Εισαγωγή

Η υποστήριξη προσθήκης προσαρμοσμένης ιδιότητας σας επιτρέπει να αποθηκεύετε μεταδεδομένα ειδικά για το έργο που δεν καλύπτονται από τα ενσωματωμένα πεδία. Σε αυτό το tutorial θα μάθετε πώς να **προσθέσετε προσαρμοσμένη ιδιότητα**, να την διαβάσετε ξανά και να διαχειριστείτε ολόκληρη τη συλλογή προσαρμοσμένων ιδιοτήτων χρησιμοποιώντας το Aspose.Tasks για .NET. Στο τέλος θα μπορείτε να προσαρμόζετε τα αρχεία έργου με τιμές Boolean, DateTime, Double και String που ταιριάζουν στους επιχειρηματικούς σας κανόνες.

## Γρήγορες απαντήσεις
- **Μπορώ να προσθέσω μια Boolean προσαρμοσμένη ιδιότητα;** Ναι – χρησιμοποιήστε `CustomPropertyType.Boolean`.
- **Πόσοι τύποι προσαρμοσμένων ιδιοτήτων υποστηρίζονται;** Τέσσερις: Boolean, DateTime, Double, String.
- **Η συλλογή προσαρμοσμένων ιδιοτήτων είναι μόνο για ανάγνωση;** Μπορεί να είναι μόνο για ανάγνωση εάν το έργο φορτωθεί από πηγή μόνο για ανάγνωση.
- **Χρειάζομαι άδεια για τη χρήση αυτής της λειτουργίας;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.
- **Ποιες εκδόσεις .NET είναι συμβατές;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι μια προσαρμοσμένη ιδιότητα;

Μια προσαρμοσμένη ιδιότητα είναι ένα πεδίο μεταδεδομένων που ορίζεται από τον χρήστη και συνδέεται με ένα αντικείμενο Project. Σας επιτρέπει να αποθηκεύετε πρόσθετες πληροφορίες όπως “Επίπεδο Κινδύνου”, “Αναγνωριστικό Πελάτη” ή οποιαδήποτε Boolean σημαία που δεν καλύπτεται από τα τυπικά πεδία του MS‑Project.

## Γιατί να προσθέσετε προσαρμοσμένη ιδιότητα στο Aspose.Tasks;

Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να διαχειριστεί έργα με **έως 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η προσθήκη προσαρμοσμένων ιδιοτήτων σας επιτρέπει να ενσωματώσετε κρίσιμα επιχειρηματικά δεδομένα απευθείας στο αρχείο έργου, εξαλείφοντας την ανάγκη για εξωτερικές βάσεις δεδομένων και διασφαλίζοντας ότι τα δεδομένα μεταφέρονται μαζί με το έργο.

## Προαπαιτούμενα

- Visual Studio (οποιαδήποτε πρόσφατη έκδοση) εγκατεστημένο στον υπολογιστή σας.  
- Aspose.Tasks for .NET – κατεβάστε το από το [download link](https://releases.aspose.com/tasks/net/).  
- Βασική εξοικείωση με τη σύνταξη C# και τη δομή έργου .NET.

## Εισαγωγή χώρων ονομάτων

Οι παρακάτω χώροι ονομάτων σας δίνουν πρόσβαση στο βασικό μοντέλο έργου και στα API προσαρμοσμένων ιδιοτήτων.

```csharp
using Aspose.Tasks;
using System;


```

## Πώς να προσθέσετε προσαρμοσμένη ιδιότητα στο Aspose.Tasks;

Για να προσθέσετε μια προσαρμοσμένη ιδιότητα, πρώτα φορτώστε το έργο, στη συνέχεια δημιουργήστε ένα αντικείμενο `CustomProperty`, ορίστε το όνομα, τον τύπο και την τιμή του, και τέλος προσθέστε το στη συλλογή `CustomProperties` του έργου. Αυτή η λειτουργία ενσωματώνει τα μεταδεδομένα απευθείας στο αρχείο έργου, και οι αλλαγές αποθηκεύονται όταν καλέσετε `project.Save(...)`.  

`CustomProperty` αντιπροσωπεύει ένα μοναδικό πεδίο που ορίζεται από τον χρήστη και συνδέεται με ένα έργο.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Βήμα 1: αρχικοποίηση έργου

`Project` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο έργου στο Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Βήμα 2: έλεγχος ετοιμότητας συλλογής προσαρμοσμένων ιδιοτήτων

`CustomProperties` είναι η συλλογή που περιέχει όλα τα αντικείμενα προσαρμοσμένων ιδιοτήτων για ένα έργο.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Βήμα 3: προσθήκη προσαρμοσμένων ιδιοτήτων

Η μέθοδος `Add` εισάγει μια νέα προσαρμοσμένη ιδιότητα στη συλλογή του έργου.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Βήμα 4: πρόσβαση σε προσαρμοσμένες ιδιότητες

Η συλλογή `CustomProperties` υλοποιεί το IEnumerable, επιτρέποντας την επανάληψη πάνω σε κάθε `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Βήμα 5: ανάκτηση τιμής προσαρμοσμένης ιδιότητας

Η μέθοδος `Get` επιστρέφει την τιμή μιας προσαρμοσμένης ιδιότητας βάσει του ονόματός της.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Βήμα 6: επανάληψη πάνω σε ονόματα προσαρμοσμένων ιδιοτήτων

Η ιδιότητα `Names` παρέχει μια λίστα με όλα τα ονόματα προσαρμοσμένων ιδιοτήτων στη συλλογή.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Βήμα 7: αφαίρεση ή εκκαθάριση προσαρμοσμένων ιδιοτήτων

Η μέθοδος `Remove` διαγράφει μια συγκεκριμένη ιδιότητα, ενώ η `Clear` αδειάζει ολόκληρη τη συλλογή.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Κοινά προβλήματα και αντιμετώπιση σφαλμάτων

- **Συλλογή μόνο για ανάγνωση** – Εάν το `project.CustomProperties.IsReadOnly` επιστρέφει `true`, βεβαιωθείτε ότι το αρχείο προέλευσης δεν είναι ανοιχτό με αποκλειστική πρόσβαση μόνο για ανάγνωση ή αντιγράψτε το σε θέση εγγραφής πριν την επεξεργασία.  
- **Ασυμφωνία τύπου** – Η ανάθεση τιμής που δεν ταιριάζει με τον δηλωμένο `CustomPropertyType` προκαλεί `ArgumentException`. Πάντα ορίζετε το `Value` μετά τον ορισμό του σωστού `Type`.  
- **Αποθήκευση αλλαγών** – Μετά την προσθήκη ή αφαίρεση ιδιοτήτων, καλέστε `project.Save("output.mpp")` για να διατηρήσετε τις τροποποιήσεις· διαφορετικά οι αλλαγές παραμένουν μόνο στη μνήμη.

## Συχνές ερωτήσεις

**Q: Μπορώ να προσθέσω προσαρμοσμένες ιδιότητες οποιουδήποτε τύπου δεδομένων στο έργο μου χρησιμοποιώντας το Aspose.Tasks για .NET;**  
A: Ναι, μπορείτε να προσθέσετε προσαρμοσμένες ιδιότητες που υποστηρίζουν τύπους Boolean, DateTime, Double και String.

**Q: Είναι δυνατόν να επαναλάβετε πάνω σε ονόματα προσαρμοσμένων ιδιοτήτων στο Aspose.Tasks για .NET;**  
A: Απόλυτα, μπορείτε να επαναλάβετε πάνω σε ονόματα προσαρμοσμένων ιδιοτήτων χρησιμοποιώντας την ιδιότητα `Names`.

**Q: Πώς μπορώ να αφαιρέσω μια συγκεκριμένη προσαρμοσμένη ιδιότητα από το έργο μου;**  
A: Μπορείτε να αφαιρέσετε μια προσαρμοσμένη ιδιότητα με το όνομά της χρησιμοποιώντας τη μέθοδο `Remove`.

**Q: Παρέχει το Aspose.Tasks για .NET υποστήριξη για προσωρινές άδειες;**  
A: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια από τον ιστότοπο της Aspose για σκοπούς αξιολόγησης.

**Q: Πού μπορώ να βρω υποστήριξη ή περαιτέρω βοήθεια σχετικά με το Aspose.Tasks για .NET;**  
A: Μπορείτε να επισκεφθείτε το φόρουμ Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για οποιεσδήποτε ερωτήσεις ή βοήθεια.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Πώς να διαβάσετε ενσωματωμένες ιδιότητες έργου χρησιμοποιώντας Aspose.Tasks για .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Διαχείριση Συλλογής Χαρακτηριστικών MS Project στο Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Τύποι Προσαρμοσμένων Πεδίων Aspose.Tasks – Ημερολόγιο και Προγραμματισμός](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}