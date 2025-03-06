---
title: Aspose.Tasks में संसाधन असाइनमेंट का संग्रह
linktitle: Aspose.Tasks में संसाधन असाइनमेंट का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में संसाधन असाइनमेंट प्रबंधित करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण ट्यूटोरियल।
weight: 12
url: /hi/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में संसाधन असाइनमेंट का संग्रह

## परिचय
.NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में संसाधन असाइनमेंट प्रबंधित करने पर इस व्यापक ट्यूटोरियल में आपका स्वागत है। इस ट्यूटोरियल में, हम चरण दर चरण प्रक्रिया का गहराई से अध्ययन करेंगे, जिससे यह सुनिश्चित होगा कि आपको संसाधन असाइनमेंट में कुशलतापूर्वक हेरफेर करने की ठोस समझ हो। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह मार्गदर्शिका आपको वह सब कुछ बताएगी जो आपको जानना आवश्यक है।
## आवश्यक शर्तें
इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप है:
1.  .NET के लिए Aspose.Tasks स्थापित: सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित हैं। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. C# का बुनियादी ज्ञान: यह ट्यूटोरियल मानता है कि आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ है।
3. Microsoft प्रोजेक्ट फ़ाइल: परीक्षण उद्देश्यों के लिए Microsoft प्रोजेक्ट फ़ाइल तैयार रखें। यदि आपके पास एक नहीं है, तो आप एक नमूना फ़ाइल बना सकते हैं।

## नामस्थान आयात करें
सबसे पहले, आइए आवश्यक नामस्थान आयात करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
Microsoft प्रोजेक्ट फ़ाइल लोड करके प्रारंभ करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## चरण 2: कार्य और संसाधन जोड़ें
अब, प्रोजेक्ट में एक कार्य और एक संसाधन जोड़ें:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## चरण 3: कार्य को संसाधन सौंपें
इसके बाद, हम कार्य के लिए संसाधन निर्दिष्ट करेंगे:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## चरण 4: विभिन्न प्रकार के असाइनमेंट के साथ कार्य करना
आप इकाइयों या लागतों वाले असाइनमेंट के साथ भी काम कर सकते हैं:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// चरण 3 में दिखाए अनुसार इकाइयों और लागतों के साथ असाइनमेंट के लिए गुण सेट करें
```
## चरण 5: असाइनमेंट प्रिंट करें
प्रोजेक्ट के लिए असाइनमेंट प्रिंट करें:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // असाइनमेंट विवरण प्रिंट करें
}
```
## चरण 6: यूआईडी द्वारा असाइनमेंट पुनः प्राप्त करें
आप यूआईडी द्वारा असाइनमेंट पुनः प्राप्त कर सकते हैं:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## चरण 7: केवल पढ़ने योग्य स्थिति की जाँच करें
सत्यापित करें कि संसाधन असाइनमेंट संग्रह केवल पढ़ने के लिए है:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## चरण 8: संग्रह को सूची और पुनरावृति में बदलें
संग्रह को एक सूची में बदलें और उस पर पुनरावृति करें:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## निष्कर्ष
बधाई हो! आपने सीखा है कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में संसाधन असाइनमेंट कैसे प्रबंधित करें। इन चरणों का पालन करके, आप कार्यों और संसाधनों में कुशलतापूर्वक हेरफेर कर सकते हैं, जिससे परियोजना प्रबंधन आसान हो जाएगा।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उ: हां, .NET के लिए Aspose.Tasks एमपीपी, एमपीटी और एक्सएमएल प्रारूपों सहित माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks खरीदने से पहले कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: यदि .NET के लिए Aspose.Tasks का उपयोग करते समय मुझे कोई समस्या आती है तो मैं कैसे समर्थन प्राप्त कर सकता हूं?
 उत्तर: आप Aspose.Tasks फोरम से समर्थन मांग सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस का उपयोग कर सकता हूँ?
 उत्तर: हां, मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप यहां से एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं .NET के लिए Aspose.Tasks का पूर्ण लाइसेंस कहां से खरीद सकता हूं?
 उ: आप Aspose ऑनलाइन स्टोर से पूर्ण लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
