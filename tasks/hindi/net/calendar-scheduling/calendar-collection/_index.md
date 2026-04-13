---
date: 2026-04-13
description: Aspose.Tasks for .NET में कार्य घंटे सेट करना और कैलेंडर संग्रह प्रबंधित
  करना सीखें। Microsoft Project से कैलेंडर आयात करें, कैलेंडर प्रोजेक्ट हटाएँ, और
  नाम से कैलेंडर आसानी से प्राप्त करें।
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Aspose.Tasks में कैलेंडर संग्रह का प्रबंधन
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks कैलेंडर संग्रह में कार्य घंटे सेट करें
url: /hi/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks कैलेंडर संग्रह में कार्य घंटे सेट करें

इस ट्यूटोरियल में, आप सीखेंगे कि **कार्य घंटे कैसे सेट करें** और Aspose.Tasks for .NET का उपयोग करके कैलेंडर संग्रह को कैसे प्रबंधित करें। कैलेंडर कार्यदिवस, छुट्टियों और अपवादों को परिभाषित करते हैं, इसलिए इन्हें समझने से आप प्रोजेक्ट शेड्यूल को सटीक रूप से नियंत्रित कर सकते हैं। हम आपको यह भी दिखाएंगे कि Microsoft Project से कैलेंडर कैसे आयात करें, प्रोजेक्ट से कैलेंडर कैसे हटाएँ, और नाम द्वारा कैलेंडर कैसे प्राप्त करें।

## त्वरित उत्तर
- **कैलेंडरों के लिए मुख्य क्लास कौन सी है?** `Project.Calendars` संग्रह।  
- **मैं कार्य घंटे कैसे सेट करूँ?** एक `Calendar` ऑब्जेक्ट बनाएँ या संशोधित करें और उसके `WorkingTime` को परिभाषित करें।  
- **क्या मैं Microsoft Project से कैलेंडर आयात कर सकता हूँ?** हाँ – एक MPP फ़ाइल लोड करें और उसके कैलेंडर तक पहुँचें।  
- **प्रोजेक्ट से कैलेंडर कैसे हटाएँ?** `Project.Calendars.Remove(calendar)` का उपयोग करें।  
- **नाम द्वारा कैलेंडर कैसे प्राप्त करें?** `Project.Calendars.GetByName("YourCalendar")` को कॉल करें।  

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. Visual Studio: .NET विकास के लिए Visual Studio या कोई अन्य संगत IDE स्थापित करें।  
2. Aspose.Tasks for .NET: Aspose.Tasks for .NET को [यहाँ](https://releases.aspose.com/tasks/net/) से डाउनलोड और स्थापित करें।  
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की परिचितता लाभदायक होगी।  

## नेमस्पेस आयात करें

पहले, Aspose.Tasks के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## नया कैलेंडर बनाना

### चरण 1: नया `Project` ऑब्जेक्ट प्रारंभ करें।
```csharp
var project = new Project();
```

### चरण 2: प्रोजेक्ट के कैलेंडर संग्रह में कैलेंडर जोड़ें।
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### चरण 3: कैलेंडरों के माध्यम से इटररेट करें और उनके नाम प्रदर्शित करें।
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## कैलेंडर के लिए कार्य घंटे कैसे सेट करें?

**कार्य घंटे सेट करने** के लिए, आप `Calendar` की `WorkingTime` संग्रह को संशोधित करते हैं।  
उदाहरण के लिए, आप एक मानक 9 am‑5 pm कार्यदिवस परिभाषित कर सकते हैं या कस्टम अपवाद जोड़ सकते हैं।  
इसका कोड वही है जैसा कि बाद में हम एक मानक कैलेंडर बनाते समय दिखाए गए उदाहरणों में है।  

## एक नए कैलेंडर से मौजूदा कैलेंडर को बदलना

### चरण 1: मौजूदा प्रोजेक्ट लोड करें।
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: मौजूदा कैलेंडर हटाएँ (यदि मौजूद है)।  
यह **कैलेंडर हटाने के प्रोजेक्ट** परिदृश्य को दर्शाता है।
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### चरण 3: एक नया कैलेंडर जोड़ें।
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## नाम या आईडी द्वारा कैलेंडर प्राप्त करना

### चरण 1: प्रोजेक्ट लोड करें।
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: कैलेंडर को नाम या UID द्वारा प्राप्त करें।  
यह **नाम द्वारा कैलेंडर प्राप्त करने** ऑपरेशन को दर्शाता है।
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### चरण 3: कैलेंडर विवरण प्रदर्शित करें।
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## कैलेंडरों पर इटररेट करना

### चरण 1: प्रोजेक्ट लोड करें।
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: कैलेंडरों की संख्या प्राप्त करें।
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### चरण 3: कैलेंडर संग्रह पर इटररेट करें और नाम प्रदर्शित करें।
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## मानक कैलेंडर बनाना

### चरण 1: नया प्रोजेक्ट प्रारंभ करें।
```csharp
var project = new Project();
```

### चरण 2: एक नया कैलेंडर परिभाषित करें और उसे मानक बनाएं।
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### चरण 3: प्रोजेक्ट सहेजें।
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान

- **`GetByName` का उपयोग करते समय कैलेंडर नहीं मिला** – सुनिश्चित करें कि नाम बिल्कुल वही है जो कैलेंडर जोड़ते समय उपयोग किया गया था, जिसमें केस भी मेल खाता हो।  
- **कार्य घंटे लागू नहीं हुए** – `WorkingTime` सेट करने के बाद, प्रोजेक्ट को सहेजना याद रखें; अन्यथा परिवर्तन केवल मेमोरी में रहेंगे।  
- **MPP फ़ाइल से कैलेंडर आयात करने में विफलता** – जाँचें कि स्रोत फ़ाइल एक वैध Microsoft Project फ़ाइल है और आपके पास पढ़ने की अनुमति है।  

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: क्या मैं Aspose.Tasks में कस्टम कार्यदिवस बना सकता हूँ?
A1: हाँ, आप कैलेंडरों में अपवाद जोड़कर कस्टम कार्यदिवस बना सकते हैं।

### प्रश्न 2: क्या Microsoft Project फ़ाइलों से कैलेंडर आयात करना संभव है?
A2: बिल्कुल, Aspose.Tasks Microsoft Project फ़ाइलों से कैलेंडर आयात करने का समर्थन करता है।

### प्रश्न 3: मैं प्रोजेक्ट से एक विशिष्ट कैलेंडर कैसे हटा सकता हूँ?
A3: आप कैलेंडर को संग्रह से प्राप्त करके और फिर `Remove` मेथड को कॉल करके हटा सकते हैं।

### प्रश्न 4: क्या Aspose.Tasks कैलेंडर को विभिन्न फ़ॉर्मेट में निर्यात करने का समर्थन करता है?
A4: हाँ, Aspose.Tasks कैलेंडर को XML, MPP आदि जैसे विभिन्न फ़ॉर्मेट में निर्यात करने की अनुमति देता है।

### प्रश्न 5: क्या मैं कैलेंडर में विशिष्ट दिनों के लिए कार्य घंटे अनुकूलित कर सकता हूँ?
A5: निश्चित रूप से, आप कैलेंडर में अपवादों का उपयोग करके व्यक्तिगत दिनों के लिए कार्य घंटे परिभाषित कर सकते हैं।

## बार-बार पूछे जाने वाले प्रश्न

**प्रश्न: 24‑घंटे शिफ्ट कैलेंडर सेट करने का सबसे अच्छा तरीका क्या है?**  
**उत्तर:** एक नया कैलेंडर बनाएं, मौजूदा `WorkingTime` प्रविष्टियों को साफ़ करें, और प्रत्येक कार्यदिवस के लिए 00:00 से 24:00 तक एक ही `WorkingTime` रेंज जोड़ें।

**प्रश्न: क्या मैं एक प्रोजेक्ट से दूसरे प्रोजेक्ट में कैलेंडर कॉपी कर सकता हूँ?**  
**उत्तर:** हाँ—`project.Save` का उपयोग करके कैलेंडर को XML में निर्यात करें और फिर `new Project(xmlPath)` से इसे दूसरे प्रोजेक्ट में आयात करें।

**प्रश्न: मैं प्रोग्रामेटिक रूप से Microsoft Project से कैलेंडर कैसे आयात करूँ?**  
**उत्तर:** `new Project("source.mpp")` के साथ MPP फ़ाइल लोड करें; कैलेंडर `project.Calendars` के माध्यम से उपलब्ध हो जाएंगे।

**प्रश्न: प्रोजेक्ट में कैलेंडरों की संख्या पर कोई सीमा है क्या?**  
**उत्तर:** व्यावहारिक रूप से नहीं; संग्रह मेमोरी की अनुमति के अनुसार जितने भी कैलेंडर रख सकता है, लेकिन प्रदर्शन के लिए सूची को प्रबंधनीय रखें।

**प्रश्न: क्या कैलेंडर में किए गए परिवर्तन स्वचालित रूप से उन कार्यों को अपडेट करते हैं जो इसका उपयोग करते हैं?**  
**उत्तर:** हाँ—प्रोजेक्ट सहेजने के बाद, कैलेंडर से जुड़े कार्य अपडेटेड कार्य समय को दर्शाते हैं।

---

**अंतिम अपडेट:** 2026-04-13  
**परीक्षण किया गया:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}