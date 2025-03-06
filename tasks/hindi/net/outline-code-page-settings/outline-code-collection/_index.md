---
title: Aspose.Tasks में आउटलाइन कोड का संग्रह एमएस प्रोजेक्ट
linktitle: Aspose.Tasks में रूपरेखा कोड का संग्रह
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आउटलाइन कोड कैसे एकत्र करें। यह व्यापक ट्यूटोरियल चरण-दर-चरण निर्देश प्रदान करता है।
type: docs
weight: 11
url: /hi/net/outline-code-page-settings/outline-code-collection/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आउटलाइन कोड कैसे एकत्र करें। स्पष्टता और समझ सुनिश्चित करने के लिए हम प्रक्रिया को चरण-दर-चरण निर्देशों में विभाजित करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. विजुअल स्टूडियो: अपने सिस्टम पर विजुअल स्टूडियो इंस्टॉल करें।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# प्रोग्रामिंग की बुनियादी समझ: C# से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करें
सबसे पहले, अपने C# प्रोजेक्ट में Aspose.Tasks कार्यक्षमता तक पहुँचने के लिए आवश्यक नामस्थान आयात करें।
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
 का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल लोड करके प्रारंभ करें`Project` कक्षा।
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## चरण 2: रूपरेखा कोड एकत्र करें
प्रोजेक्ट कार्यों से रूपरेखा कोड इकट्ठा करने के लिए एक कलेक्टर बनाएं।
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## चरण 3: कार्यों और रूपरेखा कोड के माध्यम से पुनरावृति करें
एकत्र किए गए कार्यों और रूपरेखा कोडों को दोहराते हुए, उनके विवरण प्रिंट करें।
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## चरण 4: कस्टम आउटलाइन कोड परिभाषा जोड़ें
प्रोजेक्ट में एक कस्टम आउटलाइन कोड परिभाषा जोड़ें।
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## चरण 5: आउटलाइन कोड बनाएं और डालें
एक आउटलाइन कोड बनाएं और उसे किसी कार्य में डालें.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## चरण 6: रूपरेखा कोड में हेरफेर करें
आवश्यकतानुसार आउटलाइन कोड में हेरफेर करें, जैसे सम्मिलित करना, हटाना या साफ़ करना।
```csharp
// हेरफेर का उदाहरण
// ...
// 2 के साथ कोड को सही स्थिति में डालें
task.OutlineCodes.Insert(2, code2);
// जांचें कि क्या कोड डाला गया था
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आउटलाइन कोड कैसे एकत्रित करें। इन चरणों का पालन करके, आप संगठन और स्पष्टता को बढ़ाते हुए, अपनी परियोजनाओं के भीतर रूपरेखा कोड को प्रभावी ढंग से प्रबंधित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, .NET के लिए Aspose.Tasks मुख्य रूप से .NET प्लेटफ़ॉर्म को लक्षित करता है, लेकिन यह Aspose.Tasks for Cloud के माध्यम से अन्य प्रोग्रामिंग भाषाओं के लिए भी समर्थन प्रदान करता है।
### प्रश्न: क्या प्रोजेक्ट फ़ाइलों के आकार पर कोई सीमाएँ हैं जिन्हें .NET के लिए Aspose.Tasks संभाल सकता है?
उ: .NET के लिए Aspose.Tasks बड़ी प्रोजेक्ट फ़ाइलों को कुशलता से संभाल सकता है, लेकिन फ़ाइल की जटिलता और आकार के आधार पर प्रदर्शन भिन्न हो सकता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट के नवीनतम संस्करणों के साथ संगत है?
उत्तर: हाँ, .NET के लिए Aspose.Tasks नवीनतम सहित Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks के साथ काम करते समय आउटपुट प्रारूप को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल, .NET के लिए Aspose.Tasks आपकी आवश्यकताओं के अनुसार आउटपुट प्रारूप को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### प्रश्न: मुझे .NET के लिए Aspose.Tasks के लिए अतिरिक्त समर्थन या संसाधन कहां मिल सकते हैं?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) .NET के लिए Aspose.Tasks के संबंध में किसी भी सहायता या प्रश्न के लिए।