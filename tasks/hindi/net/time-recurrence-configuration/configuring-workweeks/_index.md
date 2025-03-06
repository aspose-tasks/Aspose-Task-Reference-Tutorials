---
title: Aspose.Tasks में वर्कवीक कॉन्फ़िगरेशन में महारत हासिल करना
linktitle: Aspose.Tasks में कार्य सप्ताह कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में कार्य सप्ताहों को सहजता से कॉन्फ़िगर करने का तरीका जानें। हमारे चरण-दर-चरण मार्गदर्शिका के साथ प्रोजेक्ट शेड्यूलिंग और संसाधन प्रबंधन को बेहतर बनाएं।
weight: 16
url: /hi/net/time-recurrence-configuration/configuring-workweeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में वर्कवीक कॉन्फ़िगरेशन में महारत हासिल करना

## परिचय
.NET के लिए Aspose.Tasks में कार्य सप्ताह कॉन्फ़िगर करने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है। परियोजना नियोजन और शेड्यूलिंग के लिए कार्य सप्ताहों का कुशलतापूर्वक प्रबंधन करना महत्वपूर्ण है। Aspose.Tasks इस प्रक्रिया को सरल बनाता है, जिससे आप अपने प्रोजेक्ट की आवश्यकताओं के अनुसार कार्य सप्ताहों को अनुकूलित कर सकते हैं। इस ट्यूटोरियल में, हम आपको वर्कवीक को सहजता से कॉन्फ़िगर करने के चरणों के बारे में बताएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  Aspose.Tasks लाइब्रेरी: सुनिश्चित करें कि आपके .NET प्रोजेक्ट में Aspose.Tasks लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.कार्य वेबसाइट](https://releases.aspose.com/tasks/net/).
2. .NET वातावरण: सुनिश्चित करें कि आप .NET वातावरण में काम कर रहे हैं, और आपको C# प्रोग्रामिंग की बुनियादी समझ है।
## नामस्थान आयात करें
आरंभ करने के लिए, अपने प्रोजेक्ट में आवश्यक नामस्थान शामिल करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: अपना प्रोजेक्ट सेट करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project();
```
## चरण 2: एक मानक कैलेंडर बनाएं
```csharp
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## चरण 3: एक कस्टम कार्य सप्ताह परिभाषित करें
```csharp
var item = new WorkWeek();
item.Name = "My Work Week";
item.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
item.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## चरण 4: कार्य दिवस निर्दिष्ट करें
```csharp
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
item.WeekDays.Add(new WeekDay(DayType.Saturday));
item.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(item);
```
## चरण 5: कार्य सप्ताह विवरण प्रदर्शित करें
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    // कार्य सप्ताह विवरण प्रदर्शित करें
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    Console.WriteLine();
    // प्रत्येक दिन के लिए विशेष कार्य समय प्रदर्शित करें
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        // कार्य समय प्रदर्शित करें
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
इन चरणों का पालन करके, आप अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाते हुए, Aspose.Tasks में कार्य सप्ताहों को आसानी से कॉन्फ़िगर कर सकते हैं।
## निष्कर्ष
अंत में, कार्य सप्ताहों का प्रबंधन परियोजना नियोजन का एक मूलभूत पहलू है, और Aspose.Tasks अपनी शक्तिशाली विशेषताओं के साथ इस प्रक्रिया को सरल बनाता है। अपने प्रोजेक्ट की आवश्यकताओं के अनुसार कार्य सप्ताहों को अनुकूलित करके, आप कुशल संसाधन उपयोग और बेहतर प्रोजेक्ट शेड्यूलिंग सुनिश्चित कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं एक ही प्रोजेक्ट में एकाधिक कार्य सप्ताह कॉन्फ़िगर कर सकता हूँ?
हां, आप Aspose.Tasks का उपयोग करके एक ही प्रोजेक्ट के भीतर एकाधिक कार्य सप्ताह कॉन्फ़िगर कर सकते हैं।
### क्या विशिष्ट दिनों के लिए अलग-अलग कार्य घंटे निर्धारित करना संभव है?
बिल्कुल। Aspose.Tasks आपको कार्य सप्ताह के भीतर प्रत्येक दिन के लिए अद्वितीय कार्य समय परिभाषित करने की अनुमति देता है।
### क्या मैं परियोजनाओं के बीच कार्य सप्ताहों का आयात/निर्यात कर सकता हूँ?
जबकि Aspose.Tasks मजबूत आयात/निर्यात क्षमताएं प्रदान करता है, कार्य सप्ताह आमतौर पर परियोजना-विशिष्ट होते हैं और सीधे हस्तांतरणीय नहीं हो सकते हैं।
### क्या किसी प्रोजेक्ट में मेरे द्वारा बनाए जा सकने वाले कार्य-सप्ताहों की संख्या की कोई सीमा है?
वर्तमान संस्करण के अनुसार, किसी प्रोजेक्ट में आपके द्वारा कॉन्फ़िगर किए जा सकने वाले कार्य सप्ताहों की संख्या पर कोई पूर्वनिर्धारित सीमा नहीं है।
### क्या सामान्य कार्य सप्ताहों के लिए कोई अंतर्निहित टेम्पलेट हैं?
हां, Aspose.Tasks में एक मानक कैलेंडर टेम्पलेट शामिल है जिसे आप अपने प्रोजेक्ट के लिए शुरुआती बिंदु के रूप में उपयोग कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
