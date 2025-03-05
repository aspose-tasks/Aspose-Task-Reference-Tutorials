---
title: Aspose.Tasks में Microsoft प्रोजेक्ट डेटाबेस के लिए सेटिंग्स
linktitle: Aspose.Tasks में Microsoft प्रोजेक्ट डेटाबेस के लिए सेटिंग्स
second_title: Aspose.Tasks .NET API
description: .NET अनुप्रयोगों में निर्बाध एकीकरण के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट डेटाबेस सेटिंग्स को कॉन्फ़िगर करना सीखें।
type: docs
weight: 19
url: /hi/net/advanced-concepts/msp-database-settings/
---
## परिचय

यदि आप Aspose.Tasks का उपयोग करके अपने .NET अनुप्रयोगों में Microsoft प्रोजेक्ट डेटाबेस के साथ काम कर रहे हैं, तो आपको प्रोजेक्ट डेटा को निर्बाध रूप से आयात करने के लिए आवश्यक सेटिंग्स कॉन्फ़िगर करने की आवश्यकता होगी। यह ट्यूटोरियल चरण दर चरण प्रक्रिया में आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1.  .NET के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. Microsoft प्रोजेक्ट डेटाबेस तक पहुंच: डेटा आयात करने के लिए आपके पास Microsoft प्रोजेक्ट डेटाबेस तक पहुंच होनी चाहिए।

## नामस्थान आयात करें

सबसे पहले, सुनिश्चित करें कि आप अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## चरण 1: कनेक्शन स्ट्रिंग बनाएं

अपने Microsoft प्रोजेक्ट डेटाबेस से कनेक्शन स्ट्रिंग का निर्माण करें। यहाँ एक उदाहरण है:

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

प्लेसहोल्डर मानों को अपने वास्तविक डेटाबेस क्रेडेंशियल्स से बदलना सुनिश्चित करें।

## चरण 2: MspDbसेटिंग्स कॉन्फ़िगर करें

 का एक उदाहरण बनाएं`MspDbSettings` और प्रोजेक्ट GUID के साथ कनेक्शन स्ट्रिंग निर्दिष्ट करें:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## चरण 3: प्रोजेक्ट डेटा लोड करें

 त्वरित करें ए`Project` कॉन्फ़िगर सेटिंग्स का उपयोग कर ऑब्जेक्ट:

```csharp
var project = new Project(settings);
```

## चरण 4: प्रोजेक्ट डेटा सहेजें

लोड किए गए प्रोजेक्ट डेटा को एक फ़ाइल में सहेजें:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project डेटाबेस तक पहुँचने के लिए सेटिंग्स को कैसे कॉन्फ़िगर किया जाए। इन चरणों का पालन करके, आप कुशल प्रोजेक्ट प्रबंधन की सुविधा प्रदान करते हुए, अपने एप्लिकेशन में प्रोजेक्ट डेटा को निर्बाध रूप से आयात कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Microsoft Project डेटाबेस के विभिन्न संस्करणों के साथ Aspose.Tasks का उपयोग कर सकता हूँ?

A1: हाँ, Aspose.Tasks Microsoft प्रोजेक्ट डेटाबेस के विभिन्न संस्करणों का समर्थन करता है, जिससे एकीकरण में लचीलापन मिलता है।

### Q2: मैं डेटाबेस के साथ कनेक्शन समस्याओं का निवारण कैसे कर सकता हूँ?

 A2: सुनिश्चित करें कि आपकी कनेक्शन स्ट्रिंग उचित क्रेडेंशियल और डेटाबेस विवरण के साथ सही ढंग से कॉन्फ़िगर की गई है। आप दस्तावेज़ का संदर्भ भी ले सकते हैं या सहायता मांग सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).

### Q3: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

 उ3: हां, आप नि:शुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: क्या मैं डेटाबेस इंटरैक्शन के लिए स्कीमा को अनुकूलित कर सकता हूं?

 उ4: हां, आप इसके लिए स्कीमा निर्दिष्ट कर सकते हैं`MspDbSettings` आपके डेटाबेस संरचना के अनुसार ऑब्जेक्ट।

### Q5: Aspose.Tasks का उपयोग करने पर मुझे अधिक विस्तृत दस्तावेज़ कहां मिल सकते हैं?

 A5: आप व्यापक दस्तावेज़ीकरण का पता लगा सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/) Aspose.Tasks कार्यात्मकताओं में विस्तृत जानकारी के लिए।