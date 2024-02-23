---
title: Aspose.Tasks के साथ MS प्रोजेक्ट फ़िल्टर को कुशलतापूर्वक प्रबंधित करें
linktitle: Aspose में फ़िल्टर संग्रह का प्रबंधन। कार्य
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके फ़िल्टर MS प्रोजेक्ट संग्रह को प्रभावी ढंग से प्रबंधित करना सीखें।
type: docs
weight: 17
url: /hi/net/tasks-project-management/filter-collection/
---
## परिचय
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके फ़िल्टर MS प्रोजेक्ट संग्रह को प्रभावी ढंग से कैसे प्रबंधित किया जाए। प्रोजेक्ट डेटा को कुशलतापूर्वक व्यवस्थित करने और उसका विश्लेषण करने के लिए फ़िल्टर प्रबंधित करना महत्वपूर्ण है। Aspose.Tasks कार्य और संसाधन फ़िल्टर को निर्बाध रूप से संभालने के लिए मजबूत कार्यक्षमता प्रदान करता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
2. .NET विकास परिवेश तक पहुंच: सुनिश्चित करें कि आपके पास Aspose.Tasks के साथ काम करने के लिए एक .NET विकास परिवेश स्थापित है।

## नामस्थान आयात करें
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## चरण 2: कार्य फ़िल्टर पर पुनरावृति करें
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## चरण 3: संसाधन फ़िल्टर पर पुनरावृति करें
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## चरण 4: फ़िल्टर साफ़ करें और कॉपी करें
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// अन्य प्रोजेक्ट के फ़िल्टर साफ़ करें
otherProject.TaskFilters.Clear();
// फ़िल्टर को अन्य प्रोजेक्ट में कॉपी करें
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## चरण 5: कस्टम कार्य फ़िल्टर जोड़ें
```csharp
// कस्टम कार्य फ़िल्टर जोड़ें
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## चरण 6: सभी फ़िल्टर हटाएँ
```csharp
// सभी फ़िल्टर हटाएँ
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
इन चरणों का पालन करके, आप .NET के लिए Aspose.Tasks का उपयोग करके फ़िल्टर MS प्रोजेक्ट संग्रह को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## निष्कर्ष
प्रोजेक्ट डेटा को व्यवस्थित और विश्लेषण करने के लिए एमएस प्रोजेक्ट संग्रह में फ़िल्टर को प्रभावी ढंग से प्रबंधित करना महत्वपूर्ण है। .NET के लिए Aspose.Tasks कार्य और संसाधन फ़िल्टर को निर्बाध रूप से संभालने के लिए व्यापक कार्यक्षमता प्रदान करता है, जिससे डेवलपर्स को परियोजना प्रबंधन कार्यों को कुशलतापूर्वक व्यवस्थित करने में सशक्त बनाया जाता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose. कार्य जटिल परियोजना संरचनाओं को संभाल सकते हैं?
उत्तर: Aspose.Tasks व्यापक परियोजना प्रबंधन क्षमताओं को सुनिश्चित करते हुए, जटिल संरचनाओं सहित विभिन्न परियोजना संरचनाओं को संभालने के लिए मजबूत सुविधाएँ प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Tasks MS प्रोजेक्ट फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जो विभिन्न संस्करणों में अनुकूलता सुनिश्चित करता है।
### प्रश्न: क्या मैं विशिष्ट परियोजना आवश्यकताओं के अनुसार फ़िल्टर को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल! Aspose.Tasks डेवलपर्स को लचीलेपन और दक्षता को बढ़ाते हुए अद्वितीय परियोजना आवश्यकताओं के अनुरूप कस्टम फ़िल्टर बनाने की अनुमति देता है।
### प्रश्न: क्या Aspose.Tasks दस्तावेज़ीकरण और समर्थन संसाधन प्रदान करता है?
उत्तर: हां, Aspose.Tasks अपने प्रोजेक्ट कार्यान्वयन के हर चरण में डेवलपर्स की सहायता के लिए व्यापक दस्तावेज़ीकरण, ट्यूटोरियल और एक समर्पित सहायता मंच प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
उत्तर: हां, डेवलपर्स Aspose के निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं। खरीदारी का निर्णय लेने से पहले इसकी विशेषताओं का पता लगाने का कार्य।