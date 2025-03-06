---
title: Aspose.Tasks में सहज एमएस प्रोजेक्ट आवर्ती अंतराल
linktitle: Aspose.Tasks में आवर्ती अंतरालों का प्रबंधन
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में आवर्ती अंतरालों को आसानी से प्रबंधित करने का तरीका जानें।
weight: 12
url: /hi/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में सहज एमएस प्रोजेक्ट आवर्ती अंतराल

## परिचय
क्या आप .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइलों में आवर्ती अंतरालों को कुशलतापूर्वक प्रबंधित करना चाहते हैं? यह व्यापक ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आप अपनी परियोजनाओं में आवर्ती अंतरालों को आसानी से संभाल सकते हैं। ट्यूटोरियल में जाने से पहले, आइए कुछ आवश्यक शर्तों पर गौर करें ताकि यह सुनिश्चित हो सके कि आप आरंभ करने के लिए तैयार हैं।
## आवश्यक शर्तें
इस ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. C# प्रोग्रामिंग का ज्ञान: C# प्रोग्रामिंग भाषा और उसके सिंटैक्स की बुनियादी समझ आवश्यक है।
2. विजुअल स्टूडियो स्थापित: सुनिश्चित करें कि .NET अनुप्रयोगों को कोडिंग और संकलित करने के लिए आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
3. .NET लाइब्रेरी के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).

## नामस्थान आयात करें
.NET लाइब्रेरी के लिए Aspose.Tasks द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करके शुरुआत करें।
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें और उन्हें विस्तार से समझाएं।
## चरण 1: प्रोजेक्ट ऑब्जेक्ट आरंभ करें:
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 यहां, हम इसका एक नया उदाहरण प्रारंभ करते हैं`Project` Microsoft प्रोजेक्ट फ़ाइल के लिए पथ प्रदान करके क्लास।
## चरण 2: स्थिति तिथि निर्धारित करें:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
यह चरण प्रोजेक्ट की स्थिति तिथि को उसकी आरंभ तिथि पर सेट करता है।
## चरण 3: गैंट चार्ट दृश्य तक पहुंचें:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
हम परियोजना के गैंट चार्ट दृश्य तक पहुंचते हैं।
## चरण 4: प्रगति पंक्ति पढ़ें:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
यह चरण गैंट चार्ट दृश्य से प्रगति रेखाओं के लिए आवर्ती अंतराल को पुनः प्राप्त करता है।
## चरण 5: अंतराल सूचना प्रदर्शित करें:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
यहां, हम अंतराल, साप्ताहिक सप्ताह संख्या और साप्ताहिक दिनों के बारे में जानकारी प्रदर्शित करते हैं।
## चरण 6: आवर्ती अंतराल को फिर से परिभाषित करें:
```csharp
var newInterval = new RecurringInterval();
```
 हम इसका एक नया उदाहरण बनाते हैं`RecurringInterval` आवर्ती अंतराल को फिर से परिभाषित करने के लिए।
## चरण 7: मासिक प्रगति रेखाएँ निर्धारित करें:
```csharp
// दिन के अनुसार मासिक प्रगति रेखाएँ निर्धारित करें।
interval.MonthlyDay = true;
// मासिक प्रगति पंक्तियों की दिन संख्या निर्धारित करें।
interval.MonthlyDayDayNumber = 1;
// मासिक प्रगति पंक्तियों की माह संख्या निर्धारित करें।
interval.MonthlyDayMonthNumber = 1;
// पहले या अंतिम पूर्वनिर्धारित दिन के अनुसार प्रगति रेखाएँ निर्धारित करें।
interval.MonthlyFirstLast = true;
// मासिक प्रगति पंक्तियों के पहले या अंतिम दिन का प्रकार निर्धारित करें।
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// प्रगति पंक्तियों की माह संख्या निर्धारित करें।
interval.MonthlyFirstLastMonthNumber = 1;
```
ये चरण निर्दिष्ट मापदंडों के अनुसार मासिक प्रगति लाइनों को कॉन्फ़िगर करते हैं।
## चरण 8: प्रगति पंक्तियाँ अद्यतन करें:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
हम गैंट चार्ट दृश्य में प्रगति रेखाओं को नए परिभाषित आवर्ती अंतराल के साथ अद्यतन करते हैं।
## चरण 9: प्रोजेक्ट को पीडीएफ के रूप में सहेजें:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
अंत में, हम प्रोजेक्ट को अद्यतन आवर्ती अंतराल के साथ पीडीएफ फ़ाइल के रूप में सहेजते हैं।

## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइलों में आवर्ती अंतरालों को प्रबंधित करना लाइब्रेरी द्वारा प्रदान की गई व्यापक कार्यक्षमताओं के साथ सरल बना दिया गया है। इस ट्यूटोरियल में उल्लिखित चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी परियोजनाओं में आवर्ती अंतरालों को कुशलतापूर्वक संभाल सकते हैं, उत्पादकता और संगठन को बढ़ा सकते हैं।
### अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.Tasks का उपयोग किसी भी .NET समर्थित भाषा जैसे C# और VB.NET के साथ किया जा सकता है।
### क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से नि:शुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप Aspose.Tasks फोरम से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### क्या मैं .NET के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मुझे .NET के लिए Aspose.Tasks के लिए संपूर्ण दस्तावेज़ कहां मिल सकते हैं?
 संपूर्ण दस्तावेज़ पाया जा सकता है[यहाँ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
