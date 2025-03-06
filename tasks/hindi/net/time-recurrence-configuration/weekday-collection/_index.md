---
title: Aspose.Tasks में कार्यदिवसों में महारत हासिल करना
linktitle: Aspose.Tasks में सप्ताह के दिनों का संग्रह
second_title: Aspose.Tasks .NET API
description: कार्यदिवसों को सहजता से प्रबंधित करने में .NET के लिए Aspose.Tasks की शक्ति की खोज करें। कार्य दिवसों को अनुकूलित करें, सप्ताहांत हटाएं और आसानी से विशेष कैलेंडर बनाएं।
weight: 11
url: /hi/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्यदिवसों में महारत हासिल करना

## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो प्रोजेक्ट प्रबंधन डेटा के कुशल हेरफेर की सुविधा प्रदान करती है। इस ट्यूटोरियल में, हम Aspose.Tasks में कार्यदिवसों के संग्रह का पता लगाएंगे, जिससे आप कार्यदिवसों को अनुकूलित कर सकेंगे, सप्ताहांत हटा सकेंगे और अपनी परियोजना आवश्यकताओं को पूरा करने के लिए विशेष कैलेंडर बना सकेंगे। चाहे आप अनुभवी डेवलपर हों या नवागंतुक, यह चरण-दर-चरण मार्गदर्शिका आपको .NET के लिए Aspose.Tasks में कार्यदिवसों के साथ काम करने की प्रक्रिया के बारे में बताएगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित करें। आप इसे यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- C# प्रोग्रामिंग भाषा से परिचित होना।
- एकीकृत विकास वातावरण (आईडीई) जैसे विजुअल स्टूडियो।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाएं
एक नया Aspose.Tasks प्रोजेक्ट प्रारंभ करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## चरण 2: कैलेंडर तक पहुंचें
प्रोजेक्ट कैलेंडर पुनः प्राप्त करें:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## चरण 3: कार्यदिवसों को अनुकूलित करें
मौजूदा कार्यदिवस साफ़ करें और डिफ़ॉल्ट कार्यदिवस सेट करें:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// इसी तरह अन्य कार्यदिवस भी जोड़ें...
```
## चरण 4: कार्य समय जोड़ें
विशिष्ट कार्यदिवसों के लिए कार्य समय जोड़ें:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## चरण 5: कैलेंडर जानकारी प्रदर्शित करें
कंसोल पर आउटपुट कैलेंडर विवरण:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// प्रत्येक कार्यदिवस और कार्य समय प्रदर्शित करें...
```
## चरण 6: सप्ताहांत हटाएँ
सप्ताह के दिनों में से शनिवार और रविवार को हटाएँ:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## चरण 7: अद्यतन कार्य समय प्रदर्शित करें
सप्ताहांत हटाने के बाद आउटपुट अद्यतन कार्य समय:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// प्रत्येक अद्यतन कार्यदिवस और कार्य समय प्रदर्शित करें...
```
## चरण 8: 24 घंटे का कैलेंडर बनाएं
24 घंटे का कैलेंडर बनाएं और कार्यदिवसों की प्रतिलिपि बनाएँ:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने प्रोजेक्ट कैलेंडर के भीतर कार्यदिवसों को प्रबंधित करने में .NET के लिए Aspose.Tasks की शक्तिशाली क्षमताओं का पता लगाया। कार्य दिवसों को अनुकूलित करने से लेकर विशेष 24-घंटे के कैलेंडर बनाने तक, Aspose.Tasks प्रक्रिया को सरल बनाता है, परियोजना प्रबंधन में लचीलापन और नियंत्रण प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: Aspose.Tasks मुख्य रूप से .NET भाषाओं का समर्थन करता है, लेकिन यह जावा के लिए संस्करण भी प्रदान करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण उपलब्ध है?
 उ: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[Aspose.Tasks पृष्ठ जारी करता है](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 ए: पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक सहायता के लिए या एक सहायता योजना खरीदने पर विचार करें।
### प्रश्न: मुझे .NET के लिए Aspose.Tasks के लिए व्यापक दस्तावेज़ कहां मिल सकते हैं?
 ए: का संदर्भ लें[.NET दस्तावेज़ीकरण के लिए Aspose.Tasks](https://reference.aspose.com/tasks/net/) विस्तृत जानकारी के लिए.
### प्रश्न: मैं .NET के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 उ: आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
