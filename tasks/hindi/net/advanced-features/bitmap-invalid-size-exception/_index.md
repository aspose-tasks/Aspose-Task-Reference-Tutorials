---
date: 2026-03-21
description: Aspose.Tasks for .NET में प्रोजेक्ट को इमेज के रूप में सहेजते समय इमेज
  निर्यात करना और BitmapInvalidSizeException को संभालना सीखें। इसमें प्रोजेक्ट को
  इमेज के रूप में सहेजने और प्रोजेक्ट को PNG में निर्यात करने के चरण शामिल हैं।
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: इमेज को निर्यात कैसे करें और अमान्य आकार अपवाद को संभालें
url: /hi/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# इमेज निर्यात कैसे करें – Aspose.Tasks में Bitmap के लिए Invalid Size Exception को संभालना

इस ट्यूटोरियल में आप **इमेज निर्यात करने** का तरीका सीखेंगे Microsoft Project फ़ाइल से Aspose.Tasks for .NET का उपयोग करके और सबसे महत्वपूर्ण बात, प्रक्रिया के दौरान उत्पन्न हो सकने वाले `BitmapInvalidSizeException` को कैसे पकड़ें। प्रोजेक्ट को इमेज के रूप में निर्यात करना रिपोर्टिंग डैशबोर्ड, दस्तावेज़ीकरण, या शेड्यूल का विज़ुअल स्नैपशॉट साझा करने के लिए आम आवश्यकता है। इस गाइड के अंत तक आप **प्रोजेक्ट को इमेज के रूप में सुरक्षित** रूप से कर पाएँगे और **प्रोजेक्ट को PNG** फ़ॉर्मेट में निर्यात भी बिना किसी अनपेक्षित क्रैश के कर सकेंगे।

## त्वरित उत्तर
- **इमेज निर्यात करते समय कौन सा एक्सेप्शन हो सकता है?** `BitmapInvalidSizeException`  
- **उदाहरण में कौन सा फ़ॉर्मेट उपयोग किया गया है?** PNG (`SaveFileFormat.Png`)  
- **क्या मुझे विशेष लाइसेंस की आवश्यकता है?** प्रोडक्शन उपयोग के लिए वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं टाइमस्केल बदल सकता हूँ?** हाँ – आप टाइमस्केल यूनिट (मिनट, घंटे, दिन आदि) सेट कर सकते हैं।  
- **क्या कोड .NET Core के साथ संगत है?** बिल्कुल – वही API .NET Framework और .NET Core दोनों पर काम करती है।

## BitmapInvalidSizeException क्या है?
`BitmapInvalidSizeException` तब फेंका जाता है जब इमेज के लिए गणना किए गए बिटमैप आयाम समर्थित रेंज से बाहर होते हैं (जैसे, चौड़ाई या ऊँचाई शून्य हो या आंतरिक सीमाओं से अधिक हो)। यह आमतौर पर तब होता है जब टाइमस्केल या व्यू सेटिंग्स ऐसी इमेज बनाते हैं जो बहुत बड़ी या बहुत छोटी हो।

## प्रोजेक्ट को इमेज के रूप में निर्यात क्यों करें?
- **विज़ुअल रिपोर्टिंग** – PDF, Word दस्तावेज़ या वेब पेज में गैंट चार्ट एम्बेड करें।  
- **क्रॉस‑प्लेटफ़ॉर्म शेयरिंग** – PNG फ़ाइलें किसी भी डिवाइस पर देखी जा सकती हैं बिना Microsoft Project की आवश्यकता के।  
- **परफ़ॉर्मेंस** – पूर्ण प्रोजेक्ट फ़ाइलों की तुलना में इमेज हल्की होती हैं, जिससे तेज़ प्रीव्यू मिलते हैं।

## पूर्वापेक्षाएँ
1. C# और .NET विकास का बुनियादी ज्ञान।  
2. Aspose.Tasks for .NET स्थापित (NuGet पैकेज `Aspose.Tasks`)।  
3. एक सैंपल Microsoft Project फ़ाइल (जैसे, `Blank2010.mpp`)।

## नेमस्पेस इम्पोर्ट करें
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## चरण‑दर‑चरण गाइड

### चरण 1: प्रोजेक्ट इनिशियलाइज़ करें और व्यू चुनें
पहले, एक `Project` इंस्टेंस बनाएं और वह व्यू चुनें जिसे आप रेंडर करना चाहते हैं (यहाँ हम पहले गैंट चार्ट व्यू का उपयोग करते हैं)।

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### चरण 2: इमेज सेव ऑप्शन कॉन्फ़िगर करें (प्रोजेक्ट को PNG में निर्यात)
इच्छित इमेज फ़ॉर्मेट सेट करें और Aspose.Tasks को व्यू में परिभाषित टाइमस्केल उपयोग करने को बताएं।

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### चरण 3: टाइमस्केल यूनिट समायोजित करें (इमेज आकार नियंत्रित करें)
टाइमस्केल बदलने से बिटमैप आयाम प्रभावित होते हैं। इस उदाहरण में हम **मिनट** उपयोग करते हैं ताकि इमेज आकार प्रबंधनीय रहे।

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### चरण 4: प्रोजेक्ट को इमेज के रूप में सेव करने का प्रयास करें
यह लाइन वास्तविक **प्रोजेक्ट को इमेज के रूप में सेव** ऑपरेशन करती है।

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### चरण 5: BitmapInvalidSizeException को पकड़ें और हैंडल करें
सेव कॉल को `try / catch` ब्लॉक में रैप करें ताकि यदि बिटमैप आकार अमान्य हो तो आपका एप्लिकेशन सुगमता से प्रतिक्रिया दे सके।

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|----------|
| टाइमस्केल समायोजित करने के बाद भी एक्सेप्शन फेंका जाता है | टाइमस्केल अभी भी बहुत बड़े बिटमैप का परिणाम देता है | `view.MiddleTimescaleTier.Count` घटाएँ या अधिक मोटा `TimescaleUnit` (जैसे, Hours) चुनें। |
| आउटपुट फ़ाइल खाली है | फ़ाइल पाथ गलत है या लिखने की अनुमति नहीं है | सुनिश्चित करें कि `DataDir` लिखने योग्य फ़ोल्डर की ओर इशारा कर रहा है और फ़ाइलनाम का अंत `.png` है यदि आप फ़ॉर्मेट बदलते हैं। |
| इमेज क्वालिटी खराब है | डिफ़ॉल्ट DPI कम हो सकता है | `options.DpiX` और `options.DpiY` को उच्च मान (जैसे, 300) पर सेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: Aspose.Tasks में BitmapInvalidSizeException का कारण क्या है?**  
**उत्तर:** यह तब उत्पन्न होता है जब गणना किए गए बिटमैप आयाम अमान्य होते हैं—आमतौर पर क्योंकि टाइमस्केल ऐसी इमेज बनाता है जो बहुत बड़ी या शून्य चौड़ाई/ऊँचाई वाली हो।

**प्रश्न: क्या इमेज निर्यात करते समय टाइमस्केल को कस्टमाइज़ किया जा सकता है?**  
**उत्तर:** हाँ। आप `view.MiddleTimescaleTier.Unit` और `Count` को अपनी आवश्यकता अनुसार बदल सकते हैं, जैसा कि ट्यूटोरियल में दिखाया गया है।

**प्रश्न: क्या PNG के अलावा Aspose.Tasks अन्य इमेज फ़ॉर्मेट सपोर्ट करता है?**  
**उत्तर:** बिल्कुल। `SaveFileFormat` में JPEG, BMP, GIF, और TIFF भी शामिल हैं। बस `ImageSaveOptions` में एन्‍युम मान बदल दें।

**प्रश्न: प्रोडक्शन वातावरण में इमेज निर्यात करने के लिए लाइसेंस आवश्यक है क्या?**  
**उत्तर:** हाँ। लाइब्रेरी एवाल्युएशन मोड में काम करती है, लेकिन एक व्यावसायिक लाइसेंस एवाल्युएशन प्रतिबंधों को हटाता है और पूर्ण सपोर्ट प्रदान करता है।

**प्रश्न: निर्यात किए गए PNG की क्वालिटी कैसे बढ़ाई जा सकती है?**  
**उत्तर:** DPI सेटिंग्स (`options.DpiX` और `options.DpiY`) को बढ़ाएँ या बड़े बिटमैप के लिए व्यू का टाइमस्केल समायोजित करें।

## निष्कर्ष
ऊपर बताए गए चरणों का पालन करके आप अब **इमेज निर्यात करना** जानते हैं, **प्रोजेक्ट को इमेज के रूप में सुरक्षित** करना जानते हैं, और `BitmapInvalidSizeException` को सुगमता से हैंडल करना भी जानते हैं। ये तकनीकें आपके रिपोर्टिंग पाइपलाइन को अधिक मजबूत बनाती हैं और विभिन्न प्रोजेक्ट आकार और टाइमस्केल के साथ विज़ुअल निर्यात को विश्वसनीय बनाती हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-21  
**टेस्ट किया गया संस्करण:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose