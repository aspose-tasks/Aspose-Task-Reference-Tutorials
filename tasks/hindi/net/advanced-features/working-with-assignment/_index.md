---
title: Aspose.Tasks में असाइनमेंट के साथ कार्य करना
linktitle: Aspose.Tasks में असाइनमेंट के साथ कार्य करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks का उपयोग करके .NET में प्रोजेक्ट असाइनमेंट प्रबंधित करना सीखें। संसाधन शेड्यूलिंग के लिए विभिन्न रूपरेखाओं का अन्वेषण करें।
type: docs
weight: 13
url: /hi/net/advanced-features/working-with-assignment/
---
## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks में असाइनमेंट के साथ कैसे काम किया जाए। परियोजना प्रबंधन में असाइनमेंट महत्वपूर्ण हैं क्योंकि वे कार्यों के लिए संसाधन आवंटित करते हैं, शेड्यूल करने और प्रगति पर नज़र रखने में मदद करते हैं। हम Aspose.Tasks का उपयोग करके विभिन्न रूपरेखाओं के साथ संसाधन असाइनमेंट टाइमफ़ेज़ डेटा उत्पन्न करने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

1.  .NET के लिए Aspose.Tasks की स्थापना: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
2. C# और .NET फ्रेमवर्क की बुनियादी समझ: C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क अवधारणाओं से परिचित होना आवश्यक है।

## नामस्थान आयात करें

अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## चरण 1: एक प्रोजेक्ट और कार्य बनाएं

आइए एक नया प्रोजेक्ट बनाकर और उसमें एक कार्य जोड़कर शुरुआत करें। कार्य के लिए आरंभ तिथि, अवधि और समाप्ति तिथि निर्धारित करें:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## चरण 2: एक संसाधन जोड़ें और कार्य सौंपें

इसके बाद, प्रोजेक्ट में एक संसाधन जोड़ें और इसे पहले बनाए गए कार्य पर असाइन करें:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## चरण 3: विभिन्न रूपरेखाओं के साथ समयबद्ध डेटा उत्पन्न करें

अब, आइए संसाधन असाइनमेंट के लिए अलग-अलग रूपरेखाओं के साथ समयबद्ध डेटा तैयार करें:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## चरण 4: रूपरेखा बदलें और डेटा उत्पन्न करें

हम समोच्च प्रकार को बदल सकते हैं और तदनुसार समयबद्ध डेटा उत्पन्न कर सकते हैं। यहां कुछ उदाहरण दिए गए हैं:

```csharp
// रूपरेखा बदलें
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// समयबद्ध डेटा उत्पन्न करें और प्रिंट करें
// अन्य समोच्च प्रकारों के लिए इस चरण को दोहराएं
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks में असाइनमेंट के साथ कैसे काम करें। हमने विभिन्न रूपरेखाओं के साथ संसाधन असाइनमेंट समय-चरणीय डेटा उत्पन्न करने का पता लगाया। यह ज्ञान परियोजना प्रबंधन परिदृश्यों में बेहद उपयोगी हो सकता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अपने .NET एप्लिकेशन में कार्यों को शेड्यूल करने के लिए Aspose.Tasks का उपयोग कर सकता हूं?

A1: हां, Aspose.Tasks .NET अनुप्रयोगों में कार्य शेड्यूलिंग और प्रबंधन के लिए व्यापक एपीआई प्रदान करता है।

### Q2: क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उ2: हां, आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: क्या Aspose.Tasks में कार्यों या संसाधनों की संख्या पर कोई सीमाएँ हैं?

A3: Aspose.Tasks आपके प्रोजेक्ट में आपके द्वारा प्रबंधित किए जा सकने वाले कार्यों या संसाधनों की संख्या पर कोई सीमा नहीं लगाता है।

### Q4: क्या मैं Aspose.Tasks में संसाधन असाइनमेंट के लिए रूपरेखा को अनुकूलित कर सकता हूँ?

उ4: हाँ, जैसा कि इस ट्यूटोरियल में दिखाया गया है, आप अपनी परियोजना की आवश्यकताओं के अनुसार विभिन्न आकृतियाँ जैसे कछुआ, घंटी, चोटी इत्यादि सेट कर सकते हैं।

### Q5: Aspose.Tasks-संबंधित प्रश्नों के लिए मुझे समर्थन कहां मिल सकता है?

A5: आप पर समर्थन पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) जहां विशेषज्ञ और समुदाय के सदस्य सक्रिय रूप से चर्चा में शामिल होते हैं।