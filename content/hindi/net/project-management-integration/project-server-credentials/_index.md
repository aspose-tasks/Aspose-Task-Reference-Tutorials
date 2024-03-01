---
title: Aspose.Tasks में MS प्रोजेक्ट सर्वर क्रेडेंशियल प्रबंधित करना
linktitle: Aspose.Tasks में प्रोजेक्ट सर्वर क्रेडेंशियल प्रबंधित करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks के साथ MS प्रोजेक्ट सर्वर क्रेडेंशियल को सहजता से प्रबंधित करना सीखें। परियोजना प्रबंधन दक्षता बढ़ाएँ.
type: docs
weight: 22
url: /hi/net/project-management-integration/project-server-credentials/
---
## परिचय
परियोजना प्रबंधन के क्षेत्र में, प्रभावी समन्वय और निर्बाध संचार सफल परियोजना निष्पादन के लिए महत्वपूर्ण हैं। .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट सर्वर क्रेडेंशियल्स को प्रबंधित करने के लिए एक व्यापक समाधान प्रदान करता है, जो उपयोगकर्ताओं को प्रोजेक्ट डेटा तक सुरक्षित रूप से पहुंचने और हेरफेर करने में सक्षम बनाता है। यह ट्यूटोरियल .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट सर्वर क्रेडेंशियल्स को प्रबंधित करने की प्रक्रिया पर प्रकाश डालता है, और उपयोगकर्ताओं को एक सहज अनुभव सुनिश्चित करने के लिए प्रत्येक चरण के माध्यम से मार्गदर्शन करता है।
## आवश्यक शर्तें
.NET के लिए Aspose.Tasks के साथ MS प्रोजेक्ट सर्वर क्रेडेंशियल्स को प्रबंधित करने की यात्रा शुरू करने से पहले, सुनिश्चित करें कि निम्नलिखित शर्तें पूरी हो गई हैं:
### 1. .NET के लिए Aspose.Tasks इंस्टॉल करना
 शुरू करने के लिए, दिए गए लिंक से .NET के लिए Aspose.Tasks डाउनलोड और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/). लाइब्रेरी को अपने .NET वातावरण में निर्बाध रूप से एकीकृत करने के लिए इंस्टॉलेशन निर्देशों का पालन करें।
### 2. एक्सेस क्रेडेंशियल्स
एमएस प्रोजेक्ट सर्वर तक पहुंचने के लिए आवश्यक आवश्यक क्रेडेंशियल इकट्ठा करें। इसमें प्रोजेक्ट सर्वर से जुड़ा SharePoint डोमेन पता, उपयोगकर्ता नाम और पासवर्ड शामिल है।

## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, .NET के लिए Aspose.Tasks द्वारा प्रदान की गई कार्यक्षमताओं का कुशलतापूर्वक उपयोग करने के लिए आवश्यक नेमस्पेस आयात करें।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## चरण 1: दस्तावेज़ निर्देशिका पथ को परिभाषित करें
```csharp
String DataDir = "Your Document Directory";
```
## चरण 2: SharePoint डोमेन पता, उपयोगकर्ता नाम और पासवर्ड सेट करें
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## चरण 3: प्रोजेक्ट सर्वर क्रेडेंशियल बनाएं
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## चरण 4: प्रोजेक्ट फ़ाइल लोड करें
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## चरण 5: प्रोजेक्ट सर्वर मैनेजर को प्रारंभ करें
```csharp
var manager = new ProjectServerManager(credentials);
```
## चरण 6: नया प्रोजेक्ट बनाएं
```csharp
manager.CreateNewProject(newProject);
```
## चरण 7: परियोजना सूची पुनः प्राप्त करें
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## चरण 8: परियोजना सूची के माध्यम से पुनरावृति करें
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## निष्कर्ष
सुव्यवस्थित परियोजना प्रबंधन के लिए एमएस प्रोजेक्ट सर्वर क्रेडेंशियल्स को प्रभावी ढंग से प्रबंधित करना सर्वोपरि है। .NET के लिए Aspose.Tasks कार्यात्मकताओं का एक मजबूत सेट प्रदान करके इस प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में उल्लिखित चरण-दर-चरण मार्गदर्शिका का पालन करके, उपयोगकर्ता .NET के लिए Aspose.Tasks को अपने प्रोजेक्ट में सहजता से एकीकृत कर सकते हैं, जिससे प्रोजेक्ट डेटा की सुरक्षित पहुंच और हेरफेर सुनिश्चित हो सके।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या .NET के लिए Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट सर्वर के सभी संस्करणों के साथ संगत है?
उत्तर: .NET के लिए Aspose.Tasks को Microsoft प्रोजेक्ट सर्वर के विभिन्न संस्करणों के साथ संगत होने के लिए डिज़ाइन किया गया है, जो उपयोगकर्ताओं के लिए बहुमुखी प्रतिभा और लचीलापन सुनिश्चित करता है।
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks को अपने मौजूदा .NET प्रोजेक्ट में एकीकृत कर सकता हूँ?
उत्तर: हां, .NET के लिए Aspose.Tasks को मौजूदा .NET परियोजनाओं में सहजता से एकीकृत किया जा सकता है, जिससे कुशल परियोजना प्रबंधन क्षमताओं की सुविधा मिलती है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks परियोजना संसाधनों तक पहुँचने के लिए सहायता प्रदान करता है?
उत्तर: बिल्कुल, .NET के लिए Aspose.Tasks परियोजना प्रबंधन दक्षता को बढ़ाने, परियोजना संसाधनों तक पहुंचने और हेरफेर करने के लिए व्यापक समर्थन प्रदान करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks के लिए कोई लाइसेंसिंग विकल्प उपलब्ध हैं?
उत्तर: हां, .NET के लिए Aspose.Tasks लचीले लाइसेंसिंग विकल्प प्रदान करता है, जिसमें परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस और व्यावसायिक उपयोग के लिए पूर्ण लाइसेंस शामिल हैं।
### प्रश्न: मैं .NET के लिए Aspose.Tasks के लिए सहायता या समर्थन कहां से प्राप्त कर सकता हूं?
 उ: .NET के लिए Aspose.Tasks के संबंध में किसी भी पूछताछ या सहायता के लिए, आप सहायता मंच पर जा सकते हैं[Aspose.कार्य फोरम](https://forum.aspose.com/c/tasks/15).## संपूर्ण स्रोत कोड