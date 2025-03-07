---
title: .NET के लिए Aspose.Tasks के साथ WBS कोड मास्क में महारत हासिल करना
linktitle: Aspose.Tasks में WBS कोड मास्क का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks के साथ प्रोजेक्ट प्रबंधन बढ़ाएँ। इस व्यापक ट्यूटोरियल में आसानी से WBS कोड मास्क बनाना, प्रबंधित करना और स्थानांतरित करना सीखें।
weight: 15
url: /hi/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Tasks के साथ WBS कोड मास्क में महारत हासिल करना

## परिचय
परियोजना प्रबंधन की गतिशील दुनिया में, कार्यों को कुशलतापूर्वक व्यवस्थित करना महत्वपूर्ण है। .NET के लिए Aspose.Tasks प्रोजेक्ट वर्क ब्रेकडाउन स्ट्रक्चर (WBS) कोड को सहजता से प्रबंधित करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम डब्लूबीएस कोड मास्क के संग्रह में गहराई से उतरेंगे, यह खोजेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके उन्हें कैसे कार्यान्वित और हेरफेर किया जाए।
## आवश्यक शर्तें
इससे पहले कि हम इस कोडिंग यात्रा को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान।
-  आपके विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित है। यदि नहीं, तो इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/net/).
- सहज कोडिंग अनुभव के लिए विज़ुअल स्टूडियो जैसा कोड संपादक।
## नामस्थान आयात करें
आरंभ करने के लिए, आइए आवश्यक नामस्थान आयात करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. प्रोजेक्ट और डब्ल्यूबीएस कोड परिभाषा आरंभ करें
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. WBS कोड मास्क को परिभाषित करें
किसी भी मौजूदा कोड मास्क को साफ़ करें और नए जोड़ें:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. कोड मास्क जानकारी प्रदर्शित करें
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. प्रोजेक्ट में कार्य जोड़ें
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. कार्य सूचना पुनः प्राप्त करें
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. कोड मास्क में हेरफेर करें
एक कोड मास्क निकालें और सुनिश्चित करें कि यह हटा दिया गया है:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. कोड मास्क को दूसरे प्रोजेक्ट में कॉपी करें
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. किसी अन्य प्रोजेक्ट में कोड मास्क प्रदर्शित करें
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. अन्य प्रोजेक्ट में कार्य जोड़ें
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. अन्य प्रोजेक्ट में WBS कोड प्रदर्शित करें
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## निष्कर्ष
.NET के लिए Aspose.Tasks के साथ, WBS कोड प्रबंधित करना एक आसान कार्य बन जाता है। इस ट्यूटोरियल में WBS कोड मास्क के निर्माण, हेरफेर और हस्तांतरण को शामिल किया गया है, जो आपको अपने प्रोजेक्ट प्रबंधन अनुभव को बढ़ाने के लिए एक व्यापक मार्गदर्शिका प्रदान करता है।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: Aspose.Tasks मुख्य रूप से .NET भाषाओं का समर्थन करता है, लेकिन आप अन्य भाषाओं के साथ इंटरऑपरेबिलिटी विकल्प तलाश सकते हैं।
### प्रश्न: क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.Tasks में सहायता कैसे प्राप्त करूं या समस्याओं की रिपोर्ट कैसे करूं?
 ए: पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समर्थन और चर्चा के लिए.
### प्रश्न: परियोजना प्रबंधन में डब्ल्यूबीएस कोड का क्या उद्देश्य है?
ए: डब्ल्यूबीएस कोड परियोजना कार्यों को पदानुक्रमित रूप से व्यवस्थित और संरचना करने में मदद करते हैं, जो परियोजना नियोजन के लिए एक व्यवस्थित दृष्टिकोण प्रदान करते हैं।
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks में WBS कोड के प्रारूप को अनुकूलित कर सकता हूँ?
उ: बिल्कुल, .NET के लिए Aspose.Tasks का उपयोग करके WBS कोड के प्रारूप और संरचना पर आपका पूर्ण नियंत्रण है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
