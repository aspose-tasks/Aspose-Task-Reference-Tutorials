---
title: Aspose.Tasks के साथ प्रोजेक्ट डेटा में महारत हासिल करना
linktitle: Aspose में प्रोजेक्ट डेटा के साथ कार्य करना। कार्य
second_title: Aspose.Tasks .NET API
description: जानें कि .NET में Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट डेटा में हेरफेर कैसे करें। आसानी से कार्य बनाएं, संसाधन जोड़ें और प्रोजेक्ट सहेजें।
type: docs
weight: 16
url: /hi/net/project-management-integration/project-data/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks लाइब्रेरी का उपयोग करके Microsoft प्रोजेक्ट डेटा के साथ कैसे काम किया जाए। Aspose.Tasks प्रोजेक्ट फ़ाइलों में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिसमें कार्य बनाना, संसाधन जोड़ना, गुण सेट करना और विभिन्न प्रारूपों में प्रोजेक्ट को सहेजना शामिल है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  Aspose.Tasks लाइब्रेरी की स्थापना: Aspose.Tasks लाइब्रेरी को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास एक .NET विकास परिवेश स्थापित है।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करें
Aspose.Tasks के साथ काम करने से पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट को आरंभ करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project();
```
 यह पंक्ति एक नए उदाहरण को आरंभ करती है`Project` वर्ग, जो एक Microsoft प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है।
## चरण 2: प्रोजेक्ट गुण सेट करें
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
ये पंक्तियाँ दर्शाती हैं कि प्रोजेक्ट के गुणों जैसे कार्य प्रारूप और कार्य निर्माण मोड को कैसे सेट किया जाए।
## चरण 3: कार्य जोड़ना
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
यहां, प्रोजेक्ट के मूल कार्य में "टास्क 1" नामक एक नया कार्य जोड़ा गया है।
## चरण 4: कार्य गुण सेट करना
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
ये पंक्तियाँ "कार्य 1" के लिए प्रारंभ तिथि, अवधि और समाप्ति तिथि निर्धारित करती हैं।
## चरण 5: संसाधन जोड़ना
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
यह भाग दर्शाता है कि प्रोजेक्ट में कार्य संसाधन कैसे जोड़ा जाए।
## चरण 6: कार्यों को संसाधन सौंपना
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
ये पंक्तियाँ दिखाती हैं कि पहले जोड़े गए कार्य संसाधन को विशिष्ट प्रारंभ, कार्य और समाप्ति तिथियों के साथ "कार्य 1" में कैसे निर्दिष्ट किया जाए।
## चरण 7: प्रोजेक्ट सहेजा जा रहा है
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
अंत में, प्रोजेक्ट को Microsoft Project XML फ़ाइल स्वरूप में सहेजा गया है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET में Aspose.Tasks लाइब्रेरी का उपयोग करके Microsoft प्रोजेक्ट डेटा के साथ कैसे काम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप प्रोजेक्ट फ़ाइलों में हेरफेर कर सकते हैं, कार्य, संसाधन जोड़ सकते हैं, कार्यों के लिए संसाधन निर्दिष्ट कर सकते हैं और परियोजनाओं को विभिन्न स्वरूपों में सहेज सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose. कार्य जटिल परियोजना संरचनाओं को संभाल सकते हैं?
उत्तर: हाँ, Aspose। कार्य जटिल परियोजना संरचनाओं के लिए व्यापक समर्थन प्रदान करता है, जिससे आप कार्यों, संसाधनों और असाइनमेंट को कुशलतापूर्वक प्रबंधित कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के विभिन्न संस्करणों के साथ संगत है?
उत्तर: Aspose.Tasks विभिन्न परिवेशों में अनुकूलता सुनिश्चित करते हुए, Microsoft प्रोजेक्ट संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है।
### प्रश्न: क्या मैं Aspose.Tasks को अन्य .NET लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?
उत्तर: बिल्कुल, Aspose। कार्य अन्य .NET पुस्तकालयों के साथ सहजता से एकीकृत होते हैं, जो आपके विकास परियोजनाओं में लचीलापन प्रदान करते हैं।
### प्रश्न: क्या Aspose.Tasks प्रोजेक्ट शेड्यूलिंग एल्गोरिदम के लिए समर्थन प्रदान करता है?
उत्तर: हां, Aspose.Tasks में आपको प्रोजेक्ट टाइमलाइन और संसाधन उपयोग को अनुकूलित करने में मदद करने के लिए उन्नत शेड्यूलिंग एल्गोरिदम शामिल हैं।
### प्रश्न: क्या Aspose.Tasks उपयोगकर्ताओं के लिए कोई सामुदायिक मंच है?
 उत्तर: हाँ, आप सहायक संसाधन पा सकते हैं और अन्य Aspose के साथ जुड़ सकते हैं। उपयोगकर्ताओं पर कार्य करता है[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).