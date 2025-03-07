---
title: Aspose.Tasks में कार्य संग्रह प्रबंधित करना
linktitle: Aspose.Tasks में कार्य संग्रह प्रबंधित करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में कुशल कार्य संग्रह प्रबंधन का अन्वेषण करें। निर्माण से लेकर संपादन तक, परियोजना प्रबंधन में आसानी से महारत हासिल करें।
weight: 18
url: /hi/net/task-table-management/task-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य संग्रह प्रबंधित करना

## परिचय
यदि आप .NET का उपयोग करके परियोजना प्रबंधन की दुनिया में गहराई से उतर रहे हैं, तो Aspose.Tasks कार्य संग्रह के निर्बाध संचालन के लिए आपका पसंदीदा समाधान है। यह ट्यूटोरियल आपको कार्य संग्रह को कुशलतापूर्वक प्रबंधित करने की प्रक्रिया में मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आप इस शक्तिशाली लाइब्रेरी का अधिकतम लाभ उठा सकें।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपकी मशीन पर विज़ुअल स्टूडियो स्थापित है।
- .NET लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया और आपके प्रोजेक्ट में संदर्भित किया गया।
## नामस्थान आयात करें
आरंभ करने के लिए, आइए आपके C# प्रोजेक्ट में आवश्यक नामस्थान आयात करें:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
ये नामस्थान प्रभावी कार्य प्रबंधन के लिए आवश्यक आवश्यक कक्षाओं और विधियों तक पहुंच प्रदान करते हैं।
अब, आइए स्पष्टता और सरलता सुनिश्चित करते हुए ट्यूटोरियल को चरणों की एक श्रृंखला में विभाजित करें।
## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाना
```csharp
var project = new Project();
```
 का उपयोग करके एक नया प्रोजेक्ट प्रारंभ करें`Project` कक्षा।
## चरण 2: कार्य संग्रह की तैयारी की जाँच करना
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
सत्यापित करें कि क्या कार्य संग्रह केवल पढ़ने के लिए है।
## चरण 3: कार्य बनाना
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// प्रारंभ, अवधि और समाप्ति जैसे अतिरिक्त कार्य गुण सेट करें
// कार्य 2 और कार्य 3 के लिए समान चरण
```
प्रोजेक्ट के भीतर कार्य बनाएं और उनके गुण निर्धारित करें।
## चरण 4: परियोजना कार्यों को प्रिंट करना
```csharp
foreach (var child in project.RootTask.Children)
{
    // कार्य विवरण प्रिंट करें
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
प्रोजेक्ट के भीतर प्रत्येक कार्य का विवरण प्रिंट करें।
## चरण 5: कार्य संपादित करना
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
उनकी आईडी या यूआईडी का उपयोग करके कार्य संपादित करें।
## चरण 6: एक आवर्ती कार्य जोड़ना
```csharp
var parameters = new RecurringTaskParameters
{
    // आवर्ती कार्य पैरामीटर सेट करें
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
प्रोजेक्ट में एक आवर्ती कार्य जोड़ें.
## चरण 7: संग्रह को एक सूची में परिवर्तित करना
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
कार्य संग्रह को एक सूची में बदलें और प्रत्येक कार्य पर संचालन करें।
## निष्कर्ष
इस चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.Tasks में कार्य संग्रह प्रबंधित करना बहुत आसान है। चाहे आप कार्य बना रहे हों, संपादित कर रहे हों या हटा रहे हों, Aspose.Tasks आपको परियोजना प्रबंधन को निर्बाध रूप से संभालने का अधिकार देता है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Tasks .NET कोर के साथ संगत है?
हाँ, Aspose.Tasks .NET Core का समर्थन करता है, जिससे आप इसे क्रॉस-प्लेटफ़ॉर्म अनुप्रयोगों में उपयोग कर सकते हैं।
### क्या मैं प्रोजेक्ट कार्यों को विभिन्न फ़ाइल स्वरूपों में निर्यात कर सकता हूँ?
बिल्कुल! Aspose.Tasks PDF, XLSX और MPP सहित बहुमुखी निर्यात विकल्प प्रदान करता है।
### मैं कार्यों के बीच निर्भरता कैसे संभाल सकता हूँ?
 आप इसका उपयोग करके कार्य निर्भरताएँ निर्धारित कर सकते हैं`TaskLink` Aspose.Tasks द्वारा प्रदान की गई कक्षा।
### क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 हां, आप यहां समर्थन पा सकते हैं और समुदाय के साथ जुड़ सकते हैं[Aspose.कार्य फोरम](https://forum.aspose.com/c/tasks/15).
### क्या मैं Aspose.Tasks के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
