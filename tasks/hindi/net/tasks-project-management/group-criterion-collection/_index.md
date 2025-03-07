---
title: Aspose.Tasks के साथ MS प्रोजेक्ट ग्रुप मानदंड प्रबंधित करें
linktitle: Aspose.Tasks में समूह मानदंड संग्रह का प्रबंधन करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके समूह मानदंड MS प्रोजेक्ट संग्रह को प्रबंधित करना सीखें। डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका.
weight: 28
url: /hi/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ MS प्रोजेक्ट ग्रुप मानदंड प्रबंधित करें

## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके MS प्रोजेक्ट के भीतर समूह मानदंड संग्रह को प्रबंधित करने का तरीका जानेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1.  .NET के लिए Aspose.Tasks: सुनिश्चित करें कि आपके .NET प्रोजेक्ट में Aspose.Tasks लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).

2. माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल: काम करने के लिए एक माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल (एमपीपी) तैयार रखें।

## नामस्थान आयात करें

सबसे पहले, आपको अपने C# कोड में आवश्यक नामस्थान आयात करने की आवश्यकता है। Aspose.Tasks द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए यह चरण महत्वपूर्ण है।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

 आरंभ करें a`Project` एमपीपी फ़ाइल लोड करके ऑब्जेक्ट करें। 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## चरण 2: समूह मानदंड तक पहुंचें

प्रोजेक्ट से समूह को पुनः प्राप्त करें और उसके मानदंडों तक पहुंचें।

```csharp
var group = project.TaskGroups.ToList()[0];
```

## चरण 3: समूह मानदंड पर पुनरावृति करें

समूह में प्रत्येक मानदंड को लूप करें और उसके गुण प्रदर्शित करें।

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## चरण 4: समूह मानदंड साफ़ करें

यदि मौजूदा समूह मानदंड केवल पढ़ने योग्य नहीं है तो उसे साफ़ करें।

```csharp
group.GroupCriteria.Clear();
```

## चरण 5: नया मानदंड जोड़ें

एक नया समूह मानदंड बनाएं और उसे समूह में जोड़ें।

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## चरण 6: मानदंड को दूसरे समूह में कॉपी करें

मानदंड को एक समूह से दूसरे समूह में कॉपी करें।

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके ग्रुप क्राइटेरियन MS प्रोजेक्ट संग्रह को कैसे प्रबंधित किया जाए। इन चरणों का पालन करके, आप प्रोग्रामेटिक रूप से अपनी Microsoft प्रोजेक्ट फ़ाइलों के भीतर समूह मानदंड को प्रभावी ढंग से हेरफेर कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks Microsoft प्रोजेक्ट के सभी संस्करणों के साथ संगत है?

उत्तर: हाँ, Aspose.Tasks 2003, 2007, 2010, 2013 और 2016 सहित विभिन्न संस्करणों की Microsoft प्रोजेक्ट फ़ाइलों का समर्थन करता है।

### Q2: क्या मैं एक ही समूह के लिए अनेक मानदंड लागू कर सकता हूँ?

उ: बिल्कुल, आप प्रत्येक को दोहराकर और तदनुसार जोड़कर एक समूह में कई मानदंड जोड़ सकते हैं।

### Q3: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

 उत्तर: हाँ, आप Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मुझे Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?

 उत्तर: आप दस्तावेज़ का संदर्भ ले सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).

### Q5: यदि मुझे कोई समस्या आती है तो मुझे सहायता कैसे मिल सकती है?

 उत्तर: यदि आपके कोई प्रश्न हैं या किसी समस्या का सामना करना पड़ता है, तो आप Aspose.Tasks फोरम से समर्थन मांग सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
