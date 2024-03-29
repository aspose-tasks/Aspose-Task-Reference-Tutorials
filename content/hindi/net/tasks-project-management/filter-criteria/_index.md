---
title: Aspose.Tasks के साथ MS प्रोजेक्ट फ़िल्टर मानदंड में महारत हासिल करना
linktitle: Aspose.Tasks में मानदंड फ़िल्टर करें
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में फ़िल्टर मानदंड लागू करना सीखें। लक्षित डेटा विश्लेषण के साथ परियोजना प्रबंधन दक्षता को बढ़ावा दें।
type: docs
weight: 18
url: /hi/net/tasks-project-management/filter-criteria/
---
## परिचय
परियोजना प्रबंधन के क्षेत्र में, माइक्रोसॉफ्ट प्रोजेक्ट एक अग्रणी उपकरण के रूप में खड़ा है, जो परियोजना योजनाकारों और प्रबंधकों की सहायता के लिए ढेर सारी सुविधाएँ प्रदान करता है। इसकी कई कार्यक्षमताओं में प्रोजेक्ट डेटा को फ़िल्टर करने की क्षमता शामिल है, जिससे उपयोगकर्ता अपने प्रोजेक्ट के कार्यों के विशिष्ट पहलुओं पर ध्यान केंद्रित कर सकते हैं। हालाँकि, सही मार्गदर्शन के बिना इन फ़िल्टरिंग क्षमताओं में महारत हासिल करना एक कठिन काम हो सकता है। इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में फ़िल्टर मानदंड लागू करने पर चरण-दर-चरण मार्गदर्शिका प्रदान करके प्रक्रिया को स्पष्ट करना है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. C# की बुनियादी समझ: इस ट्यूटोरियल में शामिल अवधारणाओं को समझने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
2.  .NET के लिए Aspose.Tasks की स्थापना: सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित हैं। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. Microsoft प्रोजेक्ट फ़ाइल: एक Microsoft प्रोजेक्ट फ़ाइल (उदाहरण के लिए, Project2003.mpp) तैयार रखें, जिसका उपयोग आप फ़िल्टर मानदंड लागू करने के लिए करेंगे।

## नामस्थान आयात करें
सबसे पहले, आपको .NET के लिए Aspose.Tasks के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करने की आवश्यकता है। इन चरणों का पालन करें:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 स्पष्टीकरण: कोड की यह पंक्ति एक नए उदाहरण को प्रारंभ करती है`Project` क्लास और उसके पथ द्वारा निर्दिष्ट Microsoft प्रोजेक्ट फ़ाइल को लोड करता है।
## चरण 2: कार्य फ़िल्टर पुनर्प्राप्त करें
```csharp
var filter = project.TaskFilters.ToList()[1];
```
स्पष्टीकरण: यहां, हम प्रोजेक्ट से एक कार्य फ़िल्टर पुनर्प्राप्त करते हैं। सूचकांक समायोजित करें (`[1]`) अपनी आवश्यकता के अनुसार वांछित फ़िल्टर का चयन करें।
## चरण 3: मानदंड पंक्तियाँ प्रदर्शित करें
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
स्पष्टीकरण: यह अनुभाग फ़िल्टर की प्रत्येक मानदंड पंक्ति के माध्यम से पुनरावृत्त होता है और इसके फ़ील्ड, संचालन, परीक्षण और मान (यदि कोई हो) प्रदर्शित करता है।
## चरण 4: फ़िल्टर मानदंड प्रिंट करें
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
स्पष्टीकरण: फ़िल्टर मानदंड के संचालन को प्रिंट करता है।
## चरण 5: मानदंड विवरण प्रदर्शित करें
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
स्पष्टीकरण: यह भाग फ़िल्टर की कॉन्फ़िगरेशन में अंतर्दृष्टि प्रदान करते हुए, प्रत्येक मानदंड पंक्ति के बारे में विस्तृत जानकारी पुनर्प्राप्त और प्रदर्शित करता है।

## निष्कर्ष
.NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में फ़िल्टर मानदंड में महारत हासिल करना एक मूल्यवान कौशल है जो परियोजना प्रबंधन दक्षता को महत्वपूर्ण रूप से बढ़ा सकता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि फ़िल्टर मानदंड को प्रोग्रामेटिक रूप से कैसे हेरफेर किया जाए, जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार प्रोजेक्ट व्यू तैयार कर सकें।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं एमएस प्रोजेक्ट में एक साथ कई फिल्टर लागू कर सकता हूं?
उ: हां, आप अपने प्रोजेक्ट डेटा को और अधिक परिष्कृत करने के लिए कई फ़िल्टर जोड़ सकते हैं।
### प्रश्न: क्या Aspose.Tasks Microsoft Project फ़ाइलों के पुराने संस्करणों का समर्थन करता है?
उत्तर: हां, Aspose.Tasks बैकवर्ड संगतता प्रदान करता है, जिससे आप Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ काम कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks अन्य .NET फ्रेमवर्क के साथ संगत है?
उत्तर: Aspose.Tasks .NET फ्रेमवर्क, .NET कोर और .NET मानक का समर्थन करता है, जो विभिन्न विकास परिवेशों में लचीलापन सुनिश्चित करता है।
### प्रश्न: क्या मैं गतिशील स्थितियों के आधार पर फ़िल्टर मानदंड को अनुकूलित कर सकता हूँ?
ए: बिल्कुल, आप अनुकूली परियोजना डेटा विश्लेषण को सक्षम करते हुए, गतिशील मापदंडों के आधार पर फ़िल्टर मानदंड को प्रोग्रामेटिक रूप से समायोजित कर सकते हैं।
### प्रश्न: यदि मुझे Aspose.Tasks में कोई समस्या आती है तो मैं कहां सहायता प्राप्त कर सकता हूं?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय से समर्थन प्राप्त करने के लिए या वैयक्तिकृत सहायता के लिए सीधे Aspose.Tasks समर्थन तक पहुँचने के लिए।