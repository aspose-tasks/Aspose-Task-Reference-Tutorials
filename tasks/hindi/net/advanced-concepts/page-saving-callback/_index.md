---
date: 2026-03-16
description: Aspose.Tasks for .NET में पेज सहेजने के कॉलबैक को लागू करना सीखें, जिससे
  मल्टी‑पेज दस्तावेज़ आउटपुट स्ट्रीम्स का अनुकूलित प्रबंधन संभव हो सके।
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में पृष्ठ सहेजने के कॉलबैक को लागू करें
url: /hi/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में पेज सहेजने के कॉलबैक को लागू करें

## परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि **implement page saving callback** को Aspose.Tasks for .NET में कैसे लागू किया जाता है। यह शक्तिशाली सुविधा आपको बहु‑पृष्ठ दस्तावेज़ के प्रत्येक पृष्ठ को अपनी पसंद के स्ट्रीम की ओर निर्देशित करने की अनुमति देती है, जिससे आप आउटपुट को कैसे संग्रहीत या आगे प्रोसेस किया जाए, इस पर पूर्ण नियंत्रण प्राप्त कर सकते हैं।

## त्वरित उत्तर
- **What does the page saving callback do?** यह प्रत्येक रेंडर किए गए पृष्ठ को एक अलग स्ट्रीम में कैप्चर करता है ताकि आप उन्हें व्यक्तिगत रूप से संभाल सकें।  
- **Which format can I export to?** `ImageSaveOptions` द्वारा समर्थित कोई भी फ़ॉर्मेट, जैसे PNG, JPEG, PDF।  
- **Do I need a license?** उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **Can I use this with .NET Core?** हाँ, Aspose.Tasks पूरी तरह से .NET Core और .NET 5/6+ को सपोर्ट करता है।  
- **Is the callback thread‑safe?** कॉलबैक उसी थ्रेड पर चलता है जो रेंडरिंग करता है, इसलिए सामान्य थ्रेड‑सेफ़्टी नियम लागू होते हैं।

## **implement page saving callback** क्या है?
The **implement page saving callback** पैटर्न आपको Aspose.Tasks की सेविंग पाइपलाइन में कस्टम लॉजिक जोड़ने की अनुमति देता है। फ़ाइल में सीधे लिखने के बजाय, आपको प्रत्येक पृष्ठ के लिए एक `Stream` ऑब्जेक्ट मिलता है, जिससे आप इसे मेमोरी में स्टोर कर सकते हैं, क्लाउड स्टोरेज में अपलोड कर सकते हैं, या अतिरिक्त प्रोसेसिंग लागू कर सकते हैं।

## कॉलबैक के साथ प्रोजेक्ट को PNG के रूप में क्यों एक्सपोर्ट करें?
प्रोजेक्ट को PNG के रूप में एक्सपोर्ट करने से आपको प्रत्येक Gantt चार्ट पृष्ठ की रास्टर इमेज मिलती है, जो रिपोर्ट, ईमेल या वेब पेज में एम्बेड करने के लिए आदर्श है। कॉलबैक का उपयोग करने से आप प्रत्येक पृष्ठ को अलग `MemoryStream` में रख सकते हैं बिना डिस्क पर अस्थायी फ़ाइलें बनाए।

## पूर्वापेक्षाएँ

1. **C# knowledge** – क्लासेज़, इंटरफ़ेसेज़, और स्ट्रीम्स की बुनियादी परिचितता।  
2. **Aspose.Tasks for .NET** – [here](https://releases.aspose.com/tasks/net/) से डाउनलोड और इंस्टॉल करें।  
3. **IDE** – Visual Studio, Rider, या कोई भी .NET‑compatible एडिटर।

## नेमस्पेस इम्पोर्ट करें

शुरू करने के लिए, आवश्यक नेमस्पेस इम्पोर्ट करें:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## चरण 1: एक Project ऑब्जेक्ट बनाएं

एक मौजूदा MPP फ़ाइल को `Project` इंस्टेंस में लोड करें:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## चरण 2: Image Save Options कॉन्फ़िगर करें

`ImageSaveOptions` को PNG आउटपुट के लिए सेट करें और कस्टम कॉलबैक अटैच करें:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tip:** `RenderToSinglePage = false` सेट करने से प्रत्येक Gantt चार्ट पृष्ठ अलग‑अलग रेंडर होता है, जो कॉलबैक को अलग-अलग स्ट्रीम प्राप्त करने के लिए आवश्यक है।

## चरण 3: कॉलबैक के साथ प्रोजेक्ट सहेजें

`Save` मेथड को कॉल करें, `Stream.Null` पास करें क्योंकि वास्तविक स्ट्रीम्स कॉलबैक द्वारा प्रदान किए जाते हैं:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## चरण 4: सहेजे गए पेज स्ट्रीम्स को प्रोसेस करें

सेव ऑपरेशन पूरा होने के बाद, कॉलबैक के पास `MemoryStream` ऑब्जेक्ट्स का एक संग्रह होता है—प्रति पृष्ठ एक। अब आप उन पर इटरेट कर सकते हैं:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## चरण 5: कस्टम पेज सहेजने का कॉलबैक लागू करें

`IPageSavingCallback` को इम्प्लीमेंट करने वाली एक sealed क्लास बनाएं। यह क्लास प्रत्येक पृष्ठ के स्ट्रीम को कैप्चर करती है और बाद में उपयोग के लिए एक लिस्ट में स्टोर करती है।

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## सामान्य समस्याएँ और ट्रबलशूटिंग

| समस्या | कारण | समाधान |
|-------|--------|----------|
| **कोई पृष्ठ नहीं लौटाए गए** | `RenderToSinglePage` को `true` रहने दिया गया। | `RenderToSinglePage = false` सेट करें ताकि अलग‑अलग पृष्ठ उत्पन्न हों। |
| **स्ट्रीम्स खाली हैं** | `KeepStreamOpen` को `true` सेट किया गया है बिना बाद में डिस्पोज़ किए। | इसे `false` (डिफ़ॉल्ट) रखें और कॉलबैक को स्ट्रीम्स को स्वचालित रूप से बंद करने दें। |
| **आउट‑ऑफ़‑मेमोरी त्रुटियां** | बहुत बड़े प्रोजेक्ट्स कई हाई‑रेज़ोल्यूशन PNG बनाते हैं। | स्ट्रीम्स को एक‑एक करके प्रोसेस करें या VM मेमोरी लिमिट बढ़ाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

**Q1: What is a page saving callback in Aspose.Tasks?**  
A: एक पेज सहेजने का कॉलबैक आपको बहु‑पृष्ठ दस्तावेज़ के प्रत्येक पृष्ठ की सेविंग प्रक्रिया को इंटरसेप्ट करने की अनुमति देता है, जिससे उस पृष्ठ के लिए एक कस्टम `Stream` प्रदान किया जाता है।

**Q2: क्या मैं इस कॉलबैक का उपयोग करके पृष्ठों को सहेजने के लिए विभिन्न फ़ॉर्मेट्स का उपयोग कर सकता हूँ?**  
A: हाँ। `SaveFileFormat` बदलकर आप PNG, JPEG, PDF, SVG आदि में एक्सपोर्ट कर सकते हैं।

**Q3: क्या Aspose.Tasks .NET Core के साथ संगत है?**  
A: बिल्कुल। Aspose.Tasks .NET Core, .NET 5, और .NET 6 को सपोर्ट करता है।

**Q4: पेज सहेजने की प्रक्रिया के दौरान त्रुटियों को कैसे संभालें?**  
A: कॉलबैक लॉजिक को try/catch ब्लॉक्स में रैप करें और एक्सेप्शन लॉग करें। `OnFinish` मेथड अंतिम क्लीनअप के लिए एक अच्छा स्थान है।

**Q5: मैं Aspose.Tasks के लिए अधिक संसाधन और समर्थन कहाँ पा सकता हूँ?**  
A: आप सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं, दस्तावेज़ीकरण [here](https://reference.aspose.com/tasks/net/) से एक्सेस कर सकते हैं, या अतिरिक्त फीचर्स और लाइसेंसिंग विकल्पों के लिए [Aspose.Tasks website](https://purchase.aspose.com/buy) देख सकते हैं।

---

**अंतिम अपडेट:** 2026-03-16  
**परीक्षण किया गया:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}