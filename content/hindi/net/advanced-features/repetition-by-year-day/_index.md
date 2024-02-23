---
title: Aspose.Tasks में वर्ष दिवस के अनुसार पुनरावृत्ति
linktitle: Aspose.Tasks में वर्ष दिवस के अनुसार पुनरावृत्ति
second_title: Aspose.Tasks .NET API
description: आवर्ती कार्य प्रबंधन को कुशलतापूर्वक सुव्यवस्थित करने के लिए .NET के लिए Aspose.Tasks में वर्ष-दिवस की पुनरावृत्ति को संभालना सीखें।
type: docs
weight: 27
url: /hi/net/advanced-features/repetition-by-year-day/
---
## परिचय

परियोजना प्रबंधन के क्षेत्र में, कुशल कार्य शेड्यूलिंग और पुनरावृत्ति समय पर निष्पादन और सुचारू कार्यप्रवाह सुनिश्चित करने में महत्वपूर्ण भूमिका निभाते हैं। .NET के लिए Aspose.Tasks डेवलपर्स को उनके अनुप्रयोगों के भीतर आवर्ती कार्यों को आसानी से संभालने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके वर्ष-दिन दोहराव के साथ काम करने की जटिलताओं पर प्रकाश डालते हैं, जो वार्षिक पैटर्न के आधार पर आवर्ती कार्यों को बनाने के लिए एक व्यापक मार्गदर्शिका प्रदान करता है।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET लाइब्रेरी के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[वेबसाइट](https://releases.aspose.com/tasks/net/).
   
2. विकास वातावरण: .NET विकास के लिए विजुअल स्टूडियो या किसी अन्य पसंदीदा आईडीई के साथ एक उपयुक्त विकास वातावरण स्थापित करें।

3. सी# का बुनियादी ज्ञान: कोड उदाहरणों के साथ पालन करने के लिए सी# प्रोग्रामिंग भाषा के बुनियादी सिद्धांतों से खुद को परिचित करें।

4. परियोजना प्रबंधन अवधारणाएँ: परियोजना प्रबंधन अवधारणाओं और कार्य शेड्यूलिंग की समझ से ट्यूटोरियल अवधारणाओं को प्रभावी ढंग से समझने में मदद मिलेगी।

## नामस्थान आयात करें

इससे पहले कि हम कोडिंग शुरू करें, आइए .NET के लिए Aspose.Tasks का उपयोग करके अपने कार्य में हेरफेर को सुविधाजनक बनाने के लिए आवश्यक नेमस्पेस आयात करें।

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

अब, आइए दिए गए उदाहरण को कई चरणों में तोड़ें और प्रत्येक चरण को विस्तार से समझाएं।

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 यहां, हम एक नया प्रारंभ करते हैं`Project` ऑब्जेक्ट करें और "Project1.mpp" नामक मौजूदा प्रोजेक्ट फ़ाइल लोड करें।

## चरण 2: आवर्ती कार्य पैरामीटर्स को परिभाषित करें

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 इस चरण में, हम अपने आवर्ती कार्य के लिए पैरामीटर परिभाषित करते हैं। हम कार्य का नाम, अवधि और पुनरावृत्ति पैटर्न निर्दिष्ट करते हैं। वार्षिक पुनरावृत्ति के लिए, हम इसका उपयोग करते हैं`YearlyRecurrencePattern` और पुनरावृत्ति को जुलाई के 1 दिन पर घटित होने के लिए सेट करें`ByYearDayRepetition`. इसके अतिरिक्त, हम 1 जुलाई, 2018 से 1 जुलाई, 2019 तक पुनरावृत्ति सीमा को परिभाषित करते हैं।

## चरण 3: प्रोजेक्ट में कार्य जोड़ें

```csharp
project.RootTask.Children.Add(parameters);
```

यहां, हम प्रोजेक्ट के मूल कार्य में परिभाषित आवर्ती कार्य पैरामीटर जोड़ते हैं।

## चरण 4: प्रोजेक्ट सहेजें

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

अंत में, हम संशोधित प्रोजेक्ट फ़ाइल को अतिरिक्त आवर्ती कार्य के साथ सहेजते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks में साल-दर-साल दोहराव के साथ काम करने की प्रक्रिया का पता लगाया है। दिए गए चरणों का पालन करके, डेवलपर्स परियोजना प्रबंधन क्षमताओं को बढ़ाते हुए, अपने अनुप्रयोगों में आवर्ती कार्य कार्यक्षमता को सहजता से एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks जटिल पुनरावृत्ति पैटर्न को संभाल सकता है?

A1: हां, Aspose.Tasks विभिन्न पुनरावृत्ति पैटर्न के लिए व्यापक समर्थन प्रदान करता है, जिसमें वार्षिक, मासिक, साप्ताहिक और दैनिक दोहराव जैसे जटिल पैटर्न शामिल हैं।

### Q2: क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों के साथ संगत है?

A2: बिल्कुल, Aspose.Tasks MPP, XML और CSV जैसे लोकप्रिय प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है, जो विभिन्न प्रोजेक्ट प्रबंधन टूल में अनुकूलता सुनिश्चित करता है।

### Q3: क्या Aspose.Tasks डेवलपर्स के लिए दस्तावेज़ीकरण और सहायता प्रदान करता है?

A3: हां, डेवलपर्स व्यापक दस्तावेज़ीकरण तक पहुंच सकते हैं और किसी भी प्रश्न या समस्या के लिए Aspose.कार्य समुदाय मंचों से सहायता ले सकते हैं।

### Q4: क्या मैं Aspose.Tasks का उपयोग करके कार्य गुणों जैसे अवधि और प्रारंभ तिथि को अनुकूलित कर सकता हूँ?

A4: निश्चित रूप से, Aspose.Tasks कार्य गुणों को गतिशील रूप से हेरफेर करने के लिए मजबूत एपीआई प्रदान करता है, जिससे डेवलपर्स को अवधि, प्रारंभ तिथियां, निर्भरताएं और बहुत कुछ अनुकूलित करने की अनुमति मिलती है।

### Q5: क्या Aspose.Tasks छोटे पैमाने और उद्यम स्तर की परियोजनाओं दोनों के लिए उपयुक्त है?

A5: वास्तव में, Aspose.Tasks को व्यक्तिगत कार्यों से लेकर बड़े पैमाने की उद्यम परियोजनाओं तक, सभी स्तरों की परियोजनाओं पर काम करने वाले डेवलपर्स की जरूरतों को पूरा करने के लिए डिज़ाइन किया गया है।