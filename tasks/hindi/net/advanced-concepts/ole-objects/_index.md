---
date: 2026-03-16
description: Aspose.Tasks for .NET का उपयोग करके OLE ऑब्जेक्ट्स को कैसे हटाएँ, सीखें,
  और अपने प्रोजेक्ट्स में OLE को कैसे प्रबंधित करें तथा OLE को प्रभावी ढंग से कैसे
  साफ़ करें, यह जानें।
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET में OLE ऑब्जेक्ट्स को कैसे हटाएँ
url: /hi/net/advanced-concepts/ole-objects/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET में OLE ऑब्जेक्ट्स को कैसे हटाएँ

## परिचय

Aspose.Tasks for .NET आपको Microsoft Project फ़ाइलों के भीतर मौजूद OLE (Object Linking and Embedding) ऑब्जेक्ट्स पर पूर्ण नियंत्रण देता है। इस ट्यूटोरियल में आप **OLE ऑब्जेक्ट्स को कैसे हटाएँ**, **OLE** सामग्री को कैसे **प्रबंधित करें**, और जब इसकी आवश्यकता न रहे तो **OLE** डेटा को साफ़ करने के सटीक चरण सीखेंगे। अंत तक, आप एक प्रोजेक्ट फ़ाइल लोड कर, उसके एम्बेडेड OLE ऑब्जेक्ट्स की जाँच कर, उन्हें सुरक्षित रूप से हटाकर, और साफ‑सुथरा प्रोजेक्ट सहेज सकेंगे—सभी साफ़, पठनीय C# कोड के साथ।

## त्वरित उत्तर
- **OLE ऑब्जेक्ट्स को हटाने का मुख्य तरीका क्या है?** `project.OleObjects.Clear()` का उपयोग करें और फिर प्रोजेक्ट सहेजें।  
- **क्या मुझे विशेष लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+।  
- **क्या हटाने से पहले OLE सामग्री की जाँच कर सकता हूँ?** हाँ, `project.OleObjects` पर इटररेट करके गुण या बाइट्स पढ़ सकते हैं।  
- **क्या बड़े प्रोजेक्ट्स में OLE ऑब्जेक्ट्स को साफ़ करना सुरक्षित है?** बिल्कुल – यह ऑपरेशन तेज़ है और अन्य प्रोजेक्ट डेटा को प्रभावित नहीं करता।

## Aspose.Tasks के संदर्भ में “OLE ऑब्जेक्ट्स हटाना” क्या है?

OLE ऑब्जेक्ट्स को हटाना का अर्थ है Microsoft Project (.mpp) फ़ाइल के भीतर संग्रहीत एम्बेडेड फ़ाइलों (छवियाँ, Excel शीट्स, Word दस्तावेज़ आदि) को हटाना। यह फ़ाइल आकार घटाने, पुरानी रेफ़रेंसेज़ को समाप्त करने, या डेटा‑रिटेंशन नीतियों का पालन करने के लिए उपयोगी है।

## Aspose.Tasks के साथ OLE ऑब्जेक्ट्स का प्रबंधन क्यों करें?

- **सूक्ष्म नियंत्रण** – प्रत्येक OLE ऑब्जेक्ट का ID, नाम, और कच्चे बाइट्स तक पहुँच।  
- **ऑटोमेशन** – बिना Microsoft Project खोले प्रोग्रामेटिक रूप से दर्जनों प्रोजेक्ट्स को साफ़ करें।  
- **क्रॉस‑वर्ज़न समर्थन** – Project 2007‑2023 फ़ाइलों के साथ काम करता है।  

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Aspose.Tasks for .NET** स्थापित। आप इसे [यहाँ](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं।  
2. **C#** और **.NET** इकोसिस्टम का बुनियादी ज्ञान।  
3. **Visual Studio** (Community या उच्चतर) जैसा विकास वातावरण।  

## नेमस्पेसेस इम्पोर्ट करें

पहले, उन नेमस्पेसेस को इम्पोर्ट करें जो Aspose.Tasks API को उजागर करते हैं:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## OLE ऑब्जेक्ट्स को प्रबंधित करने का चरण‑दर‑चरण मार्गदर्शक

नीचे हम तीन सामान्य परिदृश्यों को देखते हैं:

1. **OLE ऑब्जेक्ट्स की जाँच** – उनके गुण और बाइनरी सामग्री का एक स्निपेट पढ़ें।  
2. **सभी OLE ऑब्जेक्ट्स को साफ़ करना** – मूल “OLE ऑब्जेक्ट्स हटाना” ऑपरेशन।  
3. **विज़ुअल प्लेसमेंट जानकारी पढ़ना** – जब आपको Gantt या अन्य व्यूज़ में OLE ऑब्जेक्ट्स की स्थिति समायोजित करनी हो।

### परिदृश्य 1: OLE ऑब्जेक्ट्स की जाँच

#### चरण 1: प्रोजेक्ट फ़ाइल लोड करें  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### चरण 2: OLE ऑब्जेक्ट्स तक पहुँचें  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### चरण 3: OLE ऑब्जेक्ट्स पर इटररेट करें  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### चरण 4: बाइनरी सामग्री का एक छोटा भाग प्राप्त करें (वैकल्पिक)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### परिदृश्य 2: OLE को साफ़ करना – सभी एम्बेडेड ऑब्जेक्ट्स हटाना

#### चरण 1: प्रोजेक्ट फ़ाइल लोड करें  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### चरण 2: OLE ऑब्जेक्ट्स को साफ़ करें  
```csharp
project.OleObjects.Clear();
```

#### चरण 3: साफ़ किया गया प्रोजेक्ट सहेजें  
```csharp
project.Save("ClearedProject.mpp");
```

> **प्रो टिप:** OLE ऑब्जेक्ट्स को साफ़ करने के बाद, आप `project.Save` को अलग फ़ाइल नाम के साथ कॉल कर सकते हैं ताकि मूल फ़ाइल अपरिवर्तित रहे।

### परिदृश्य 3: विज़ुअल ऑब्जेक्ट प्लेसमेंट गुण प्राप्त करना

#### चरण 1: प्रोजेक्ट फ़ाइल लोड करें  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### चरण 2: पहले OLE ऑब्जेक्ट और उसके Gantt व्यू में प्लेसमेंट तक पहुँचें  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### चरण 3: प्लेसमेंट गुण प्राप्त करें  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## सामान्य समस्याएँ और ट्रबलशूटिंग

| समस्या | कारण | समाधान |
|-------|--------|-----|
| `project.OleObjects` खाली है | स्रोत .mpp फ़ाइल में कोई OLE ऑब्जेक्ट नहीं है। | सुनिश्चित करें कि प्रोजेक्ट फ़ाइल वास्तव में OLE डेटा एम्बेड करती है (जैसे, एक संलग्न Excel शीट)। |
| `project.Save` अपवाद फेंकता है | फ़ाइल लॉक है या आपके पास लिखने की अनुमति नहीं है। | फ़ाइल के सभी खुले इंस्टेंस बंद करें और लक्ष्य फ़ोल्डर में लिखने की अनुमति सुनिश्चित करें। |
| सामग्री बाइट्स भ्रष्ट दिख रही हैं | आप पूरी बाइट एरे को टेक्स्ट के रूप में पढ़ रहे हैं। | `Get10Bytes` का उपयोग करें या बाइट्स को फ़ाइल में लिखकर उचित व्यूअर में देखें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks विभिन्न OLE ऑब्जेक्ट फ़ॉर्मेट्स को संभाल सकता है?**  
उत्तर: हाँ, यह छवियों, Office दस्तावेज़ों, PDFs, और कई अन्य OLE फ़ॉर्मेट्स को समर्थन देता है।

**प्रश्न: क्या API पुराने Microsoft Project संस्करणों के साथ संगत है?**  
उत्तर: बिल्कुल – Aspose.Tasks 2007 से लेकर नवीनतम 2023 रिलीज़ तक के प्रोजेक्ट फ़ाइलों के साथ काम करता है।

**प्रश्न: सभी को साफ़ करने के बजाय केवल विशिष्ट OLE ऑब्जेक्ट्स को कैसे हटाएँ?**  
उत्तर: इच्छित `OleObject` को उसके `Id` या `Name` से खोजें और सहेजने से पहले `project.OleObjects.Remove(oleObject)` कॉल करें।

**प्रश्न: क्या OLE ऑब्जेक्ट्स को साफ़ करने से टास्क डिपेंडेंसीज़ या शेड्यूल प्रभावित होते हैं?**  
उत्तर: नहीं। OLE ऑब्जेक्ट्स स्वतंत्र विज़ुअल तत्व हैं; उन्हें हटाने से टास्क संबंध नहीं बदलते।

**प्रश्न: OLE मैनिपुलेशन पर और उदाहरण कहाँ मिलेंगे?**  
उत्तर: आधिकारिक Aspose.Tasks दस्तावेज़ और `OleObject` तथा `VisualObjectsPlacements` क्लासेस के API रेफ़रेंस देखें।

## निष्कर्ष

हमने Aspose.Tasks for .NET में **OLE ऑब्जेक्ट्स को हटाने** और OLE सामग्री को प्रबंधित करने के सभी आवश्यक पहलुओं को कवर किया। चरण‑दर‑चरण उदाहरणों का पालन करके, आप OLE ऑब्जेक्ट्स की जाँच, सफ़ाई, और विज़ुअल प्लेसमेंट को समायोजित कर सकते हैं, जिससे आपके प्रोजेक्ट फ़ाइलें हल्की और केंद्रित रहें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-16  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose  

---