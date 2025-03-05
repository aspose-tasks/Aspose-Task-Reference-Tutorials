---
title: Aspose.Tasks में कार्य समय को कॉन्फ़िगर करना
linktitle: Aspose.Tasks में कार्य समय को कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks के साथ .NET में प्रोजेक्ट शेड्यूलिंग बढ़ाएँ। सटीक संसाधन प्रबंधन के लिए कार्य समय को सहजता से कॉन्फ़िगर करें। अभी लाइब्रेरी डाउनलोड करें!
type: docs
weight: 13
url: /hi/net/time-recurrence-configuration/working-times/
---
## परिचय
परियोजना प्रबंधन में, सटीक शेड्यूलिंग और संसाधन आवंटन के लिए कार्य समय पर सटीक नियंत्रण महत्वपूर्ण है। .NET के लिए Aspose.Tasks आपकी परियोजनाओं के भीतर कार्य समय की जानकारी को संभालने के लिए एक शक्तिशाली समाधान प्रदान करता है। यह ट्यूटोरियल आपको .NET वातावरण में Aspose.Tasks का उपयोग करके कार्य समय को कॉन्फ़िगर करने की प्रक्रिया में मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
-  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
- विज़ुअल स्टूडियो या कोई पसंदीदा C# विकास वातावरण स्थापित करें।
## नामस्थान आयात करें
Aspose.Tasks कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## चरण 1: कैलेंडर बनाएं
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
यहां, हम एक नया प्रोजेक्ट शुरू करते हैं और मानक कैलेंडर के आधार पर "MyCalendar" नामक एक कैलेंडर बनाते हैं। इस कैलेंडर का उपयोग विशिष्ट कार्य समय को परिभाषित करने के लिए किया जाएगा।

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## चरण 2: कार्य सप्ताह की जानकारी प्रदर्शित करें
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
यह चरण निर्दिष्ट कैलेंडर में कार्य दिवसों की कुल संख्या प्रिंट करता है।
## चरण 3: कार्य समय का विवरण
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
इस भाग में, हम सप्ताह के प्रत्येक दिन को दोहराते हैं, दिन के प्रकार और संबंधित कार्य समय को प्रिंट करते हैं। आप अपनी परियोजना की आवश्यकताओं के अनुसार प्रत्येक कार्यदिवस के लिए कार्य समय को अनुकूलित कर सकते हैं।
## निष्कर्ष
.NET के लिए Aspose.Tasks में कार्य समय को प्रभावी ढंग से कॉन्फ़िगर करना सटीक परियोजना योजना और संसाधन प्रबंधन सुनिश्चित करता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने प्रोजेक्ट वर्कफ़्लो में कार्य समय समायोजन को सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Tasks बड़े पैमाने पर परियोजना प्रबंधन के लिए उपयुक्त है?
हाँ, Aspose.Tasks को विभिन्न आकारों की परियोजनाओं को संभालने के लिए डिज़ाइन किया गया है, जो कुशल परियोजना प्रबंधन के लिए मजबूत सुविधाएँ प्रदान करता है।
### क्या मैं टीम के विभिन्न सदस्यों के लिए अलग-अलग कार्य समय निर्धारित कर सकता हूँ?
बिल्कुल। आप वैयक्तिकृत शेड्यूल की अनुमति देकर, प्रति-संसाधन के आधार पर कार्य समय को अनुकूलित कर सकते हैं।
### क्या Aspose.Tasks अन्य परियोजना प्रबंधन उपकरणों के साथ एकीकरण का समर्थन करता है?
हां, Aspose.Tasks विभिन्न परियोजना प्रबंधन उपकरणों के साथ एकीकरण की सुविधा प्रदान करता है, जिससे अंतरसंचालनीयता बढ़ती है।
### क्या प्रोजेक्ट डेटा को विभिन्न प्रारूपों में आयात/निर्यात करना संभव है?
Aspose.Tasks कई फ़ाइल स्वरूपों का समर्थन करता है, जो प्रोजेक्ट डेटा के लिए निर्बाध आयात/निर्यात संचालन को सक्षम बनाता है।
### Aspose.Tasks अपडेट कितनी बार जारी किए जाते हैं?
नवीनतम तकनीकों के साथ अनुकूलता सुनिश्चित करने और उपयोगकर्ता की प्रतिक्रिया को संबोधित करने के लिए अपडेट नियमित रूप से जारी किए जाते हैं।