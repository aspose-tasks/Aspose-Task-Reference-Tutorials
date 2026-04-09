---
date: 2026-04-09
description: Aspose.Tasks का उपयोग करके अपने .NET प्रोजेक्ट्स में मानक कैलेंडर सेट
  करना और प्रोजेक्ट छुट्टियों का प्रबंधन करना सीखें, जिससे शेड्यूलिंग सटीक हो सके।
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Aspose.Tasks में मानक कैलेंडर सेट करें और अपवादों को संभालें
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में मानक कैलेंडर सेट करें और अपवादों को संभालें
url: /hi/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में मानक कैलेंडर सेट करें और अपवादों को संभालें

## परिचय

सटीक शेड्यूलिंग किसी भी सफल प्रोजेक्ट की रीढ़ होती है, और वास्तविक‑दुनिया की योजनाओं को अक्सर छुट्टियों, विशेष कार्यक्रमों, या अप्रत्याशित बंद होने के कारण डिफ़ॉल्ट कार्य कैलेंडर से अलग होना पड़ता है। Aspose.Tasks for .NET **set standard calendar** सेटिंग्स को आसानी से सेट करने और उसके ऊपर कस्टम अपवाद जोड़ने की सुविधा देता है। इस ट्यूटोरियल में आप सीखेंगे कि प्रोजेक्ट कैलेंडर को कैसे लोड करें, मानक कैलेंडर सेट करें, और Calendar Exception Collection फीचर के माध्यम से प्रोजेक्ट छुट्टियों का प्रबंधन कैसे करें।

## त्वरित उत्तर
- **“set standard calendar” क्या करता है?** यह एक कैलेंडर को डिफ़ॉल्ट कार्य समय (सुबह 9 से शाम 5 तक, सोमवार‑शुक्रवार) पर रीसेट करता है, इससे पहले कि आप कस्टम अपवाद जोड़ें।  
- **कौन सा मेथड मौजूदा अपवादों को साफ़ करता है?** `Calendar.Exceptions.Clear()` सभी पहले परिभाषित अपवादों को हटा देता है।  
- **मैं छुट्टी कैसे जोड़ सकता हूँ?** `DayWorking = false` के साथ एक `CalendarException` बनाएं और इसे कलेक्शन में जोड़ें।  
- **क्या बदलावों के बाद प्रोजेक्ट को पुनः लोड करना आवश्यक है?** नहीं, बदलाव सीधे मेमोरी में मौजूद `Project` ऑब्जेक्ट पर लागू होते हैं।  
- **कौन सी लाइब्रेरी आवश्यक हैं?** Aspose.Tasks for .NET (कोई भी समर्थित .NET संस्करण) और `System` नेमस्पेस।

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Aspose.Tasks for .NET** – इसे [यहाँ](https://releases.aspose.com/tasks/net/) डाउनलोड करें।  
2. **C#** का बुनियादी ज्ञान – आप कुछ छोटे स्निपेट लिखेंगे।  
3. **Visual Studio** या **JetBrains Rider** जैसे विकास वातावरण।

## नेमस्पेस आयात करें

ये `using` निर्देश आपको कैलेंडर मैनिपुलेशन के लिए आवश्यक क्लासेस तक पहुँच प्रदान करते हैं।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## कैलेंडर अपवाद क्या है?

*कैलेंडर अपवाद* वह अवधि दर्शाता है जहाँ सामान्य कार्य शेड्यूल बदल दिया जाता है – उदाहरण के लिए, कंपनी‑व्यापी छुट्टी या अस्थायी ओवरटाइम शेड्यूल। कैलेंडर में अपवाद जोड़कर आप बेस कैलेंडर को बदले बिना वास्तविक‑दुनिया की बाधाओं को मॉडल कर सकते हैं।

## Aspose.Tasks में मानक कैलेंडर कैसे सेट करें

पहला कदम है अपने प्रोजेक्ट फ़ाइल को लोड करना और वह कैलेंडर प्राप्त करना जिसे आप उपयोग करना चाहते हैं।

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### चरण 1: मौजूदा अपवाद साफ़ करें और मानक कैलेंडर पर रीसेट करें

नई नियम जोड़ने से पहले, पुराने अपवादों को साफ़ करना और **set standard calendar** सेटिंग्स को रीसेट करना एक अच्छी प्रथा है। यह एक साफ़ बेसलाइन सुनिश्चित करता है।

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### चरण 2: कार्य‑समय अपवाद परिभाषित करें

कभी‑कभी आपको एक अस्थायी शेड्यूल बनाना पड़ता है (जैसे, प्रोडक्ट लॉन्च के लिए विस्तारित घंटे)। नीचे दिया गया स्निपेट कई दिनों तक फैला एक कार्य‑समय अपवाद परिभाषित करता है और दो दैनिक कार्य अवधि शामिल करता है।

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### चरण 3: गैर‑कार्य समय अपवाद (छुट्टियाँ) जोड़ें

**प्रोजेक्ट छुट्टियों** को प्रबंधित करने के लिए, ऐसे अपवाद बनाएं जहाँ `DayWorking` `false` हो। नीचे का उदाहरण दो‑दिन की छुट्टी ब्लॉक जोड़ता है।

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### चरण 4: कैलेंडर अपवाद दिखाएँ (सत्यापन)

अपवाद जोड़ने के बाद, आप अक्सर यह सत्यापित करना चाहेंगे कि वे सही ढंग से रिकॉर्ड हुए हैं या नहीं। नीचे दिया गया लूप प्रत्येक अपवाद का विवरण कंसोल में प्रिंट करता है।

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### चरण 5: सभी अपवाद हटाएँ (सफाई)

यदि आपको कैलेंडर को उसकी मूल स्थिति में वापस लाना है, तो आप प्रोग्रामेटिक रूप से सभी अपवाद हटा सकते हैं।

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| सहेजने के बाद अपवाद नहीं दिख रहे हैं | परिवर्तनों के बाद प्रोजेक्ट सहेजा नहीं गया | परिवर्तन करने के बाद `project.Save("output.mpp")` कॉल करें। |
| ओवरलैपिंग अपवाद अनपेक्षित कार्य घंटे पैदा करते हैं | Aspose.Tasks ओवरलैपिंग अवधि के लिए अंतिम जोड़े गए अपवाद को उपयोग करता है | अपने `Add` कॉल्स को सावधानी से क्रमित करें या प्राथमिकताएँ मैन्युअल रूप से समायोजित करें। |
| `MakeStandardCalendar` कस्टम कार्य समय रीसेट करता है | यह जानबूझकर कस्टम समय साफ़ करता है; आवश्यकता होने पर कॉल के बाद उन्हें पुनः जोड़ें। | `MakeStandardCalendar` को कॉल करने के बाद अपने कस्टम `WorkingTime` ऑब्जेक्ट्स जोड़ें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही कैलेंडर में कई अपवाद जोड़ सकता हूँ?**  
A: हाँ, आप `AddRange` मेथड का उपयोग करके कैलेंडर में कई अपवाद जोड़ सकते हैं।

**Q: साप्ताहिक छुट्टियों जैसे आवर्ती अपवादों को मैं कैसे संभालूँ?**  
A: आप प्रोग्रामेटिक रूप से आवर्ती अपवादों की गणना कर सकते हैं और कस्टम लॉजिक का उपयोग करके उन्हें कैलेंडर में जोड़ सकते हैं।

**Q: क्या कैलेंडर अपवादों को बाहरी स्रोतों से आयात करना संभव है?**  
A: हाँ, आप डेटाबेस या CSV फ़ाइलों जैसे बाहरी स्रोतों से कैलेंडर अपवाद पढ़ सकते हैं और उन्हें अपने प्रोजेक्ट में एकीकृत कर सकते हैं।

**Q: यदि कैलेंडर में ओवरलैपिंग अपवाद हैं तो क्या होता है?**  
A: Aspose.Tasks for .NET आपको प्राथमिकताएँ निर्धारित करके या प्रोजेक्ट की आवश्यकताओं के आधार पर टकराव को हल करके ओवरलैपिंग अपवादों को संभालने की अनुमति देता है।

**Q: क्या मैं एक अपवाद के भीतर प्रत्येक दिन के कार्य समय को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, आप विशिष्ट शेड्यूलिंग आवश्यकताओं को पूरा करने के लिए अपवाद के भीतर व्यक्तिगत दिनों के लिए कस्टम कार्य समय निर्दिष्ट कर सकते हैं।

## निष्कर्ष

पहले **set standard calendar** सेट करके और फिर कस्टम अपवाद जोड़कर, आप प्रोजेक्ट शेड्यूलिंग पर पूर्ण नियंत्रण प्राप्त करते हैं, जिससे **प्रोजेक्ट छुट्टियों** को प्रबंधित करना और अन्य विशेष‑केस टाइमलाइन आसान हो जाता है। Aspose.Tasks में Calendar Exception Collection आपके .NET एप्लिकेशन में सीधे वास्तविक‑दुनिया के कैलेंडर को मॉडल करने का एक साफ़, प्रोग्रामेटिक तरीका प्रदान करता है।

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}