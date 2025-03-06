---
title: Aspose.Tasks के साथ मास्टर एमएस प्रोजेक्ट दरें
linktitle: Aspose.Tasks में दरों का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों में दरें प्रबंधित करना सीखें। प्रभावी संसाधन प्रबंधन के लिए चरण-दर-चरण ट्यूटोरियल।
weight: 11
url: /hi/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ मास्टर एमएस प्रोजेक्ट दरें

## परिचय
.NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में दरें प्रबंधित करने पर हमारे ट्यूटोरियल में आपका स्वागत है! इस गाइड में, हम आपको Aspose.Tasks का उपयोग करके आपकी MS प्रोजेक्ट फ़ाइलों में दरों के साथ काम करने की प्रक्रिया के बारे में बताएंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी-अभी .NET विकास के साथ शुरुआत कर रहे हों, यह ट्यूटोरियल आपको अपनी परियोजनाओं के भीतर दरों को प्रभावी ढंग से संभालने के लिए चरण-दर-चरण निर्देश प्रदान करेगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. विजुअल स्टूडियो स्थापित
सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है। यदि आपने पहले से इसे डाउनलोड नहीं किया है तो आप इसे वेबसाइट से डाउनलोड कर सकते हैं।
### 2. .NET के लिए Aspose.Tasks
 .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/tasks/net/).
### 3. C# और .NET का बुनियादी ज्ञान
इस ट्यूटोरियल में दिए गए कोड उदाहरणों को बेहतर ढंग से समझने के लिए C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क की बुनियादी बातों से खुद को परिचित करें।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:
## चरण 1: एक एमएस प्रोजेक्ट फ़ाइल लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 यहां, हम एक नया बनाते हैं`Project` मौजूदा एमएस प्रोजेक्ट फ़ाइल को लोड करके ऑब्जेक्ट करें।
## चरण 2: एक संसाधन जोड़ें और कार्य और दरें निर्धारित करें
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
हम प्रोजेक्ट में एक नया संसाधन जोड़ते हैं, उसका प्रकार कार्य, कार्य राशि और मानक दर के रूप में निर्धारित करते हैं।
## चरण 3: संसाधन में दरें जोड़ें
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
हम प्रारंभ और समाप्ति तिथियों, मानक दर और दर प्रारूप को निर्दिष्ट करते हुए संसाधन में दरें जोड़ते हैं।
## चरण 4: दरों की जानकारी प्रिंट करें
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
यह चरण संसाधन से जुड़ी दरों के बारे में जानकारी प्रिंट करता है।
## चरण 5: दर अपडेट करें
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
हम एक विशिष्ट दर की अंतिम तिथि अपडेट करते हैं।
## चरण 6: दरें हटाएँ
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
यह चरण एक विशिष्ट प्रकार की सभी दरें हटा देता है.
## चरण 7: शेष दरों पर पुनरावृति करें
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
अंत में, हम हटाने के बाद शेष दरों पर पुनरावृति करते हैं।
## निष्कर्ष
अंत में, इस ट्यूटोरियल ने आपको .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों में दरों के प्रबंधन पर एक व्यापक मार्गदर्शिका प्रदान की। इस ट्यूटोरियल में उल्लिखित चरण-दर-चरण निर्देशों का पालन करके, आप सटीक संसाधन प्रबंधन सुनिश्चित करते हुए, अपनी परियोजनाओं के भीतर दरों को कुशलतापूर्वक संभाल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोजेक्ट प्रबंधन सॉफ़्टवेयर के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, .NET के लिए Aspose.Tasks एमएस प्रोजेक्ट, प्रिमावेरा और अन्य सहित विभिन्न परियोजना प्रबंधन सॉफ्टवेयर के साथ एकीकरण का समर्थन करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: बिल्कुल, .NET के लिए Aspose.Tasks लचीलापन और अनुकूलता सुनिश्चित करते हुए विभिन्न संस्करणों की MS प्रोजेक्ट फ़ाइलों के साथ काम करने का समर्थन करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks दस्तावेज़ीकरण और समर्थन प्रदान करता है?
 उत्तर: हां, आप Aspose.Tasks पर व्यापक दस्तावेज़ीकरण और समर्थन मंचों तक पहुंच पा सकते हैं[वेबसाइट](https://reference.aspose.com/tasks/net/).
### प्रश्न: क्या मैं खरीदने से पहले .NET के लिए Aspose.Tasks आज़मा सकता हूँ?
उत्तर: हाँ, आप अपनी आवश्यकताओं के साथ इसकी विशेषताओं और अनुकूलता का मूल्यांकन करने के लिए .NET के लिए Aspose.Tasks के निःशुल्क परीक्षण का लाभ उठा सकते हैं।
### प्रश्न: मैं .NET के लिए Aspose.Tasks का लाइसेंस कैसे खरीद सकता हूं?
 उ: आप .NET के लिए Aspose.Tasks के लिए लाइसेंस खरीद सकते हैं[वेबसाइट](https://purchase.aspose.com/temporary-license/)जो आपकी आवश्यकताओं के अनुरूप लचीले लाइसेंसिंग विकल्प प्रदान करता है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
