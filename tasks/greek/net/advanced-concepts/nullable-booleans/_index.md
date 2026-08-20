---
date: 2026-03-14
description: Μάθετε πώς να χρησιμοποιείτε nullable boolean στο Aspose.Tasks για .NET,
  συμπεριλαμβανομένης της μετατροπής nullable boolean τιμών και του ορισμού nullable
  boolean ιδιοτήτων.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Πώς να χρησιμοποιήσετε Nullable Booleans στο Aspose.Tasks
url: /el/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Χρησιμοποιήσετε Nullable Booleans στο Aspose.Tasks

Σε αυτό το σεμινάριο θα δείξουμε **πώς να χρησιμοποιήσετε nullable** booleans όταν εργάζεστε με το Aspose.Tasks .NET API. Τα nullable booleans σας παρέχουν τρεις δυνατές καταστάσεις—`true`, `false`, ή *undefined*—που είναι ιδιαίτερα χρήσιμες για ρυθμίσεις επιπέδου έργου που ενδέχεται να μην έχουν καθοριστεί ρητά. Θα δείτε πώς να δημιουργήσετε, να μετατρέψετε και **να ορίσετε nullable boolean** τιμές, και γιατί η σωστή διαχείριση των nullable booleans μπορεί να αποτρέψει απρόσμενη συμπεριφορά στις εφαρμογές χρονοπρογραμματισμού σας.

## Γρήγορες Απαντήσεις
- **Τι είναι ένα nullable boolean;** Ένας τύπος που μπορεί να περιέχει `true`, `false`, ή να είναι undefined.  
- **Γιατί να χρησιμοποιήσετε nullable booleans στο Aspose.Tasks;** Σας επιτρέπουν να αντιπροσωπεύετε προαιρετικές ιδιότητες του έργου χωρίς να υποθέτετε προεπιλογή.  
- **Πώς να μετατρέψετε ένα nullable boolean σε κανονικό bool;** Χρησιμοποιήστε τη ρητή μετατροπή ή ελέγξτε πρώτα το `IsDefined`.  
- **Ποια είναι η κύρια κλάση;** `NullableBool` στο namespace `Aspose.Tasks`.  
- **Χρειάζομαι άδεια;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για χρήση σε παραγωγή.

## Τι είναι ένα Nullable Boolean;

Ένα nullable boolean (`NullableBool`) επεκτείνει τον κανονικό τύπο `bool` προσθέτοντας μια σημαία *IsDefined*. Όταν το `IsDefined` είναι `false`, η τιμή θεωρείται undefined, επιτρέποντάς σας να διακρίνετε μεταξύ “false” και “not set”.

## Γιατί να Διαχειρίζεστε Nullable Booleans στις Ρυθμίσεις Έργου;

Πολλές επιλογές έργου—όπως **ActualsInSync** ή **HonorConstraints**—είναι προαιρετικές. Η χρήση ενός απλού `bool` σας αναγκάζει να επιλέξετε `true` ή `false`, κάτι που μπορεί ακούσια να αντικαταστήσει την πρόθεση του χρήστη. Με το **διαχειρίζεστε nullable booleans**, διατηρείτε την αρχική κατάσταση και αποτρέπετε τυχαίες αλλαγές διαμόρφωσης.

## Προαπαιτούμενα

1. **Visual Studio** (ή οποιοδήποτε IDE συμβατό με .NET).  
2. **Aspose.Tasks for .NET** – κατεβάστε το από [εδώ](https://releases.aspose.com/tasks/net/).

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τα απαιτούμενα namespaces:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Τώρα ας περάσουμε από κάθε παράδειγμα βήμα‑βήμα.

## Εργασία με `NullableBool`

### Βήμα 1: Δημιουργήστε ένα νέο αντικείμενο `Project`.

```csharp
var project = new Project();
```

### Βήμα 2: Δημιουργήστε ένα αντικείμενο `NullableBool` με καθορισμένες τιμές.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Βήμα 3: Ελέγξτε την τιμή και την κατάσταση ορισμού του αντικειμένου `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Βήμα 4: **Ορίστε nullable boolean** στο έργο.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Βήμα 5: Δημιουργήστε ένα άλλο αντικείμενο `NullableBool` με μία τιμή.

```csharp
var honorConstraints = new NullableBool(true);
```

### Βήμα 6: Εμφανίστε την αναπαράσταση συμβολοσειράς του αντικειμένου `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Βήμα 7: Χρησιμοποιήστε το παράδειγμα `NullableBool` ορίζοντάς το στο έργο.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Σύγκριση Παραδειγμάτων `NullableBool`

### Βήμα 1: Δημιουργήστε δύο αντικείμενα `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Βήμα 2: Ελέγξτε την αναπαράσταση συμβολοσειράς του κάθε αντικειμένου `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Βήμα 3: Ρητή μετατροπή σε `bool` και εκτύπωση του αποτελέσματος.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Βήμα 4: Συγκρίνετε τα δύο αντικείμενα `NullableBool` για ισότητα.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Λήψη του Hash Code του `NullableBool`

### Βήμα 1: Δημιουργήστε δύο αντικείμενα `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Βήμα 2: Εκτυπώστε το hash code για κάθε αντικείμενο `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές

- **Ποτέ μην υποθέτετε ότι ένα nullable boolean είναι ορισμένο.** Πάντα ελέγξτε το `IsDefined` πριν χρησιμοποιήσετε το `Value`.  
- **Η μετατροπή σε κανονικό bool** χωρίς έλεγχο μπορεί να προκαλέσει εξαίρεση αν η τιμή είναι undefined. Χρησιμοποιήστε τη ρητή μετατροπή μόνο όταν είστε σίγουροι ότι είναι ορισμένη.  
- **Κατά τον ορισμό ιδιοτήτων έργου**, χρησιμοποιήστε τη μέθοδο `Set` με ένα `NullableBool` για να διατηρήσετε την κατάσταση undefined εάν χρειάζεται.

## Συχνές Ερωτήσεις

**Q: Τι είναι ένα nullable boolean;**  
A: Ένα nullable boolean μπορεί να αντιπροσωπεύει `true`, `false`, ή μια κατάσταση undefined, επιτρέποντας τρία διαφορετικά αποτελέσματα.

**Q: Πώς μπορώ να μετατρέψω ένα nullable boolean σε κανονικό bool με ασφάλεια;**  
A: Ελέγξτε πρώτα το `IsDefined`, μετά χρησιμοποιήστε την ιδιότητα `Value` ή βασιστείτε στη ρητή μετατροπή όταν είστε βέβαιοι ότι είναι ορισμένο.

**Q: Γιατί πρέπει να χρησιμοποιώ nullable booleans αντί για απλά bools στο Aspose.Tasks;**  
A: Σας επιτρέπουν να διατηρήσετε τις προαιρετικές ρυθμίσεις του έργου αμετάβλητες, αποτρέποντας τυχαίες αντικαταστάσεις.

**Q: Μπορώ να ορίσω ένα nullable boolean ως undefined;**  
A: Ναι—χρησιμοποιήστε τον κατασκευαστή που δέχεται μόνο τη σημαία ορισμού, π.χ., `new NullableBool(false, false)`.

**Q: Πού μπορώ να βρω περαιτέρω τεκμηρίωση για το Aspose.Tasks για .NET;**  
A: Μπορείτε να βρείτε λεπτομερή τεκμηρίωση [εδώ](https://reference.aspose.com/tasks/net/).

**Τελευταία Ενημέρωση:** 2026-03-14  
**Δοκιμάστηκε Με:** Aspose.Tasks for .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}