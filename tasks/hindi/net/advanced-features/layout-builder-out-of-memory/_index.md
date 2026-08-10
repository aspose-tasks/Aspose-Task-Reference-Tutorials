---
date: 2026-03-24
description: .NET में Aspose.Tasks Layout Builder का उपयोग करके मेमोरी‑ऑफ़‑हैंडलिंग
  और प्रोजेक्ट इमेज को कैसे सहेजें, सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण गाइड।
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks लेआउट बिल्डर (C#) के साथ मेमोरी समाप्ति को संभालना
url: /hi/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Layout Builder के साथ मेमोरी समाप्ति प्रबंधन

## परिचय

मेमोरी समाप्ति प्रबंधन बड़े प्रोजेक्ट फ़ाइलों के साथ काम करने वाले विश्वसनीय .NET एप्लिकेशनों को बनाने का एक महत्वपूर्ण हिस्सा है। जब आप Aspose.Tasks Layout Builder के साथ विज़ुअलाइज़ेशन जनरेट करते हैं, तो आप जल्दी ही मेमोरी‑संबंधी अपवादों का सामना कर सकते हैं, विशेष रूप से जटिल Gantt चार्ट पर। इस ट्यूटोरियल में हम आपको **मेमोरी अपवादों को संभालना**, **Gantt व्यू को कस्टमाइज़ करना**, और **प्रोजेक्ट इमेज को सुरक्षित रूप से सेव करना** सिखाएंगे, ताकि आपका एप्लिकेशन बड़े शेड्यूल के साथ भी प्रतिक्रियाशील बना रहे।

## त्वरित उत्तर
- **Out of memory handling क्या है?** बड़े डेटा को प्रोसेस करते समय मेमोरी उपयोग को प्रबंधित करना और `OutOfMemoryException`‑प्रकार की त्रुटियों को पकड़ना।
- **कौन सा API मदद करता है?** .NET के लिए Aspose.Tasks Layout Builder।
- **सामान्य परिदृश्य?** उच्च‑रिज़ॉल्यूशन Gantt चार्ट को PNG में रेंडर करना।
- **मुख्य पूर्वापेक्षा?** Aspose.Tasks स्थापित के साथ .NET (Framework 4.5+ या .NET 6)।
- **त्रुटियों को कैसे पकड़ें?** `ApsLayoutBuilderOutOfMemoryException` और संबंधित अपवादों के लिए `try…catch` ब्लॉक्स का उपयोग करें।

## पूर्वापेक्षाएँ

कोड में जाने से पहले, सुनिश्चित करें कि आपके पास है:

1. **C# बेसिक्स** – आपको मानक C# सिंटैक्स में सहज होना चाहिए।
2. **Aspose.Tasks for .NET** स्थापित। यदि आपने अभी तक इसे नहीं जोड़ा है, तो इसे [here](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।
3. **एक IDE** जैसे Visual Studio (या C# एक्सटेंशन के साथ VS Code) नमूना को संकलित और चलाने के लिए।

## नेमस्पेस आयात करें

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: प्रोजेक्ट लोड करें

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

यह पंक्ति **Blank2010.mpp** को एक `Project` इंस्टेंस में लोड करती है, जिससे यह विज़ुअलाइज़ेशन के लिए तैयार हो जाता है।

### स्टेप 2: Gantt चार्ट व्यू को कस्टमाइज़ करें

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

यहाँ हम मध्य और निचले टाइमस्केल टियर्स को समायोजित करके **Gantt व्यू को कस्टमाइज़** करते हैं। इन टियर्स को बदलने से एक साथ रेंडर किए जाने वाले डेटा की मात्रा कम होती है, जिससे मेमोरी दबाव कम करने में मदद मिलती है।

### स्टेप 3: इमेज सेव ऑप्शन्स कॉन्फ़िगर करें

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` Aspose.Tasks को बताता है कि चार्ट को कैसे रेंडर किया जाए। हम आउटपुट फ़ॉर्मेट के रूप में PNG चुनते हैं और टाइमस्केल को अभी कस्टमाइज़ किए गए व्यू से बाइंड करते हैं।

### स्टेप 4: प्रोजेक्ट को इमेज के रूप में सेव करें

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

`Save` कॉल **प्रोजेक्ट इमेज को** ऊपर परिभाषित विकल्पों का उपयोग करके सेव करता है। यदि प्रोजेक्ट बहुत बड़ा है, तो यह वह बिंदु है जहाँ मेमोरी‑समाप्ति की स्थिति सबसे अधिक संभावना से उत्पन्न होती है।

### स्टेप 5: अपवादों को संभालें

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

`ApsLayoutBuilderOutOfMemoryException` को पकड़कर आप **मेमोरी अपवाद** को सुगमता से संभालते हैं, जिससे एप्लिकेशन को क्रैश किए बिना स्पष्ट संदेश मिलता है। दूसरा कैच बिटमैप आकार की समस्याओं को संभालता है, जो बड़े चार्ट रेंडर करते समय भी उत्पन्न हो सकती हैं।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|----------------|-----|
| **OutOfMemoryException** | बहुत उच्च‑रिज़ॉल्यूशन इमेज को रेंडर करने से प्रक्रिया द्वारा आवंटित RAM से अधिक मेमोरी उपयोग होती है। | इमेज के आयाम कम करें, टाइमस्केल टियर्स को सरल बनाएं, या चार्ट को कई इमेज में विभाजित करें। |
| **BitmapInvalidSizeException** | अनुरोधित बिटमैप आकार प्लेटफ़ॉर्म की अधिकतम सीमा से अधिक है। | `ImageSaveOptions` में चौड़ाई/ऊँचाई सीमित करें या सेगमेंट में रेंडर करें। |
| **Slow performance** | बड़े प्रोजेक्ट फ़ाइलों को प्रोसेस करने में बहुत समय लगता है। | रेंडर करने से पहले `project.Set(Prj.SaveToCache, true)` सक्षम करें, या बैकग्राउंड थ्रेड का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: Aspose.Tasks for .NET क्या है?

A1: Aspose.Tasks for .NET एक शक्तिशाली API है जो डेवलपर्स को .NET एप्लिकेशन्स में प्रोग्रामेटिक रूप से Microsoft Project फ़ाइलों को संशोधित करने की अनुमति देता है।

### प्रश्न 2: Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?

A2: आप Aspose.Tasks के लिए अस्थायी लाइसेंस [this link](https://purchase.aspose.com/temporary-license/) पर जाकर प्राप्त कर सकते हैं।

### प्रश्न 3: क्या Aspose.Tasks बड़े प्रोजेक्ट फ़ाइलों को संभालने के लिए उपयुक्त है?

A3: हाँ, Aspose.Tasks बड़े प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभालने के लिए फीचर्स और ऑप्टिमाइज़ेशन प्रदान करता है, लेकिन डेवलपर्स को अभी भी मेमोरी प्रबंधन रणनीतियों पर विचार करना चाहिए।

### प्रश्न 4: क्या मैं Aspose.Tasks का उपयोग करके Gantt चार्ट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?

A4: बिल्कुल! Aspose.Tasks आपके आवश्यकताओं के अनुसार Gantt चार्ट की उपस्थिति और लेआउट को कस्टमाइज़ करने की व्यापक क्षमताएँ प्रदान करता है।

### प्रश्न 5: Aspose.Tasks के लिए अधिक मदद और समर्थन कहाँ मिल सकता है?

A5: आप अधिक मदद और समर्थन, साथ ही समुदाय के साथ जुड़ाव, [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर पा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: प्रोजेक्ट इमेज को सेव करते समय मेमोरी उपयोग कैसे कम करूँ?**  
उत्तर: इमेज रेज़ॉल्यूशन कम करें, टाइमस्केल रेंज सीमित करें, या चार्ट को कई छोटे सेगमेंट में सेव करें।

**प्रश्न: क्या इमेज को सीधे वेब रिस्पॉन्स में स्ट्रीम करना संभव है?**  
उत्तर: हाँ, आप `project.Save(stream, options)` का उपयोग करके स्ट्रीम को HTTP रिस्पॉन्स में लिख सकते हैं।

**प्रश्न: क्या Aspose.Tasks .NET Core और .NET 5/6 को सपोर्ट करता है?**  
उत्तर: यह लाइब्रेरी .NET Core, .NET 5, और .NET 6 के साथ पूरी तरह संगत है।

**प्रश्न: ऑप्टिमाइज़ेशन के बाद भी यदि मेमोरी‑समाप्ति त्रुटि आती है तो क्या करें?**  
उत्तर: अधिक RAM वाले मशीन पर प्रोजेक्ट प्रोसेस करने पर विचार करें या रेंडरिंग को बैकग्राउंड सर्विस पर ऑफ‑लोड करें।

**प्रश्न: क्या मैं Gantt चार्ट को PNG के अलावा अन्य फ़ॉर्मेट में एक्सपोर्ट कर सकता हूँ?**  
उत्तर: हाँ, `ImageSaveOptions` PNG के अलावा JPEG, BMP, और TIFF को भी सपोर्ट करता है।

---

**अंतिम अपडेट:** 2026-03-24  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}