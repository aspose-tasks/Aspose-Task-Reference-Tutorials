---
title: Aspose.Tasks में कार्य समय में महारत हासिल करना
linktitle: Aspose में कार्य समय का संग्रह। कार्य
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट टाइमलाइन को कुशलतापूर्वक प्रबंधित करने में .NET के लिए Aspose.Tasks की शक्ति का अन्वेषण करें। कैलेंडर अनुकूलित करें, कार्य समय निर्धारित करें और अपनी परियोजनाओं को आसानी से सुव्यवस्थित करें।
type: docs
weight: 14
url: /hi/net/time-recurrence-configuration/working-time-collection/
---
## परिचय
क्या आप .NET के लिए Aspose.Tasks में कामकाजी समय को प्रबंधित करने की कला में महारत हासिल करना चाहते हैं? आगे कोई तलाश नहीं करें! इस चरण-दर-चरण मार्गदर्शिका में, हम Aspose.Tasks का उपयोग करके कार्य समय संग्रह की जटिलताओं को समझेंगे, जो आपको कस्टम कैलेंडर को कुशलतापूर्वक संभालने और अपनी परियोजना की समयसीमा को सुव्यवस्थित करने के लिए सशक्त बनाएगा।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
-  .NET लाइब्रेरी के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[Aspose. कार्य रिलीज़ पृष्ठ](https://releases.aspose.com/tasks/net/).
- कार्य वातावरण: एक उपयुक्त विकास वातावरण स्थापित करें, अधिमानतः .NET-संगत आईडीई का उपयोग करके।
## नामस्थान आयात करें
अपने प्रोजेक्ट में, Aspose तक पहुँचने के लिए आवश्यक नामस्थान आयात करें। कार्य कार्यक्षमताएँ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
अब, आइए एक सहज सीखने के अनुभव को सुनिश्चित करते हुए ट्यूटोरियल को कई चरणों में विभाजित करें।
## चरण 1: एक कस्टम कैलेंडर बनाएं
एक नया प्रोजेक्ट बनाकर और उसमें एक कस्टम कैलेंडर जोड़कर शुरुआत करें:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## चरण 2: कार्य दिवसों को परिभाषित करें
सोमवार से शुक्रवार तक डिफ़ॉल्ट कार्य दिवस सेट करें:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## चरण 3: शनिवार कार्य समय कॉन्फ़िगर करें
शनिवार के लिए कार्य समय निर्दिष्ट करें:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## चरण 4: शनिवार कार्य अवधि प्रिंट करें
शनिवार के लिए कॉन्फ़िगर किए गए कार्य समय को प्रिंट करें:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## चरण 5: रविवार कार्य समय कॉन्फ़िगर करें
रविवार के लिए कार्य समय निर्धारित करें:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## चरण 6: रविवार कार्य अवधि प्रिंट करें
रविवार के लिए कॉन्फ़िगर किए गए कार्य समय को प्रिंट करें:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## चरण 7: कैलेंडर में कस्टम दिन जोड़ें
कैलेंडर में कॉन्फ़िगर किए गए शनिवार और रविवार को शामिल करें:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## चरण 8: कामकाजी समय से गुजरें
कार्य समय का पता लगाएं और उन्हें कैलेंडर में प्रत्येक दिन के लिए प्रदर्शित करें:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
अब जब आपने चरणों को सफलतापूर्वक पार कर लिया है, तो आप कार्य समय को प्रभावी ढंग से प्रबंधित करने में .NET के लिए Aspose.Tasks की शक्ति का उपयोग करने के लिए सुसज्जित हैं।
## निष्कर्ष
Aspose.Tasks में कार्य समय के संग्रह में महारत हासिल करना आपको प्रोजेक्ट कैलेंडर को अनुकूलित करने, सटीक शेड्यूलिंग और कुशल संसाधन उपयोग सुनिश्चित करने का अधिकार देता है। इस व्यापक मार्गदर्शिका से प्राप्त ज्ञान से लैस होकर, आत्मविश्वास के साथ अपनी परियोजनाओं में लग जाएँ।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Tasks बड़े पैमाने पर परियोजना प्रबंधन के लिए उपयुक्त है?
हाँ, Aspose.Tasks को विभिन्न आकारों की परियोजनाओं को संभालने के लिए डिज़ाइन किया गया है, जो कुशल परियोजना प्रबंधन के लिए मजबूत सुविधाएँ प्रदान करता है।
### क्या मैं Aspose.Tasks को अन्य .NET लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?
निश्चित रूप से! Aspose.Tasks अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जिससे इसकी बहुमुखी प्रतिभा और अनुकूलता बढ़ती है।
### Aspose.Tasks को कितनी बार अद्यतन किया जाता है?
 नई सुविधाओं, संवर्द्धन और संगतता सुधारों को शामिल करने के लिए Aspose.Tasks को नियमित रूप से अपडेट किया जाता है। जाँचें[रिलीज पेज](https://releases.aspose.com/tasks/net/) नवीनतम अपडेट के लिए.
### क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप Aspose पर जाकर नि:शुल्क परीक्षण के साथ कार्यों का पता लगा सकते हैं[इस लिंक](https://releases.aspose.com/).
### मैं Aspose.Tasks के लिए सहायता कहाँ से प्राप्त कर सकता हूँ?
 किसी भी प्रश्न या सहायता के लिए, पर जाएँ[Aspose.Tasks सहायता फ़ोरम](https://forum.aspose.com/c/tasks/15).