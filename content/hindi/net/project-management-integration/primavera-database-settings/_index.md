---
title: Aspose.Tasks में MS प्रोजेक्ट प्रिमावेरा डेटाबेस कॉन्फ़िगर करें
linktitle: Aspose.Tasks में प्रिमावेरा डेटाबेस सेटिंग्स को कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में MS प्रोजेक्ट प्रिमावेरा डेटाबेस सेटिंग्स को आसानी से कैसे कॉन्फ़िगर करें। अपने प्रोजेक्ट प्रबंधन कार्यों को सुव्यवस्थित करें।
type: docs
weight: 11
url: /hi/net/project-management-integration/primavera-database-settings/
---
## परिचय
क्या आप MS प्रोजेक्ट प्राइमेरा डेटाबेस सेटिंग्स को सहजता से कॉन्फ़िगर करने के लिए .NET के लिए Aspose.Tasks की शक्ति का उपयोग करने के लिए तैयार हैं? इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में मार्गदर्शन देंगे। लेकिन इससे पहले कि हम आगे बढ़ें, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. .NET के लिए Aspose.Tasks इंस्टॉल करें
 वहां जाओ[.NET के लिए Aspose.Tasks डाउनलोड करें](https://releases.aspose.com/tasks/net/) और Aspose. Tasks लाइब्रेरी का नवीनतम संस्करण प्राप्त करें। इसे अपने .NET वातावरण में स्थापित करने के लिए दिए गए इंस्टॉलेशन निर्देशों का पालन करें।
### 2. एमएस प्रोजेक्ट प्रिमावेरा डेटाबेस तक पहुंचें
सुनिश्चित करें कि आपके पास एमएस प्रोजेक्ट प्रिमावेरा डेटाबेस तक पहुंच है। आगे बढ़ने के लिए आपको आवश्यक क्रेडेंशियल्स और कनेक्शन विवरण की आवश्यकता होगी।
### 3. C# और .NET फ्रेमवर्क का बुनियादी ज्ञान
यह ट्यूटोरियल मानता है कि आपको C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क की बुनियादी समझ है।

## नामस्थान आयात करें
आइए आपके C# प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें।

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

```
 यह लाइन आयात करती है`System.Data.SqlClient` नेमस्पेस, जिसमें .NET अनुप्रयोगों में SQL सर्वर डेटाबेस के साथ काम करने के लिए कक्षाएं शामिल हैं।

अब जब आपने पूर्वापेक्षाएँ सेट कर ली हैं और आवश्यक नेमस्पेस आयात कर लिया है, तो आइए .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट प्राइमेरा डेटाबेस सेटिंग्स को कॉन्फ़िगर करने के लिए प्रदान किए गए उदाहरण कोड को तोड़ दें।
## चरण 1: SqlConnectionStringBuilder ऑब्जेक्ट बनाएं
```csharp
var sb = new SqlConnectionStringBuilder();
sb.DataSource = "192.168.56.3,1433";
sb.Encrypt = true;
sb.TrustServerCertificate = true;
sb.InitialCatalog = "PrimaveraEDB";
sb.NetworkLibrary = "DBMSSOCN";
sb.UserID = "privuser";
sb.Password = "***";
sb.ConnectTimeout = 2; // पूर्वछोड़ें
```
 यह कोड एक बनाता है`SqlConnectionStringBuilder` ऑब्जेक्ट और विभिन्न गुण सेट करता है जैसे कि`DataSource`, `Encrypt`, `InitialCatalog`, `UserID`, `Password`, आदि, प्राइमेरा डेटाबेस के लिए कनेक्शन स्ट्रिंग को कॉन्फ़िगर करने के लिए।
## चरण 2: प्राइमेराडीबीसेटिंग्स ऑब्जेक्ट को आरंभ करें
```csharp
var settings = new PrimaveraDbSettings(sb.ConnectionString, 4502);
```
यहां, हम इसका एक नया उदाहरण प्रारंभ करते हैं`PrimaveraDbSettings` कनेक्शन स्ट्रिंग और प्रोजेक्ट आईडी पास करके क्लास (इस मामले में,`4502`) पैरामीटर के रूप में।
## चरण 3: डेटाबेस से प्रोजेक्ट पढ़ें
```csharp
var project = new Project(settings);
```
 यह पंक्ति एक नया सृजन करती है`Project` पास करके ऑब्जेक्ट करें`settings` वस्तु जो हमने पहले बनाई थी। यह प्रिमावेरा डेटाबेस से एक कनेक्शन स्थापित करता है और निर्दिष्ट यूआईडी के साथ प्रोजेक्ट को पढ़ता है (`4502`).
## चरण 4: प्रोजेक्ट यूआईडी प्रदर्शित करें
```csharp
Console.WriteLine("Project UID to read: " + settings.ProjectId);
```
अंत में, यह कोड कंसोल पर पढ़े जा रहे प्रोजेक्ट की यूआईडी को प्रिंट करता है।

## निष्कर्ष
बधाई हो! आपने सीखा है कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट प्राइमेरा डेटाबेस सेटिंग्स को कैसे कॉन्फ़िगर किया जाए। इस ज्ञान के साथ, आप Aspose.Tasks को अपने .NET अनुप्रयोगों में कुशलतापूर्वक एकीकृत कर सकते हैं और परियोजना प्रबंधन कार्यों को सुव्यवस्थित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोजेक्ट प्रबंधन सॉफ़्टवेयर के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, .NET के लिए Aspose.Tasks एमएस प्रोजेक्ट, प्रिमावेरा और अन्य सहित विभिन्न परियोजना प्रबंधन सॉफ्टवेयर के साथ एकीकरण का समर्थन करता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks नवीनतम .NET कोर संस्करणों के साथ संगत है?
उत्तर: हां, .NET के लिए Aspose.Tasks .NET कोर और .NET फ्रेमवर्क दोनों वातावरणों के साथ संगत है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks क्लाउड-आधारित परियोजना प्रबंधन समाधानों के लिए समर्थन प्रदान करता है?
उत्तर: .NET के लिए Aspose.Tasks मुख्य रूप से ऑन-प्रिमाइसेस प्रोजेक्ट प्रबंधन समाधानों पर केंद्रित है, लेकिन इसे उपयुक्त कॉन्फ़िगरेशन के साथ कुछ क्लाउड वातावरणों के लिए अनुकूलित किया जा सकता है।
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा को प्रोग्रामेटिक रूप से हेरफेर कर सकता हूँ?
उत्तर: बिल्कुल! .NET के लिए Aspose.Tasks विभिन्न प्रारूपों में प्रोजेक्ट डेटा को पढ़ने, लिखने और हेरफेर करने के लिए एपीआई का एक समृद्ध सेट प्रदान करता है।
### प्रश्न: क्या .NET उपयोगकर्ताओं के लिए Aspose.Tasks के लिए कोई सामुदायिक मंच या सहायता चैनल उपलब्ध है?
 उत्तर: हां, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) आपके किसी भी मुद्दे या प्रश्न के लिए सामुदायिक समर्थन और सहायता के लिए।## संपूर्ण स्रोत कोड