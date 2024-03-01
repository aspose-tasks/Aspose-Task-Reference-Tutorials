---
title: Aspose.Tasks में कार्य सप्ताह अनुकूलित करें
linktitle: Aspose.Tasks में कार्य सप्ताहों का संग्रह
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में कार्य सप्ताहों को कैसे अनुकूलित करें। वैयक्तिकृत प्रोजेक्ट कैलेंडर बनाने के लिए चरण-दर-चरण मार्गदर्शिका। अब डाउनलोड करो!
type: docs
weight: 17
url: /hi/net/time-recurrence-configuration/workweek-collection/
---
## परिचय
.NET के लिए Aspose.Tasks का उपयोग करके एक कस्टम कार्य सप्ताह बनाने पर हमारे ट्यूटोरियल में आपका स्वागत है! इस चरण-दर-चरण मार्गदर्शिका में, हम आपको आपके प्रोजेक्ट में एक कैलेंडर के लिए वैयक्तिकृत कार्य सप्ताह को परिभाषित करने की प्रक्रिया के बारे में बताएंगे। Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में Microsoft प्रोजेक्ट दस्तावेज़ों के साथ कुशलतापूर्वक काम करने में सक्षम बनाती है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. विजुअल स्टूडियो: सुनिश्चित करें कि आपकी मशीन पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: एक प्रोजेक्ट और कैलेंडर बनाएं
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## चरण 2: एक कस्टम कार्य सप्ताह परिभाषित करें
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## चरण 3: कार्य दिवस निर्धारित करें
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## चरण 4: कार्य सप्ताह की जानकारी प्रदर्शित करें
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
यह व्यापक मार्गदर्शिका आपको .NET के लिए Aspose.Tasks का उपयोग करके कुशलतापूर्वक कस्टम कार्य सप्ताह बनाने और प्रबंधित करने का अधिकार देती है।
## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks कस्टम कार्य सप्ताहों के साथ प्रोजेक्ट कैलेंडर को संभालने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि अपने प्रोजेक्ट में कस्टम कार्य सप्ताहों के बारे में जानकारी कैसे बनाएं और प्रदर्शित करें।
## पूछे जाने वाले प्रश्न
### क्या मैं एक ही प्रोजेक्ट में एकाधिक कस्टम कार्य सप्ताह रख सकता हूँ?
हाँ, आप किसी प्रोजेक्ट कैलेंडर में एकाधिक कस्टम कार्य सप्ताह जोड़ सकते हैं।
### मैं मौजूदा कार्य सप्ताहों को कैसे संशोधित कर सकता हूं?
 दिए गए का उपयोग करें`WorkWeek`मौजूदा कार्य सप्ताहों को संशोधित करने के गुण और तरीके।
### क्या Aspose.Tasks .NET कोर के साथ संगत है?
हाँ, Aspose.Tasks .NET कोर का समर्थन करता है।
### क्या मैं कस्टम कार्य सप्ताहों के साथ प्रोजेक्ट को Microsoft Project फ़ाइल स्वरूप में निर्यात कर सकता हूँ?
बिल्कुल, Aspose.Tasks आपको अपने प्रोजेक्ट को Microsoft Project सहित विभिन्न स्वरूपों में सहेजने की अनुमति देता है।
### मैं Aspose.Tasks-संबंधित प्रश्नों के लिए सहायता कहाँ से प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) किसी भी समर्थन या सहायता के लिए.