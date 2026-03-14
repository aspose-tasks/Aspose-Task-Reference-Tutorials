---
date: 2026-03-14
description: Erfahren Sie, wie Sie nullable Booleans in Aspose.Tasks für .NET verwenden,
  einschließlich der Konvertierung nullable Boolescher Werte und dem Setzen nullable
  Boolescher Eigenschaften.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man nullable Booleans in Aspose.Tasks verwendet
url: /de/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Nullable Booleans in Aspose.Tasks verwendet

In diesem Tutorial zeigen wir **wie man nullable** Booleans verwendet, wenn man mit der Aspose.Tasks .NET API arbeitet. Nullable Booleans bieten Ihnen drei mögliche Zustände—`true`, `false` oder *undefined*—was besonders praktisch für Projekteinstellungen ist, die nicht explizit angegeben werden. Sie sehen, wie man nullable Boolean‑Werte erstellt, konvertiert und **nullable Boolean setzen** Werte, und warum die korrekte Handhabung von nullable Booleans unerwartetes Verhalten in Ihren Terminplanungs‑Anwendungen verhindern kann.

## Schnelle Antworten
- **Was ist ein nullable Boolean?** Ein Typ, der `true`, `false` oder undefined sein kann.  
- **Warum nullable Booleans in Aspose.Tasks verwenden?** Sie ermöglichen es, optionale Projekteigenschaften darzustellen, ohne einen Standardwert zu raten.  
- **Wie konvertiert man einen nullable Boolean in einen regulären bool?** Verwenden Sie die implizite Konvertierung oder prüfen Sie zuerst `IsDefined`.  
- **Was ist die primäre Klasse?** `NullableBool` im `Aspose.Tasks`‑Namespace.  
- **Benötige ich eine Lizenz?** Ja, für die Produktion ist eine gültige Aspose.Tasks‑Lizenz erforderlich.

## Was ist ein Nullable Boolean?

Ein nullable Boolean (`NullableBool`) erweitert den regulären `bool`‑Typ um ein *IsDefined*‑Flag. Wenn `IsDefined` `false` ist, wird der Wert als undefined betrachtet, sodass Sie zwischen „false“ und „nicht gesetzt“ unterscheiden können.

## Warum Nullable Booleans in Projekteinstellungen behandeln?

Viele Projektoptionen—wie **ActualsInSync** oder **HonorConstraints**—sind optional. Die Verwendung eines einfachen `bool` zwingt Sie, `true` oder `false` zu wählen, was unbeabsichtigt die Absicht eines Benutzers überschreiben kann. Durch **Umgang mit nullable Booleans** bewahren Sie den ursprünglichen Zustand und vermeiden versehentliche Konfigurationsänderungen.

## Voraussetzungen

1. **Visual Studio** (oder eine beliebige .NET‑kompatible IDE).  
2. **Aspose.Tasks for .NET** – laden Sie es von [hier](https://releases.aspose.com/tasks/net/) herunter.

## Namespaces importieren

Zuerst importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Jetzt gehen wir jedes Beispiel Schritt für Schritt durch.

## Arbeiten mit `NullableBool`

### Schritt 1: Erstellen Sie eine neue `Project`‑Instanz.

```csharp
var project = new Project();
```

### Schritt 2: Instanziieren Sie ein `NullableBool`‑Objekt mit angegebenen Werten.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Schritt 3: Überprüfen Sie den Wert und den definierten Status des `NullableBool`‑Objekts.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Schritt 4: **Nullable Boolean setzen** im Projekt.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Schritt 5: Instanziieren Sie ein weiteres `NullableBool`‑Objekt mit einem einzelnen Wert.

```csharp
var honorConstraints = new NullableBool(true);
```

### Schritt 6: Zeigen Sie die String‑Repräsentation des `NullableBool`‑Objekts an.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Schritt 7: Verwenden Sie die `NullableBool`‑Instanz, indem Sie sie im Projekt setzen.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Vergleich von `NullableBool`‑Instanzen

### Schritt 1: Instanziieren Sie zwei `NullableBool`‑Objekte.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Schritt 2: Überprüfen Sie die String‑Repräsentation jedes `NullableBool`‑Objekts.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Schritt 3: Implizite Konvertierung zu `bool` und Ausgabe des Ergebnisses.

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

### Schritt 4: Vergleichen Sie die beiden `NullableBool`‑Objekte auf Gleichheit.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Ermitteln des Hash‑Codes von `NullableBool`

### Schritt 1: Instanziieren Sie zwei `NullableBool`‑Objekte.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Schritt 2: Geben Sie den Hash‑Code jedes `NullableBool`‑Objekts aus.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Häufige Fallstricke & Tipps

- **Nehmen Sie niemals an, dass ein nullable Boolean definiert ist.** Prüfen Sie immer `IsDefined`, bevor Sie `Value` verwenden.  
- **Die Konvertierung zu einem regulären bool** ohne Prüfung kann eine Ausnahme auslösen, wenn der Wert undefined ist. Verwenden Sie die implizite Konvertierung nur, wenn Sie sicher sind, dass er definiert ist.  
- **Beim Setzen von Projekteigenschaften** verwenden Sie die `Set`‑Methode mit einem `NullableBool`, um bei Bedarf den undefined‑Zustand beizubehalten.

## Häufig gestellte Fragen

**Q: Was ist ein nullable Boolean?**  
A: Ein nullable Boolean kann `true`, `false` oder einen undefined‑Zustand darstellen, wodurch drei unterschiedliche Ergebnisse möglich sind.

**Q: Wie kann ich einen nullable Boolean sicher in einen regulären bool konvertieren?**  
A: Prüfen Sie zuerst `IsDefined` und verwenden Sie dann die `Value`‑Eigenschaft oder verlassen Sie sich auf die implizite Konvertierung, wenn Sie sicher sind, dass er definiert ist.

**Q: Warum sollte ich nullable Booleans anstelle von einfachen bools in Aspose.Tasks verwenden?**  
A: Sie ermöglichen es, optionale Projekteinstellungen unverändert zu lassen und verhindern versehentliche Überschreibungen.

**Q: Kann ich einen nullable Boolean auf undefined setzen?**  
A: Ja – verwenden Sie den Konstruktor, der nur das defined‑Flag akzeptiert, z. B. `new NullableBool(false, false)`.

**Q: Wo finde ich weitere Dokumentation zu Aspose.Tasks für .NET?**  
A: Detaillierte Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/net/).

**Zuletzt aktualisiert:** 2026-03-14  
**Getestet mit:** Aspose.Tasks for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}