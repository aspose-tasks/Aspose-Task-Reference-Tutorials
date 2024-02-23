---
title: Aspose.Tasks में उपलब्धता अवधि का संग्रह
linktitle: Aspose.Tasks में उपलब्धता अवधि का संग्रह
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में संसाधनों की उपलब्धता अवधि कैसे प्रबंधित करें। यह चरण-दर-चरण ट्यूटोरियल प्रभावी परियोजना संसाधन नियोजन सुनिश्चित करते हुए, उपलब्धता अवधि जोड़ने, अपडेट करने और हटाने में आपका मार्गदर्शन करता है।
type: docs
weight: 18
url: /hi/net/advanced-features/availability-period-collection/
---
## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks में किसी संसाधन की उपलब्धता अवधि संग्रह के साथ कैसे काम किया जाए। परियोजना प्रबंधन के लिए उपलब्धता अवधि का प्रबंधन करना महत्वपूर्ण है, जिससे हमें यह परिभाषित करने की अनुमति मिलती है कि किसी परियोजना के कार्यों के लिए संसाधन कब उपलब्ध हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. बुनियादी समझ: C# और .NET ढांचे से परिचित होना।

## नामस्थान आयात करें

सबसे पहले, हमें अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने की आवश्यकता है:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

आइए उदाहरण कोड को कई चरणों में विभाजित करें और प्रत्येक भाग को समझें:

## चरण 1: परियोजना और संसाधन को प्रारंभ करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

यहां, हम एक प्रोजेक्ट फ़ाइल लोड कर रहे हैं और उसकी आईडी द्वारा एक विशिष्ट संसाधन प्राप्त कर रहे हैं।

## चरण 2: मौजूदा उपलब्धता अवधि साफ़ करें

```csharp
resource.AvailabilityPeriods.Clear();
```

हम संसाधन से जुड़ी किसी भी मौजूदा उपलब्धता अवधि को साफ़ कर देते हैं।

## चरण 3: उपलब्धता अवधि जोड़ें

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

हम उपलब्धता अवधियों के संग्रह के माध्यम से पुनरावृत्ति करते हैं और उन्हें संसाधन में जोड़ते हैं।

## चरण 4: एक नई उपलब्धता अवधि डालें

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

हम वर्ष 2013 के लिए एक नई उपलब्धता अवधि बनाते हैं और इसे संग्रह में सम्मिलित करते हैं।

## चरण 5: उपलब्धता अवधि प्रदर्शित करें

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

हम संसाधन से जुड़ी प्रत्येक उपलब्धता अवधि की गिनती और विवरण प्रिंट करते हैं।

## चरण 6: उपलब्धता अवधि को किसी अन्य संसाधन पर कॉपी करें

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

हम उपलब्धता अवधि को एक संसाधन से दूसरे संसाधन में कॉपी करते हैं।

## चरण 7: उपलब्धता अवधि को अद्यतन करें और हटाएँ

```csharp
// किसी विशिष्ट अवधि के लिए उपलब्ध इकाइयों को अद्यतन करें
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// एक विशिष्ट अवधि निकालें
otherResource.AvailabilityPeriods.Remove(period2013);
```

हम एक अवधि के लिए उपलब्ध इकाइयों को अद्यतन करते हैं और संग्रह से विशिष्ट अवधियों को हटा देते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Tasks में उपलब्धता अवधि संग्रह के साथ कैसे काम किया जाए। प्रभावी परियोजना योजना और कार्यान्वयन के लिए संसाधन उपलब्धता का प्रबंधन आवश्यक है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं उपलब्धता अवधि में कस्टम फ़ील्ड जोड़ सकता हूँ?

A1: नहीं, .NET के लिए Aspose.Tasks में उपलब्धता अवधि कस्टम फ़ील्ड का समर्थन नहीं करती है।

### Q2: क्या उपलब्धता अवधि विशिष्ट कार्यों से जुड़ी हुई है?

उ2: नहीं, उपलब्धता अवधि संसाधनों से जुड़ी होती है और यह परिभाषित करती है कि वे सामान्य रूप से कार्यों के लिए कब उपलब्ध हैं।

### Q3: क्या मैं बाहरी स्रोतों से उपलब्धता अवधि आयात कर सकता हूँ?

A3: हाँ, आप .NET API के लिए Aspose.Tasks का उपयोग करके विभिन्न डेटा स्रोतों से उपलब्धता अवधि आयात कर सकते हैं।

### Q4: मैं ओवरलैपिंग उपलब्धता अवधियों को कैसे प्रबंधित करूं?

A4: .NET के लिए Aspose.Tasks ओवरलैपिंग अवधियों को संभालने के लिए अंतर्निहित तंत्र प्रदान नहीं करता है। ऐसे परिदृश्यों को प्रबंधित करने के लिए आपको कस्टम तर्क लागू करने की आवश्यकता हो सकती है।

### Q5: क्या किसी संसाधन की उपलब्धता अवधि की संख्या की कोई सीमा है?

A5: किसी संसाधन की उपलब्धता अवधि की संख्या की कोई पूर्वनिर्धारित सीमा नहीं है, लेकिन बड़ी संख्या में अवधियों के साथ प्रदर्शन ख़राब हो सकता है।