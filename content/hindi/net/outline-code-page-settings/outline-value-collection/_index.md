---
title: Aspose.Tasks के साथ MS प्रोजेक्ट रूपरेखा मान प्रबंधित करें
linktitle: Aspose.Tasks में रूपरेखा मूल्यों का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइलों में रूपरेखा मानों को प्रबंधित करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण ट्यूटोरियल।
type: docs
weight: 17
url: /hi/net/outline-code-page-settings/outline-value-collection/
---
## परिचय
.NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के साथ इंटरैक्ट करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है। ऐसी ही एक सुविधा किसी प्रोजेक्ट के भीतर रूपरेखा मूल्यों को प्रबंधित करने की क्षमता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके आउटलाइन मानों को कैसे एकत्र और हेरफेर किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET के लिए Aspose.Tasks: आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास एक उपयुक्त आईडीई स्थापित है, जैसे विजुअल स्टूडियो।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।
## नामस्थान आयात करें
अपनी C# कोड फ़ाइल में, Aspose.Tasks कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;

```
आइए दिए गए उदाहरण को कई चरणों में तोड़ें:
## चरण 1: एक प्रोजेक्ट फ़ाइल लोड करें
 सबसे पहले, आरंभ करें a`Project` मौजूदा Microsoft प्रोजेक्ट फ़ाइल लोड करके ऑब्जेक्ट करें:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## चरण 2: मौजूदा रूपरेखा मान साफ़ करें
इसके बाद, प्रोजेक्ट से किसी भी मौजूदा रूपरेखा मान को साफ़ करें:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## चरण 3: नया आउटलाइन कोड परिभाषित करें
अब, विवरण और मूल्य के साथ एक नया रूपरेखा कोड परिभाषित करें:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## चरण 4: रूपरेखा मूल्य अद्यतन करें
आउटलाइन कोड का मान अपडेट करें:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## चरण 5: रूपरेखा मूल्यों पर पुनरावृति करें
रूपरेखा मानों के माध्यम से पुनरावृति करें और उनका विवरण प्रिंट करें:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## चरण 6: रूपरेखा मूल्यों में हेरफेर करें
आवश्यकतानुसार आउटलाइन मानों को हटाने, डालने और कॉपी करने जैसे कार्य करें:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों में आउटलाइन मानों के साथ कैसे काम किया जाए। दिए गए चरणों का पालन करके, आप अधिक नियंत्रण और लचीलेपन को सक्षम करते हुए, अपनी परियोजनाओं के भीतर रूपरेखा मूल्यों को कुशलतापूर्वक प्रबंधित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं एक साथ कई आउटलाइन कोड में हेरफेर कर सकता हूँ?
उ: हां, आप Aspose.Tasks का उपयोग करके एक प्रोजेक्ट के भीतर कई आउटलाइन कोड को परिभाषित और हेरफेर कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हाँ, Aspose.Tasks MPP और XML प्रारूपों सहित Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: मैं रूपरेखा मूल्यों के साथ काम करते समय त्रुटियों को कैसे संभाल सकता हूँ?
ए: आप अपवादों को शानदार ढंग से प्रबंधित करने के लिए ट्राई-कैच ब्लॉक जैसे त्रुटि प्रबंधन तंत्र को लागू कर सकते हैं।
### प्रश्न: क्या मैं अपने प्रोजेक्ट में रूपरेखा मूल्यों की उपस्थिति को अनुकूलित कर सकता हूँ?
उत्तर: हां, Aspose.Tasks आपकी आवश्यकताओं के अनुसार रूपरेखा मूल्यों की उपस्थिति और व्यवहार को अनुकूलित करने के लिए व्यापक एपीआई प्रदान करता है।
### प्रश्न: Aspose.Tasks के लिए मुझे अतिरिक्त संसाधन और समर्थन कहां मिल सकता है?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन के लिए और अन्वेषण करें[प्रलेखन](https://reference.aspose.com/tasks/net/) एपीआई और सुविधाओं पर विस्तृत जानकारी के लिए।