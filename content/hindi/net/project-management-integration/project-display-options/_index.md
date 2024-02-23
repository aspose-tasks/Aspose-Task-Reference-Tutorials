---
title: Aspose.Tasks में MS प्रोजेक्ट डिस्प्ले विकल्प कॉन्फ़िगर करना
linktitle: Aspose.Tasks में प्रोजेक्ट प्रदर्शन विकल्प कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट डिस्प्ले विकल्पों को प्रोग्रामेटिक रूप से कॉन्फ़िगर करने का तरीका जानें। अपने प्रोजेक्ट के स्वरूप को सहजता से अनुकूलित करें।
type: docs
weight: 17
url: /hi/net/project-management-integration/project-display-options/
---
## परिचय
Microsoft प्रोजेक्ट आपके प्रोजेक्ट के स्वरूप को अनुकूलित करने के लिए ढेर सारे प्रदर्शन विकल्प प्रदान करता है। .NET के लिए Aspose.Tasks इन विकल्पों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए एक मजबूत ढांचा प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके MS प्रोजेक्ट डिस्प्ले विकल्पों को कॉन्फ़िगर करने का तरीका जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET के लिए Aspose.Tasks: यहां से लाइब्रेरी डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. Microsoft प्रोजेक्ट फ़ाइल: प्रदर्शन विकल्पों को लागू करने के लिए एक वैध MS प्रोजेक्ट फ़ाइल (.mpp) तैयार रखें।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।

## नामस्थान आयात करना
सबसे पहले, अपने C# कोड में आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
 का उपयोग करके MS प्रोजेक्ट फ़ाइल लोड करें`Project` Aspose.Tasks द्वारा प्रदान की गई कक्षा:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## चरण 2: प्रदर्शन विकल्प कॉन्फ़िगर करें
अब, आइए एमएस प्रोजेक्ट में उपलब्ध विभिन्न डिस्प्ले विकल्पों को कॉन्फ़िगर करें:
### कार्य शेड्यूल चेतावनियाँ अक्षम करें
मैन्युअल रूप से निर्धारित कार्यों के साथ शेड्यूलिंग टकराव के लिए चेतावनियों को अक्षम करने के लिए (प्रोजेक्ट 2010 और बाद के लिए उपलब्ध):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### लेबल से पहले स्थान जोड़ें
संख्या मान और समय संक्षिप्तीकरण से पहले एक स्थान जोड़ने के लिए सेट करें:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### समय इकाइयों के लिए लेबल डिस्प्ले कॉन्फ़िगर करें
अनुकूलित करें कि अलग-अलग समय इकाइयाँ कैसे प्रदर्शित हों:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### प्रोजेक्ट सारांश कार्य दिखाएँ
संपूर्ण प्रोजेक्ट के बारे में सारांश जानकारी एक ही पंक्ति में प्रदर्शित करें:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### कार्य अनुसूची सुझाव सक्षम करें
मैन्युअल रूप से निर्धारित कार्यों के साथ शेड्यूलिंग टकराव के लिए सुझाव प्रदर्शित करने की अनुमति दें:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### हाइपरलिंक्स को रेखांकित करें
प्रोजेक्ट के भीतर हाइपरलिंक को रेखांकित करने के लिए सेट करें:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## चरण 3: प्रोजेक्ट सहेजें
अंत में, लागू प्रदर्शन विकल्पों के साथ प्रोजेक्ट को सहेजें:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट डिस्प्ले विकल्पों को कैसे कॉन्फ़िगर किया जाए। इन क्षमताओं के साथ, आप प्रोग्रामेटिक रूप से अपनी प्रोजेक्ट फ़ाइलों की उपस्थिति को कुशलतापूर्वक अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं इन प्रदर्शन विकल्पों को केवल विशिष्ट कार्यों पर ही लागू कर सकता हूँ?
उ: हां, आप Aspose.Tasks API का उपयोग करके व्यक्तिगत कार्यों के लिए चुनिंदा प्रदर्शन विकल्प लागू कर सकते हैं।
### प्रश्न: क्या ये प्रदर्शन विकल्प अंतर्निहित प्रोजेक्ट डेटा को प्रभावित करते हैं?
उत्तर: नहीं, ये विकल्प केवल प्रोजेक्ट के दृश्य प्रतिनिधित्व को संशोधित करते हैं और अंतर्निहित डेटा को नहीं बदलते हैं।
### प्रश्न: क्या ये प्रदर्शन विकल्प Microsoft प्रोजेक्ट के सभी संस्करणों के साथ संगत हैं?
उ: नहीं, कुछ विकल्प एमएस प्रोजेक्ट के कुछ संस्करणों के लिए विशिष्ट हो सकते हैं। अनुकूलता विवरण के लिए दस्तावेज़ देखें।
### प्रश्न: क्या मैं प्रदर्शन विकल्पों को वापस डिफ़ॉल्ट सेटिंग्स पर वापस ला सकता हूँ?
उ: हाँ, आप Aspose. Tasks API का उपयोग करके प्रदर्शन विकल्पों को उनके डिफ़ॉल्ट मानों पर रीसेट कर सकते हैं।
### प्रश्न: क्या प्रदर्शन विकल्पों को प्रोग्रामेटिक रूप से अनुकूलित करने की कोई सीमाएँ हैं?
उ: जबकि Aspose.Tasks व्यापक अनुकूलन क्षमताएं प्रदान करता है, एमएस प्रोजेक्ट फ़ाइल प्रारूप में सीमाओं के कारण कुछ प्रदर्शन विकल्प प्रोग्रामेटिक रूप से पहुंच योग्य नहीं हो सकते हैं।