---
title: Aspose.Tasks में उन्नत और संचालन
linktitle: Aspose.Tasks में उन्नत और संचालन
second_title: Aspose.Tasks .NET API
description: कई मानदंडों के आधार पर प्रोजेक्ट कार्यों को कुशलतापूर्वक फ़िल्टर करने के लिए .NET के लिए Aspose.Tasks में उन्नत और संचालन करना सीखें।
weight: 10
url: /hi/net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में उन्नत और संचालन

## परिचय

 इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks में उन्नत AND ऑपरेशन के बारे में विस्तार से जानेंगे, जो कार्यों और परियोजनाओं के प्रबंधन के लिए एक शक्तिशाली उपकरण है। हम यह पता लगाएंगे कि इसका उपयोग करके कई स्थितियों के आधार पर प्रोजेक्ट कार्यों को कैसे फ़िल्टर किया जाए`Util.And` कक्षा।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
2.  .NET के लिए Aspose.Tasks स्थापित किया गया। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. एकीकृत विकास वातावरण (आईडीई) जैसे विजुअल स्टूडियो।

## नामस्थान आयात करें

सबसे पहले, आइए अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## चरण 1: प्रोजेक्ट प्रारंभ करें और कार्य एकत्रित करें

एक नया Aspose.Tasks प्रोजेक्ट आरंभ करके और उसमें सभी कार्यों को एकत्रित करके शुरुआत करें:

```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## चरण 2: फ़िल्टर शर्तों को परिभाषित करें

इसके बाद, फ़िल्टर शर्तों को परिभाषित करें। इस उदाहरण के लिए, हम दो स्थितियाँ बनाएंगे: एक सारांश कार्यों को फ़िल्टर करने के लिए और दूसरी गैर-शून्य कार्यों को फ़िल्टर करने के लिए:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## चरण 3: शर्तों को AND संचालन के साथ संयोजित करें

 अब, का उपयोग करके शर्तों को संयोजित करें`Util.And` एक समग्र स्थिति बनाने के लिए कक्षा:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## चरण 4: शर्त लागू करें और कार्य फ़िल्टर करें

एकत्रित कार्यों पर संयुक्त शर्त लागू करें और तदनुसार उन्हें फ़िल्टर करें:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## चरण 5: आउटपुट फ़िल्टर किए गए कार्य

अंत में, फ़िल्टर किए गए कार्यों को आउटपुट करें:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // अतिरिक्त प्रसंस्करण यहां किया जा सकता है
}
```

## निष्कर्ष

 इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks में उन्नत और संचालन कैसे करें। का उपयोग करके शर्तों को संयोजित करके`Util.And`वर्ग, हम कई मानदंडों के आधार पर कार्यों को कुशलतापूर्वक फ़िल्टर कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Tasks क्या है?

उ: .NET के लिए Aspose.Tasks एक मजबूत एपीआई है जो डेवलपर्स को .NET अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है।

### Q2: क्या मैं Util.And का उपयोग करके दो से अधिक शर्तें लागू कर सकता हूँ?

उत्तर: हाँ, Util.And का उपयोग जटिल फ़िल्टरिंग मानदंड बनाने के लिए किसी भी संख्या में स्थितियों को संयोजित करने के लिए किया जा सकता है।

### Q3: क्या .NET के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उत्तर: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मुझे .NET के लिए Aspose.Tasks के लिए दस्तावेज़ कहां मिल सकते हैं?

 उत्तर: आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).

### Q5: मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?

उत्तर: आप Aspose.Tasks समुदाय मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
