---
title: Aspose.Tasks में MS प्रोजेक्ट विशेषताएँ संग्रह प्रबंधित करें
linktitle: Aspose.Tasks में विस्तारित विशेषता संग्रह का प्रबंधन
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट विस्तारित विशेषताओं को कुशलतापूर्वक प्रबंधित करना सीखें। चरण-दर-चरण मार्गदर्शन के साथ कार्य विशेषताओं में निर्बाध रूप से हेरफेर करें।
type: docs
weight: 12
url: /hi/net/tasks-project-management/extended-attribute-collection/
---
## परिचय
क्या आप .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट विस्तारित विशेषताओं को कुशलतापूर्वक प्रबंधित करना चाहते हैं? इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में मार्गदर्शन देंगे। आइए गोता लगाएँ!
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. विजुअल स्टूडियो: अपने सिस्टम पर विजुअल स्टूडियो इंस्टॉल करें।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।

## नामस्थान आयात करें
अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, निम्नलिखित कोड स्निपेट का उपयोग करके एमएस प्रोजेक्ट फ़ाइल लोड करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## चरण 2: कार्य और विस्तारित विशेषताओं तक पहुंचें
किसी विशिष्ट कार्य और उसकी विस्तारित विशेषताओं तक पहुँचें:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## चरण 3: विस्तारित विशेषताएँ साफ़ करें
यदि आवश्यक हो तो मौजूदा विस्तारित विशेषताओं को साफ़ करें:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## चरण 4: विस्तारित विशेषता परिभाषाएँ बनाएँ
नई विस्तारित विशेषताओं के लिए परिभाषाएँ बनाएँ:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## चरण 5: कार्य विस्तारित विशेषताओं पर पुनरावृति
कार्य विस्तारित विशेषताओं पर पुनरावृति:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## चरण 6: विस्तारित विशेषताएँ जोड़ें
कार्य में नई विस्तारित विशेषताएँ जोड़ें:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## चरण 7: विस्तारित विशेषताओं के साथ कार्य करें
आवश्यकतानुसार विस्तारित विशेषताओं पर संचालन करें।
## चरण 8: विस्तारित विशेषताएँ हटाएँ
अनुक्रमणिका या सशर्त रूप से विस्तारित विशेषताएँ हटाएँ:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## चरण 9: विशेषताओं को किसी अन्य कार्य में कॉपी करें
समान या भिन्न प्रोजेक्ट के अंतर्गत किसी अन्य कार्य में विशेषताएँ कॉपी करें:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## निष्कर्ष
.NET के लिए Aspose.Tasks के साथ MS प्रोजेक्ट विस्तारित विशेषता संग्रह को प्रबंधित करना सहज हो जाता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाते हुए, विस्तारित विशेषताओं को कुशलतापूर्वक संभाल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अनेक परियोजनाओं में विस्तारित विशेषताओं में हेरफेर कर सकता हूँ?
उ: हाँ, आप .NET के लिए Aspose.Tasks का उपयोग करके विभिन्न परियोजनाओं में कार्यों के बीच विस्तारित विशेषताओं की प्रतिलिपि बना सकते हैं।
### प्रश्न: क्या प्रति कार्य विस्तारित विशेषताओं की संख्या पर कोई सीमाएँ हैं?
उत्तर: .NET के लिए Aspose.Tasks प्रति कार्य विस्तारित विशेषताओं की संख्या पर कोई अंतर्निहित सीमा नहीं लगाता है।
### प्रश्न: क्या मैं कस्टम विस्तारित विशेषता फ़ील्ड बना सकता हूँ?
उत्तर: बिल्कुल! .NET के लिए Aspose.Tasks आपको अपनी परियोजना आवश्यकताओं के अनुरूप कस्टम विस्तारित विशेषता फ़ील्ड को परिभाषित करने की अनुमति देता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks विभिन्न संस्करणों की MS प्रोजेक्ट फ़ाइलों को पढ़ने और लिखने का समर्थन करता है?
उत्तर: हाँ, .NET के लिए Aspose.Tasks विभिन्न संस्करणों में MS प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).