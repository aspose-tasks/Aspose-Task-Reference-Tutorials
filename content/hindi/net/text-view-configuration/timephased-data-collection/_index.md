---
title: Aspose.Tasks में समयबद्ध डेटा संग्रह में महारत हासिल करना
linktitle: Aspose.Tasks में समयबद्ध डेटा का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में समयबद्ध डेटा संग्रह का अन्वेषण करें। चरण-दर-चरण मार्गदर्शिका, अक्सर पूछे जाने वाले प्रश्न और बहुत कुछ। आज ही अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाएँ!
type: docs
weight: 15
url: /hi/net/text-view-configuration/timephased-data-collection/
---
## परिचय
क्या आप Aspose.Tasks का उपयोग करके अपने .NET अनुप्रयोगों में समय चरणबद्ध डेटा की शक्ति का उपयोग करना चाह रहे हैं? आगे कोई तलाश नहीं करें! यह व्यापक मार्गदर्शिका आपको .NET के लिए Aspose.Tasks के साथ समय-चरणबद्ध डेटा एकत्र करने की प्रक्रिया से गुजराएगी, यह सुनिश्चित करते हुए कि आप इस शक्तिशाली लाइब्रेरी का अधिकतम लाभ उठा सकें।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[Aspose.Tasks .NET दस्तावेज़ीकरण](https://reference.aspose.com/tasks/net/).
2. .NET विकास वातावरण: सुनिश्चित करें कि आपके पास एक कार्यशील .NET विकास वातावरण स्थापित है।
3. आपकी दस्तावेज़ निर्देशिका: कोड स्निपेट में प्लेसहोल्डर "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के पथ से बदलें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं का लाभ उठाने के लिए आवश्यक नामस्थान आयात करके शुरुआत करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. एक परियोजना और संसाधन बनाएँ
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. प्रोजेक्ट में कार्य जोड़ें
```csharp
var task = project.RootTask.Children.Add("Task 1");
// कार्य गुण सेट करें...
var task2 = project.RootTask.Children.Add("Task 2");
// कार्य2 गुण सेट करें...
```
## 3. कार्यों के लिए संसाधन निर्दिष्ट करें
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// असाइनमेंट गुण सेट करें...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// असाइनमेंट2 गुण सेट करें...
```
## 4. समय चरणबद्ध डेटा के साथ कार्य करें
```csharp
// समोच्च कार्य रूपरेखा सेट करें
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// जांचें कि क्या समयबद्ध डेटा संग्रह केवल पढ़ने के लिए है
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// उत्पन्न समय चरणबद्ध डेटा साफ़ करें
assignment.TimephasedData.Clear();
// समय चरणबद्ध डेटा बनाएं और जोड़ें
var td = new TimephasedData
{
    // समय चरणबद्ध डेटा गुण सेट करें...
};
assignment.TimephasedData.Add(td);
// समय चरणबद्ध डेटा की एक सूची जोड़ें
var list = new List<TimephasedData>();
// सूची में अधिक समय चरणबद्ध डेटा आइटम जोड़ें...
assignment.TimephasedData.AddRange(list);
// समय चरणबद्ध डेटा को प्रकार और दिनांक सीमा के अनुसार फ़िल्टर करें
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// फ़िल्टर किया गया समय चरणबद्ध डेटा प्रिंट करें...
```
## 5. समय चरणबद्ध डेटा में हेरफेर करें
```csharp
//गलत समय चरणबद्ध डेटा आइटम जोड़ें और फिर उसे हटा दें
var td4 = new TimephasedData
{
    // गलत समय चरणबद्ध डेटा गुण सेट करें...
};
assignment.TimephasedData.Add(td4);
// ग़लत समय चरणबद्ध डेटा आइटम हटाएँ
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// सभी समय चरणबद्ध आइटमों पर पुनरावृति करें
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // प्रिंट समय चरणबद्ध आइटम विवरण...
}
```
## 6. टाइमफ़ेज़्ड डेटा को दूसरे असाइनमेंट में कॉपी करें
```csharp
// समय चरणबद्ध डेटा को किसी अन्य असाइनमेंट में कॉपी करें
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// संग्रह को एक सादे सूची में बदलें
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// समय चरणबद्ध डेटा आइटम को एक-एक करके हटाएँ
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## निष्कर्ष
अंत में, इस ट्यूटोरियल ने .NET के लिए Aspose.Tasks का उपयोग करके समय-चरणबद्ध डेटा एकत्र करने का एक विस्तृत पूर्वाभ्यास प्रदान किया है। इन चरणों का पालन करके, आप प्रभावी समय ट्रैकिंग और संसाधन प्रबंधन को सक्षम करते हुए, इस कार्यक्षमता को अपनी परियोजनाओं में निर्बाध रूप से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य प्रोजेक्ट प्रबंधन टूल के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.Tasks को लोकप्रिय प्रोजेक्ट प्रबंधन टूल के साथ काम करने के लिए डिज़ाइन किया गया है और यह विभिन्न फ़ाइल स्वरूपों का समर्थन करता है।
### क्या Aspose.Tasks के साथ मेरे द्वारा प्रबंधित किये जा सकने वाले संसाधनों और कार्यों की संख्या की कोई सीमा है?
Aspose.Tasks विभिन्न आकारों की परियोजनाओं को संभालता है, और संसाधनों और कार्यों की संख्या पर कोई सख्त सीमा नहीं है।
### मैं .NET के लिए Aspose.Tasks से संबंधित किसी भी मुद्दे या प्रश्न के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 समर्थन के लिए, पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय से जुड़ने और सहायता प्राप्त करने के लिए।
### क्या मैं .NET खरीदने से पहले Aspose.Tasks को आज़मा सकता हूँ?
 हां, आप एक्सेस करके .NET के लिए Aspose.Tasks की सुविधाओं का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Tasks का लाइसेंस कहां से खरीद सकता हूं?
 आप .NET के लिए Aspose.Tasks का लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).