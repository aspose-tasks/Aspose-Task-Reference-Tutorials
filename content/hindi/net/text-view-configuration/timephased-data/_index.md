---
title: .NET के लिए Aspose.Tasks के साथ मास्टर टाइमफ़ेज़्ड डेटा हैंडलिंग
linktitle: Aspose.Tasks में समयबद्ध डेटा को संभालना
second_title: Aspose.Tasks .NET API
description: समय-चरणबद्ध डेटा को आसानी से संभालने, परियोजना योजना को बढ़ाने और संसाधन प्रबंधन को अनुकूलित करने के लिए .NET के लिए Aspose.Tasks का अन्वेषण करें। #असपोज़ #कार्य #एमएसप्रोजेक्ट
type: docs
weight: 14
url: /hi/net/text-view-configuration/timephased-data/
---
## परिचय
परियोजना प्रबंधन की दुनिया में, संसाधन आवंटन, लागत अनुमान और समग्र परियोजना योजना के लिए समय-चरणबद्ध डेटा का प्रभावी प्रबंधन महत्वपूर्ण है। .NET के लिए Aspose.Tasks कस्टम समय चरणबद्ध डेटा के साथ निर्बाध रूप से काम करने के लिए एक शक्तिशाली समाधान प्रदान करता है। यह ट्यूटोरियल आपको Aspose.कार्यों का उपयोग करके समय-चरणबद्ध डेटा को संभालने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा, जिससे आप अपनी परियोजनाओं में संसाधन प्रबंधन को अनुकूलित कर सकेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- परियोजना प्रबंधन अवधारणाओं की बुनियादी समझ।
-  .NET के लिए Aspose.Tasks स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
- दिए गए उदाहरणों को लागू करने के लिए विज़ुअल स्टूडियो जैसा एक कोड संपादक।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं का लाभ उठाने के लिए आवश्यक नामस्थान आयात करना सुनिश्चित करें। अपनी कोड फ़ाइल की शुरुआत में निम्नलिखित पंक्तियाँ जोड़ें:
```csharp
    using Aspose.Tasks;
    using System;
    
```
अब, आइए Aspose.Tasks का उपयोग करके समय चरणबद्ध डेटा को संभालने में आपका मार्गदर्शन करने के लिए दिए गए उदाहरण को कई चरणों में विभाजित करें:
## चरण 1: प्रोजेक्ट सेट करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
यहां, हम एक नया प्रोजेक्ट आरंभ करते हैं और उसका गणना मोड सेट करते हैं।
## चरण 2: संसाधनों और कार्यों को परिभाषित करें
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
एक परियोजना संरचना का अनुकरण करने के लिए कार्य और लागत संसाधन, साथ ही एक कार्य बनाएं।
## चरण 3: कार्य के लिए संसाधन निर्दिष्ट करें
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
कार्य को कार्य और लागत संसाधन सौंपें।
## चरण 4: कस्टम समय चरणबद्ध डेटा जोड़ें
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// लागत असाइनमेंट के लिए समान चरण
costAssignment.TimephasedData.Clear();
```
कार्य और लागत असाइनमेंट दोनों के लिए कस्टम समय चरणबद्ध डेटा जोड़ें।
## चरण 5: समय चरणबद्ध डेटा प्रदर्शित करें
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // प्रत्येक बार चरणबद्ध डेटा प्रविष्टि के बारे में प्रासंगिक जानकारी प्रदर्शित करें
    }
}
```
अंत में, प्रत्येक असाइनमेंट के लिए समय चरणबद्ध डेटा प्रदर्शित करें।
#
## निष्कर्ष
Aspose में समयबद्ध डेटा को प्रभावी ढंग से प्रबंधित करना। कार्य विस्तृत परियोजना योजना और संसाधन प्रबंधन के लिए नई संभावनाएं खोलते हैं। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने सीखा है कि अपनी परियोजनाओं की विशिष्ट आवश्यकताओं को पूरा करने के लिए समय-चरणबद्ध डेटा में हेरफेर कैसे करें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य प्रोजेक्ट प्रबंधन टूल के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
Aspose.Tasks मुख्य रूप से .NET विकास के लिए डिज़ाइन किया गया है। हालाँकि, इसकी कार्यक्षमताएँ विभिन्न परियोजना प्रबंधन उपकरणों की पूरक हो सकती हैं।
### क्या .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण उपलब्ध है?
 हां, आप नि:शुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15)सामुदायिक समर्थन के लिए.
### अस्थायी लाइसेंस क्या है और मैं इसे कैसे प्राप्त कर सकता हूँ?
 अस्थायी लाइसेंस के बारे में जानें[यहाँ](https://purchase.aspose.com/temporary-license/).
### मुझे .NET के लिए Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?
 व्यापक का संदर्भ लें[प्रलेखन](https://reference.aspose.com/tasks/net/) विस्तृत जानकारी के लिए.