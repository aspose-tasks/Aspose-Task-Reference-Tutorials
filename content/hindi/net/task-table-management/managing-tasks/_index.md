---
title: Aspose.Tasks में कार्य प्रबंधित करना
linktitle: Aspose.Tasks में कार्य प्रबंधित करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks के साथ कार्यों के प्रबंधन पर व्यापक मार्गदर्शिका का अन्वेषण करें। जोड़ना, विभाजित हिस्सों को प्रदर्शित करना, स्थानांतरित करना, गुण प्राप्त करना/सेट करना और बहुत कुछ करना सीखें।
type: docs
weight: 15
url: /hi/net/task-table-management/managing-tasks/
---
## परिचय
यदि आप एक .NET डेवलपर हैं जो अपने प्रोजेक्ट में कार्यों को कुशलतापूर्वक प्रबंधित करना चाहते हैं, तो .NET के लिए Aspose.Tasks एक मजबूत समाधान प्रदान करता है। यह ट्यूटोरियल चरण-दर-चरण निर्देश और कोड उदाहरण पेश करते हुए, Aspose.Tasks का उपयोग करके कार्यों को प्रबंधित करने के विभिन्न पहलुओं के माध्यम से आपका मार्गदर्शन करेगा। चाहे आप कार्य जोड़ रहे हों, विभाजित भागों को प्रदर्शित कर रहे हों, कार्यों को एक ही पैरेंट के अंतर्गत ले जा रहे हों, कार्य गुण प्राप्त/सेट कर रहे हों, कार्य असाइनमेंट पर पुनरावृत्ति कर रहे हों, कार्य बेसलाइन पढ़ रहे हों, या कार्यों को हटा रहे हों, यह मार्गदर्शिका आपको कवर कर देगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. .NET लाइब्रेरी के लिए Aspose.Tasks: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. दस्तावेज़ निर्देशिका: एक निर्देशिका स्थापित करें जहाँ आपके प्रोजेक्ट दस्तावेज़ संग्रहीत किए जाएंगे।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks के साथ काम करने के लिए आवश्यक नेमस्पेस शामिल करें:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. किसी प्रोजेक्ट में कोई कार्य जोड़ना
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
// कोई कार्य जोड़ें
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// प्रोजेक्ट सहेजें
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. कार्य के विभाजित भागों को प्रदर्शित करना
```csharp
// विभाजित कार्यों के साथ एक प्रोजेक्ट लोड करें
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// किसी कार्य तक पहुंचें
var task = project.RootTask.Children.GetById(4);
// विभाजित भागों को प्रदर्शित करें
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. किसी कार्य को एक ही अभिभावक के अधीन ले जाना
```csharp
try
{
    // एक प्रोजेक्ट लोड करें
    var project = new Project(DataDir + "MoveTask.mpp");
    // आईडी 5 वाले कार्यों को आईडी 3 वाले कार्य से पहले ले जाएं
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // संशोधित प्रोजेक्ट सहेजें
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. कार्य गुण प्राप्त करना/सेट करना
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
// कोई कार्य जोड़ें और गुण सेट करें
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// कार्य गुण एकत्र करें और प्रदर्शित करें
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. कार्य के असाइनमेंट पर बार-बार विचार करना
```csharp
// किसी प्रोजेक्ट को असाइनमेंट के साथ लोड करें
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// कार्य असाइनमेंट एकत्रित करें और प्रदर्शित करें
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. कार्य की आधार रेखाएँ पढ़ना
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
// एक कार्य जोड़ें और एक आधार रेखा निर्धारित करें
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// कार्य की आधारभूत अवधि प्रदर्शित करें
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. किसी कार्य को हटाना
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
// कोई कार्य जोड़ें
var task = project.RootTask.Children.Add("Task");
//हटाने से पहले और बाद में कार्यों की संख्या प्रदर्शित करें
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// कार्य हटाएँ
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## निष्कर्ष
.NET के लिए Aspose.Tasks में कार्यों को प्रबंधित करना दिए गए उदाहरणों के साथ एक सहज प्रक्रिया है। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, इन तकनीकों को शामिल करने से आपकी परियोजना प्रबंधन क्षमताएं बढ़ेंगी।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या Aspose.Tasks सभी .NET फ्रेमवर्क के साथ संगत है?
उत्तर: हां, Aspose.Tasks आपके विकास परिवेश के साथ अनुकूलता सुनिश्चित करते हुए विभिन्न .NET फ्रेमवर्क का समर्थन करता है।
### प्रश्न: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उत्तर: आप 30 दिन का अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: क्या Aspose.Tasks में विभाजित कार्यों के साथ काम करते समय कोई सीमाएँ हैं?
 उ: विभाजित कार्य एक शक्तिशाली सुविधा है, और विस्तृत दस्तावेज़ीकरण पाया जा सकता है[यहाँ](https://reference.aspose.com/tasks/net/).
### प्रश्न: क्या मैं कार्य गुणों को उदाहरणों में दिखाए गए से परे अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल! Aspose.Tasks कार्य गुणों के लिए व्यापक अनुकूलन विकल्प प्रदान करता है। अधिक विवरण के लिए दस्तावेज़ की जाँच करें.
### प्रश्न: मुझे Aspose.Tasks के लिए समर्थन कैसे मिलेगा?
 ए: पर जाएँ[Aspose.कार्य फोरम](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।