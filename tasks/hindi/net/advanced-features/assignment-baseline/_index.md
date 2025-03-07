---
title: Aspose.Tasks में असाइनमेंट बेसलाइन का प्रबंधन
linktitle: Aspose.Tasks में असाइनमेंट बेसलाइन का प्रबंधन
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट प्रगति और प्रदर्शन की सटीक ट्रैकिंग सुनिश्चित करते हुए, .NET के लिए Aspose.Tasks के साथ असाइनमेंट बेसलाइन को कुशलतापूर्वक प्रबंधित करना सीखें।
weight: 14
url: /hi/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में असाइनमेंट बेसलाइन का प्रबंधन

## परिचय

परियोजना प्रबंधन कार्यों पर काम करते समय, प्रगति को सटीक रूप से ट्रैक करने के लिए असाइनमेंट बेसलाइन का प्रबंधन करना महत्वपूर्ण है। .NET के लिए Aspose.Tasks असाइनमेंट बेसलाइन को कुशलतापूर्वक संभालने के लिए टूल का एक व्यापक सेट प्रदान करता है। इस ट्यूटोरियल में, हम चरण दर चरण असाइनमेंट बेसलाइन प्रबंधित करने की प्रक्रिया के बारे में विस्तार से जानेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
- .NET लाइब्रेरी के लिए Aspose.Tasks आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
- एमपीपी प्रारूप में एक परियोजना फ़ाइल तक पहुंच।

## नामस्थान आयात करें

Aspose.Tasks के साथ काम करना शुरू करने के लिए, आपको अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना होगा। अपनी C# फ़ाइल की शुरुआत में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Tasks;
using System;


```

## चरण 1: प्रोजेक्ट लोड करें और बेसलाइन सेट करें

 सबसे पहले, का उपयोग करके प्रोजेक्ट फ़ाइल लोड करें`Project` Aspose.Tasks से कक्षा। फिर, का उपयोग करके प्रोजेक्ट के लिए बेसलाइन प्रकार सेट करें`SetBaseline` तरीका।

```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## चरण 2: असाइनमेंट बेसलाइन जानकारी पढ़ें

प्रोजेक्ट में प्रत्येक संसाधन असाइनमेंट के माध्यम से पुनरावृत्ति करें और प्रत्येक असाइनमेंट के लिए आधारभूत जानकारी पुनः प्राप्त करें।

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## चरण 3: आधारभूत समानता की जाँच करें

Aspose.Tasks द्वारा प्रदान की गई विभिन्न तुलना विधियों का उपयोग करके विभिन्न असाइनमेंट के लिए आधारभूत जानकारी की तुलना करें।

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// आधारभूत समानता की जाँच करें
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// आधारभूत तुलना की जाँच करें
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// बेसलाइन हैशकोड प्रदर्शित करें
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## निष्कर्ष

असाइनमेंट बेसलाइन का प्रबंधन करना परियोजना प्रबंधन का अभिन्न अंग है, जो प्रगति और प्रदर्शन की सटीक ट्रैकिंग की अनुमति देता है। .NET के लिए Aspose.Tasks के साथ, असाइनमेंट बेसलाइन को संभालना सुव्यवस्थित और कुशल हो जाता है, जिससे डेवलपर्स को प्रोजेक्ट प्रबंधन वर्कफ़्लो को बढ़ाने के लिए शक्तिशाली टूल मिलते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks एक ही असाइनमेंट के लिए एकाधिक आधार रेखाओं को संभाल सकता है?

A1: हाँ, Aspose.Tasks प्रत्येक असाइनमेंट के लिए कई आधार रेखाओं का समर्थन करता है, जिससे समय के साथ परियोजना की प्रगति की व्यापक ट्रैकिंग की अनुमति मिलती है।

### Q2: क्या Aspose.Tasks MPP के अलावा विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों के साथ संगत है?

A2: हां, Aspose.Tasks XML, MPX और MPP सहित प्रोजेक्ट फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जो विभिन्न प्रोजेक्ट प्रबंधन टूल के साथ संगतता सुनिश्चित करता है।

### Q3: क्या मैं Aspose.Tasks का उपयोग करके आधारभूत जानकारी को प्रोग्रामेटिक रूप से संशोधित कर सकता हूँ?

A3: बिल्कुल, Aspose.Tasks परियोजना की आवश्यकताओं के अनुसार आधारभूत जानकारी को गतिशील रूप से संशोधित करने के लिए व्यापक एपीआई प्रदान करता है, जो परियोजना प्रबंधन प्रक्रियाओं पर लचीलापन और नियंत्रण प्रदान करता है।

### Q4: क्या Aspose.Tasks डेवलपर्स के लिए दस्तावेज़ीकरण और समर्थन संसाधन प्रदान करता है?

A4: हां, डेवलपर्स Aspose.Tasks वेबसाइट पर व्यापक दस्तावेज़, ट्यूटोरियल और फ़ोरम तक पहुंच सकते हैं, जिससे सुचारू एकीकरण और समस्या निवारण की सुविधा मिलती है।

### Q5: क्या .NET के लिए Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

 A5: हां, डेवलपर्स .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/), जिससे उन्हें खरीदारी का निर्णय लेने से पहले इसकी विशेषताओं और क्षमताओं का मूल्यांकन करने की अनुमति मिलती है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
