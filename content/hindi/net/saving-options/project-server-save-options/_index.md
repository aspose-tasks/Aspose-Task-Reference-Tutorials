---
title: Aspose.Tasks के लिए सर्वर MS प्रोजेक्ट विकल्प सहेजें
linktitle: प्रोजेक्ट सर्वर Aspose.Tasks के लिए विकल्प सहेजें
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट सर्वर एकीकरण का उपयोग करके Aspose.Tasks के लिए Microsoft प्रोजेक्ट विकल्पों को सहेजना सीखें। अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को बढ़ाएँ।
type: docs
weight: 16
url: /hi/net/saving-options/project-server-save-options/
---
## परिचय
इस ट्यूटोरियल में, हम प्रोजेक्ट सर्वर का उपयोग करके Aspose.Tasks के लिए Microsoft प्रोजेक्ट विकल्पों को सहेजने के बारे में विस्तार से जानेंगे। Aspose.Tasks एक शक्तिशाली .NET API है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। प्रोजेक्ट सर्वर क्षमताओं का लाभ उठाते हुए, हम Aspose.Tasks को अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो में निर्बाध रूप से एकीकृत कर सकते हैं। यह ट्यूटोरियल चरण दर चरण प्रक्रिया में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
   
2. प्रोजेक्ट सर्वर तक पहुंच: आपको एक्सेस क्रेडेंशियल्स और आपके प्रोजेक्ट सर्वर इंस्टेंस के यूआरएल की आवश्यकता होगी। यदि आपके पास कोई नहीं है, तो आप नि:शुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
3. Microsoft प्रोजेक्ट फ़ाइल: Microsoft प्रोजेक्ट फ़ाइल (.mpp) तैयार करें जिसे आप Aspose.Tasks का उपयोग करके सहेजना चाहते हैं।

## नामस्थान आयात करें
सबसे पहले, आपको अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने की आवश्यकता है:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## चरण 1: प्रोजेक्ट और क्रेडेंशियल प्रारंभ करें
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 सुनिश्चित करें कि आप प्रतिस्थापित करें`"Your Document Directory"`, `URL`, `Domain`, `UserName` , और`Password` अपने वास्तविक मूल्यों के साथ।
## चरण 2: प्रोजेक्ट सर्वर मैनेजर बनाएं
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## चरण 3: सहेजें विकल्प परिभाषित करें
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 समायोजित`ProjectGuid`, `ProjectName`, `Timeout` , और`PollingInterval` आपकी आवश्यकताओं के अनुसार.
## चरण 4: प्रोजेक्ट को सर्वर पर सहेजें
```csharp
manager.CreateNewProject(project, options);
```
यह प्रोजेक्ट को निर्दिष्ट विकल्पों के साथ प्रोजेक्ट सर्वर पर सहेज लेगा।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि प्रोजेक्ट सर्वर एकीकरण का उपयोग करके Aspose.Tasks के लिए Microsoft प्रोजेक्ट विकल्पों को कैसे सहेजा जाए। इन चरणों का पालन करके, आप दक्षता और उत्पादकता को बढ़ाते हुए Aspose.Tasks को अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो में सहजता से शामिल कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं माइक्रोसॉफ्ट प्रोजेक्ट के विभिन्न संस्करणों के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, Aspose.Tasks विभिन्न वातावरणों में अनुकूलता सुनिश्चित करते हुए, Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप Aspose.Tasks का निःशुल्क परीक्षण संस्करण यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: क्या Aspose.Tasks मल्टी-थ्रेडिंग का समर्थन करता है?
उत्तर: हां, Aspose.Tasks को थ्रेड-सुरक्षित बनाने के लिए डिज़ाइन किया गया है, जो प्रोजेक्ट डेटा तक समवर्ती पहुंच की अनुमति देता है।
### प्रश्न: क्या मैं प्रोजेक्ट सर्वर एकीकरण का उपयोग करते समय सेव विकल्पों को अनुकूलित कर सकता हूँ?
उत्तर: हां, आप अपनी आवश्यकताओं के अनुरूप प्रोजेक्ट नाम, टाइमआउट और मतदान अंतराल जैसे विकल्पों को सहेज सकते हैं।
### प्रश्न: मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 उत्तर: आप इस पर समर्थन और सहायता पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).