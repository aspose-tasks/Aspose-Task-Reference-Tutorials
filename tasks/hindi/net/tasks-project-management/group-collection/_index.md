---
title: Aspose.Tasks में प्रोजेक्ट संग्रह का प्रबंधन करना
linktitle: Aspose.Tasks में समूह संग्रह का प्रबंधन करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संग्रहों को कुशलतापूर्वक प्रबंधित करना सीखें। हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें.
weight: 26
url: /hi/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में प्रोजेक्ट संग्रह का प्रबंधन करना

## परिचय
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके समूह MS प्रोजेक्ट संग्रहों को कैसे प्रबंधित किया जाए। आपके प्रोजेक्ट के भीतर कार्यों और संसाधनों को कुशलतापूर्वक व्यवस्थित करने और हेरफेर करने के लिए समूह संग्रह का प्रबंधन करना महत्वपूर्ण है।
## आवश्यक शर्तें
इस ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
2. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें क्योंकि इस ट्यूटोरियल में C# में कोडिंग शामिल है।
3. विकास परिवेश: एक विकास परिवेश स्थापित करें जैसे विज़ुअल स्टूडियो या कोई अन्य आईडीई जो .NET विकास का समर्थन करता हो।

## नामस्थान आयात करें
सबसे पहले, आइए अपने C# कोड में Aspose.Tasks कार्यात्मकताओं के साथ काम करने के लिए आवश्यक नामस्थान आयात करें।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## चरण 1: प्रोजेक्ट लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
इस चरण में MS प्रोजेक्ट फ़ाइल को Aspose.Tasks प्रोजेक्ट ऑब्जेक्ट में लोड करना शामिल है, जिससे हमें उस पर संचालन करने की अनुमति मिलती है।
## चरण 2: कार्य समूहों पर पुनरावृति करें
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
यहां, हम प्रोजेक्ट के भीतर कार्य समूहों पर पुनरावृत्ति करते हैं, प्रत्येक समूह के लिए मेनू में अनुक्रमणिका, नाम और दृश्यता जैसे विवरण प्रिंट करते हैं।
## चरण 3: संसाधन समूहों पर पुनरावृति करें
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
इसी प्रकार, यह चरण मेनू में उनके सूचकांक, नाम और दृश्यता को प्रदर्शित करते हुए संसाधन समूहों पर पुनरावृत्त होता है।
## चरण 4: समूहों को साफ़ करें और दूसरे प्रोजेक्ट में कॉपी करें
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// अन्य प्रोजेक्ट के समूह साफ़ करें
otherProject.TaskGroups.Clear();
// समूहों को अन्य प्रोजेक्ट में कॉपी करें
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
यहां, हम किसी अन्य प्रोजेक्ट के समूहों को साफ़ करते हैं और फिर मूल प्रोजेक्ट से समूहों को उसमें कॉपी करते हैं।
## चरण 5: एक कस्टम कार्य समूह जोड़ें
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
इस चरण में, हम एक कस्टम कार्य समूह बनाते हैं और यदि यह पहले से मौजूद नहीं है तो इसे दूसरे प्रोजेक्ट में जोड़ते हैं।
## चरण 6: सभी समूह हटाएँ
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
अंत में, हम अन्य प्रोजेक्ट से सभी समूहों को हटा देते हैं।

## निष्कर्ष
.NET के लिए Aspose.Tasks में समूह MS प्रोजेक्ट संग्रहों को प्रबंधित करना प्रोजेक्ट डेटा को कुशलतापूर्वक व्यवस्थित करने और हेरफेर करने के लिए आवश्यक है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप समग्र परियोजना प्रबंधन में सुधार करते हुए, अपनी परियोजनाओं के भीतर कार्य और संसाधन समूहों को प्रभावी ढंग से संभाल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए Aspose.Tasks MS प्रोजेक्ट के सभी संस्करणों के साथ संगत है?
.NET के लिए Aspose.Tasks 2003, 2007, 2010, 2013, 2016 और 2019 सहित Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।
### क्या मैं .NET के लिए Aspose.Tasks का उपयोग करके समूह गुणों को अनुकूलित कर सकता हूँ?
हाँ, आप .NET के लिए Aspose.Tasks का उपयोग करके समूह गुणों जैसे नाम और दृश्यता को अनुकूलित कर सकते हैं।
### क्या .NET के लिए Aspose.Tasks क्रॉस-प्लेटफ़ॉर्म संगतता प्रदान करता है?
.NET के लिए Aspose.Tasks मुख्य रूप से .NET फ्रेमवर्क को लक्षित करता है, लेकिन इसका उपयोग .NET कोर और .NET मानक के साथ क्रॉस-प्लेटफ़ॉर्म परिदृश्यों में किया जा सकता है।
### मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप .NET के लिए Aspose.Tasks के लिए समर्थन प्राप्त कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
### क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
