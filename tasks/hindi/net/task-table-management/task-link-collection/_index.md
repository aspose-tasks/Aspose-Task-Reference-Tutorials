---
title: Aspose.Tasks में कार्य लिंक को संभालना
linktitle: Aspose.Tasks में कार्य लिंक को संभालना
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट कार्य लिंक को कुशलतापूर्वक प्रबंधित करने में .NET के लिए Aspose.Tasks की शक्ति का अन्वेषण करें। अपने प्रोजेक्ट प्रबंधन अनुभव को बेहतर बनाने के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 19
url: /hi/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य लिंक को संभालना

## परिचय
.NET के लिए Aspose.Tasks में कार्य लिंक को संभालने के लिए चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है! कार्य लिंक परियोजना प्रबंधन में महत्वपूर्ण भूमिका निभाते हैं, जिससे आप कार्यों के बीच संबंध स्थापित कर सकते हैं और निर्भरताएँ बना सकते हैं। इस ट्यूटोरियल में, हम आपको Aspose.Tasks का उपयोग करके कार्य लिंक संग्रह के साथ काम करने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी को डाउनलोड और इंस्टॉल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. नमूना प्रोजेक्ट फ़ाइल: उदाहरणों के साथ अनुसरण करने के लिए एक नमूना प्रोजेक्ट फ़ाइल (उदाहरण के लिए, "SampleProject.mpp") तैयार करें।
अब, चलिए शुरू करें!
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करना सुनिश्चित करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: प्रोजेक्ट लोड करें और कार्यों तक पहुंचें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
// प्रोजेक्ट लोड करें
var project = new Project(DataDir + "SampleProject.mpp");
// आईडी द्वारा कार्यों तक पहुंचें
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## चरण 2: कार्य लिंक बनाएं
निर्भरताएँ स्थापित करने के लिए कार्यों को एक साथ जोड़ें:
```csharp
// फिनिशटूस्टार्ट निर्भरता का उपयोग करके कार्यों को लिंक करें
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## चरण 3: कार्य लिंक प्रिंट करें
प्रोजेक्ट के लिए कार्य लिंक प्रिंट करें:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//कार्य लिंक के माध्यम से पुनरावृति करें
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## चरण 4: कार्य लिंक संपादित करें
इंडेक्स एक्सेस द्वारा कार्य लिंक संपादित करें:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## चरण 5: कार्य लिंक हटाएँ
प्रोजेक्ट से सभी कार्य लिंक हटाएँ:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Tasks में कार्य लिंक को कैसे संभालना है। इस व्यापक मार्गदर्शिका में प्रोजेक्ट लोड करना, कार्य लिंक बनाना, लिंक प्रिंट करना, लिंक संपादित करना और कार्य लिंक हटाना शामिल है।
अपने प्रोजेक्ट प्रबंधन अनुभव को बढ़ाने के लिए Aspose.Tasks द्वारा दी जाने वाली अधिक सुविधाओं और कार्यात्मकताओं का बेझिझक पता लगाएं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks .NET के सभी संस्करणों के साथ संगत है?
हां, Aspose.Tasks को .NET के सभी संस्करणों के साथ निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है।
### क्या मैं Aspose.Tasks का उपयोग करके कस्टम कार्य लिंक प्रकार बना सकता हूँ?
वर्तमान में, Aspose.Tasks मानक कार्य लिंक प्रकारों का समर्थन करता है, और कस्टम लिंक प्रकार उपलब्ध नहीं हैं।
### मैं Aspose.Tasks में कार्यों पर प्रतिबंध कैसे लागू कर सकता हूँ?
 आप का उपयोग करके बाधाएँ लागू कर सकते हैं`ConstraintType` की संपत्ति`Task` Aspose.Tasks में कक्षा।
### क्या प्रोजेक्ट फ़ाइलों के आकार पर कोई सीमाएँ हैं जिन्हें Aspose.Tasks संभाल सकता है?
Aspose.Tasks न्यूनतम प्रदर्शन प्रभाव के साथ बड़ी परियोजना फ़ाइलों को कुशलतापूर्वक संभाल सकता है।
### क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 हां, आप समर्थन पा सकते हैं और समुदाय के साथ जुड़ सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
