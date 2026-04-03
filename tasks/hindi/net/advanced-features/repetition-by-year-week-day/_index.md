---
date: 2026-04-03
description: Aspose.Tasks का उपयोग करके आवर्ती कार्य प्रोजेक्ट जोड़ना और प्रोजेक्ट
  को MPP के रूप में सहेजना सीखें। यह गाइड वर्ष‑सप्ताह‑दिन के अनुसार पुनरावृत्ति सुविधा
  को चरण‑बद्ध दिखाता है।
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks में वर्ष, सप्ताह, दिन द्वारा पुनरावृत्ति
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks का उपयोग कैसे करें – वर्ष, सप्ताह, दिन द्वारा दोहराव
url: /hi/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में वर्ष, सप्ताह, दिन द्वारा दोहराव

## परिचय

जब आपको जटिल आवर्ती शेड्यूल को संभालने के लिए **how to use Aspose.Tasks** की आवश्यकता होती है, तो लाइब्रेरी आपको वार्षिक पैटर्न पर सूक्ष्म नियंत्रण देती है। इस ट्यूटोरियल में हम एक टास्क बनाने की प्रक्रिया देखेंगे जो किसी विशेष महीने के एक विशिष्ट सप्ताह के दिन पर कई वर्षों तक दोहराता है। अंत तक आप **add recurring task project** प्रविष्टियों को जोड़ सकेंगे और **save project as MPP** को केवल कुछ ही C# लाइनों से सहेज सकेंगे।

## त्वरित उत्तर

- **“Repetition by Year Week Day” क्या दर्शाता है?** यह प्रत्येक वर्ष एक निर्धारित महीने के चुने हुए सप्ताह के दिन (जैसे, पहला रविवार) पर टास्क को दोहराता है।  
- **कौन से .NET संस्करण समर्थित हैं?** सभी आधुनिक .NET Framework और .NET Core/5/6 संस्करण समर्थित हैं।  
- **क्या कोड चलाने के लिए लाइसेंस आवश्यक है?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं आवृत्ति सीमा बदल सकता हूँ?** हाँ – आप प्रारंभ तिथि, समाप्ति तिथि, या निश्चित संख्या में आवृत्तियों को सेट कर सकते हैं।  
- **क्या आउटपुट एक MPP फ़ाइल है?** बिल्कुल – प्रोजेक्ट को Microsoft Project के लिए तैयार MPP फ़ाइल के रूप में सहेजा जाता है।

## “Repetition by Year Week Day” सुविधा क्या है?

यह सुविधा आपको एक वार्षिक आवृत्ति परिभाषित करने देती है जो किसी विशेष **day of the week** (जैसे, रविवार) और महीने के भीतर एक **position** (पहला, दूसरा, अंतिम, आदि) को लक्षित करती है। यह त्रैमासिक समीक्षाओं, वार्षिक ऑडिट्स, या किसी भी कैलेंडर‑आधारित रिदम वाले इवेंट के लिए आदर्श है।

## आवर्ती कार्यों के लिए Aspose.Tasks क्यों उपयोग करें?

- **Precision** – महीनों, सप्ताह के दिनों, और क्रमिक स्थितियों पर पूर्ण नियंत्रण।  
- **Compatibility** – मूल MPP फ़ाइलें बनाता है जो Microsoft Project में बिना किसी समस्या के खुलती हैं।  
- **No COM interop** – शुद्ध .NET API, Office इंस्टॉलेशन की आवश्यकता नहीं।  
- **Scalability** – छोटे प्रोजेक्ट्स और एंटरप्राइज़‑स्तर के शेड्यूल दोनों के लिए काम करता है।

## पूर्वापेक्षाएँ

1. **Basic .NET knowledge** – C# और ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं की परिचितता।  
2. **Aspose.Tasks for .NET** – इसे [download link](https://releases.aspose.com/tasks/net/) से डाउनलोड करें और DLL को अपने प्रोजेक्ट में जोड़ें।  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) में सभी क्लासों के विस्तृत विवरण हैं।  
4. **A development IDE** – Visual Studio, Rider, या कोई भी संगत .NET एडिटर।

अब जब आप तैयार हैं, चलिए कार्यान्वयन देखते हैं।

## आवर्ती कार्यों के लिए Aspose.Tasks का उपयोग कैसे करें

### आवश्यक नेमस्पेस आयात करना

पहले, आवश्यक नेमस्पेस को स्कोप में लाएँ ताकि आप प्रोजेक्ट्स, टास्क और सहेजने विकल्पों के साथ काम कर सकें।

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### चरण 1: प्रोजेक्ट और टास्क पैरामीटर प्रारंभ करें

`Project` का नया इंस्टेंस बनाएं, फिर एक `RecurringTaskParameters` ऑब्जेक्ट परिभाषित करें जो आवृत्ति पैटर्न का वर्णन करता है।

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** `Month`, `WeekDay`, और `Position` को अपने वास्तविक शेड्यूल के अनुसार समायोजित करें।

### चरण 2: प्रोजेक्ट में पैरामीटर जोड़ें

आवर्ती टास्क परिभाषा को प्रोजेक्ट की रूट में डालें।

```csharp
project.RootTask.Children.Add(parameters);
```

### चरण 3: प्रोजेक्ट को MPP के रूप में सहेजें

अंत में, प्रोजेक्ट को MPP फ़ाइल में सहेजें ताकि इसे Microsoft Project या किसी भी संगत व्यूअर में खोला जा सके।

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> यह **save project as mpp** को एक ही कोड लाइन में दर्शाता है।

## सामान्य समस्याएँ और समाधान

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| MPP फ़ाइल खोलने के बाद कोई टास्क नहीं दिखता | आवृत्ति सीमा तिथियां प्रोजेक्ट कैलेंडर के बाहर हैं | `Start` और `Finish` तिथियों को प्रोजेक्ट के कार्य समय के भीतर सुनिश्चित करें |
| `Add` पर अपवाद `ArgumentNullException` | `parameters` null है या पूरी तरह से प्रारंभ नहीं किया गया है | सभी आवश्यक प्रॉपर्टीज़ (TaskName, Duration, RecurrencePattern) सेट हैं यह सुनिश्चित करें |
| गलत सप्ताह का दिन चयनित | `WeekDay` enum मान मेल नहीं खाता | आवश्यकतानुसार `DayOfWeek.Monday` … `DayOfWeek.Sunday` का उपयोग करें |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं प्रदान किए गए उदाहरण से आगे आवृत्ति पैटर्न को अनुकूलित कर सकता हूँ?**  
A: हाँ, Aspose.Tasks आपको `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, या कस्टम `RecurrenceRange` ऑब्जेक्ट्स को मिलाकर किसी भी शेड्यूल के अनुसार अनुकूलित करने देता है।

**Q: क्या Aspose.Tasks for .NET अन्य प्रोजेक्ट मैनेजमेंट सॉफ़्टवेयर के साथ संगत है?**  
A: बिल्कुल – लाइब्रेरी MPP, XML, और Primavera फ़ॉर्मेट को पढ़ती और लिखती है, जिससे सुगम डेटा एक्सचेंज संभव होता है।

**Q: मैं आवर्ती टास्क में अपवाद या संशोधनों को कैसे संभाल सकता हूँ?**  
A: `ExceptionTask` क्लास का उपयोग करके विशिष्ट घटनाओं के लिए ओवरराइड बनाएं, या `RecurringTaskParameters` को संपादित करके प्रोजेक्ट को पुनः सहेजें।

**Q: क्या Aspose.Tasks क्लाउड‑आधारित समाधान का समर्थन करता है?**  
A: हाँ, आप API को Azure Functions, AWS Lambda, या किसी भी .NET‑संगत क्लाउड सेवा में चला सकते हैं।

**Q: क्या Aspose.Tasks for .NET के लिए ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks for .NET का मुफ्त ट्रायल [website](https://releases.aspose.com/) से प्राप्त कर सकते हैं, जिससे आप खरीद निर्णय से पहले इसकी सुविधाओं का अन्वेषण कर सकते हैं।

**Q: मैं मौजूदा प्रोजेक्ट में अन्य डेटा को ओवरराइट किए बिना आवर्ती टास्क कैसे जोड़ूँ?**  
A: `new Project("Existing.mpp")` से मौजूदा प्रोजेक्ट लोड करें, `RecurringTaskParameters` को `RootTask.Children` में जोड़ें, और फिर फ़ाइल को `Save` करें।

## निष्कर्ष

**how to use Aspose.Tasks** को **Repetition by Year Week Day** परिदृश्य में महारत हासिल करके, आप **add recurring task project** प्रविष्टियों को जोड़ने में सक्षम होते हैं जो वास्तविक कैलेंडर के साथ पूरी तरह से मेल खाती हैं और **save project as MPP** को सहज सहयोग के लिए सहेजते हैं। इन स्निपेट्स को अपने समाधान में शामिल करें ताकि शेड्यूलिंग की सटीकता बढ़े और मैनुअल प्रयास कम हो।

---

**अंतिम अद्यतन:** 2026-04-03  
**परीक्षित संस्करण:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}