---
title: Aspose.Tasks में MS प्रोजेक्ट जानकारी निकालें
linktitle: Aspose.Tasks में प्रोजेक्ट जानकारी निकालना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके आसानी से MS प्रोजेक्ट जानकारी निकालने का तरीका जानें। हमारे व्यापक ट्यूटोरियल में गोता लगाएँ।
weight: 20
url: /hi/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट जानकारी निकालें

## परिचय
क्या आप .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइलों से कुशलतापूर्वक जानकारी निकालना चाहते हैं? इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में मार्गदर्शन देंगे। लेकिन इससे पहले कि हम कार्यान्वयन विवरण में उतरें, आइए पहले यह सुनिश्चित कर लें कि आपके पास वह सब कुछ है जो आपको चाहिए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
### 1. .NET के लिए Aspose.Tasks
 सुनिश्चित करें कि आपने .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित किया है। यदि आपने पहले से ऐसा नहीं किया है, तो आप इसे यहां से डाउनलोड कर सकते हैं[.NET वेबसाइट के लिए Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. SharePoint के लिए क्रेडेंशियल
आपको उस SharePoint तक पहुंचने के लिए क्रेडेंशियल्स की आवश्यकता होगी जहां आपकी MS प्रोजेक्ट फ़ाइलें संग्रहीत हैं। सुनिश्चित करें कि आपके पास निम्नलिखित जानकारी है:
- SharePoint डोमेन पता
- उपयोगकर्ता नाम
- पासवर्ड
## नामस्थान आयात करना
एक बार जब आप अपनी पूर्वापेक्षाएँ सुलझा लेते हैं, तो आपके प्रोजेक्ट में आवश्यक नामस्थान आयात करने का समय आ जाता है।
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
आइए अब MS प्रोजेक्ट जानकारी निकालने की प्रक्रिया को कई चरणों में विभाजित करें।
## चरण 1: क्रेडेंशियल प्रदान करें
सबसे पहले, आपको प्रोजेक्ट सर्वर तक पहुंचने के लिए अपने SharePoint क्रेडेंशियल प्रदान करने होंगे।
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## चरण 2: प्रोजेक्ट सर्वर मैनेजर को प्रारंभ करें
 इसके बाद, a आरंभ करें`ProjectServerManager` प्रदान किए गए क्रेडेंशियल्स के साथ उदाहरण।
```csharp
var reader = new ProjectServerManager(credentials);
```
## चरण 3: परियोजना सूची पुनः प्राप्त करें
अब, आप प्रोजेक्ट सर्वर से परियोजनाओं की सूची पुनः प्राप्त कर सकते हैं।
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## चरण 4: परियोजना जानकारी प्रिंट करें
अंत में, परियोजनाओं की सूची को दोबारा दोहराएं और उनकी जानकारी प्रिंट करें।
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट जानकारी निकालने का तरीका सफलतापूर्वक सीख लिया है। इस ज्ञान के साथ, अब आप इस कार्यक्षमता को अपने .NET अनुप्रयोगों में निर्बाध रूप से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं Microsoft Project के किसी भी संस्करण के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, .NET के लिए Aspose.Tasks 2003, 2007, 2010, 2013, 2016 और 2019 सहित Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।
### Q2: क्या .NET के लिए Aspose.Tasks विंडोज़ और लिनक्स दोनों प्लेटफ़ॉर्म के साथ संगत है?
उत्तर: हाँ, .NET के लिए Aspose.Tasks विंडोज़ और लिनक्स दोनों प्लेटफार्मों के साथ संगत है, जो इसे विभिन्न विकास परिवेशों के लिए बहुमुखी बनाता है।
### Q3: क्या मैं .NET के लिए Aspose.Tasks का उपयोग करके कार्य निर्भरताएँ निकाल सकता हूँ?
उत्तर: बिल्कुल! .NET के लिए Aspose.Tasks न केवल बुनियादी परियोजना जानकारी बल्कि कार्य निर्भरता और अन्य जटिल विवरण निकालने के लिए मजबूत कार्यक्षमता प्रदान करता है।
### Q4: क्या .NET के लिए Aspose.Tasks तकनीकी सहायता प्रदान करता है?
 उत्तर: हां, आप .NET के लिए Aspose.Tasks के लिए तकनीकी सहायता प्राप्त कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15), जहां आप प्रश्न पूछ सकते हैं और विशेषज्ञों से सहायता ले सकते हैं।
### Q5: क्या मैं .NET खरीदने से पहले Aspose.Tasks को आज़मा सकता हूँ?
 उत्तर: निश्चित रूप से! आप .NET के लिए Aspose.Tasks के निःशुल्क परीक्षण का लाभ उठा सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/), जिससे आप खरीदारी का निर्णय लेने से पहले इसकी विशेषताओं का पता लगा सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
