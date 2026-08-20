---
date: 2026-03-14
description: Aspose.Tasks का उपयोग करके Microsoft Project डेटाबेस के लिए डेटाबेस स्कीमा
  कैसे निर्दिष्ट करें, और .NET अनुप्रयोगों में प्रोजेक्ट डेटा कैसे आयात करें, यह सीखें।
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks के साथ प्रोजेक्ट DB के लिए डेटाबेस स्कीमा निर्दिष्ट करें
url: /hi/net/advanced-concepts/msp-database-settings/
weight: 19
---

 produce final content with all translations.

Check for any missed items: The heading "Settings for Microsoft Project Database in Aspose.Tasks" we translated.

Also "Quick Answers" -> "त्वरित उत्तर". Good.

Make sure to keep markdown formatting.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में Microsoft Project डेटाबेस के लिए सेटिंग्स

## परिचय

यदि आप Aspose.Tasks का उपयोग करके अपने .NET अनुप्रयोगों में Microsoft Project डेटाबेस के साथ काम कर रहे हैं, तो आपको **डेटाबेस स्कीमा निर्दिष्ट** करना होगा और आवश्यक सेटिंग्स को कॉन्फ़िगर करना होगा ताकि **प्रोजेक्ट डेटा** को सहजता से आयात किया जा सके। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से चरण‑दर‑चरण मार्गदर्शन करेगा, जिसमें **कनेक्शन विवरण को कॉन्फ़िगर करने** का तरीका, **.NET कनेक्शन स्ट्रिंग बनाना**, और अंत में **प्रोजेक्ट को MPP के रूप में सहेजना** दिखाया गया है।

## त्वरित उत्तर
- **मुख्य लक्ष्य क्या है?** डेटाबेस स्कीमा निर्दिष्ट करना और एक Project डेटाबेस को .NET ऐप में आयात करना।  
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Tasks for .NET।  
- **मैं Project Server से कैसे कनेक्ट करूँ?** उचित SQL कनेक्शन स्ट्रिंग बनाकर और `MspDbSettings` का उपयोग करके।  
- **कौनसा फ़ाइल फ़ॉर्मेट उत्पन्न होता है?** `SaveFileFormat.Mpp` के साथ सहेजी गई MPP फ़ाइल।  
- **क्या मैं स्कीमा नाम बदल सकता हूँ?** हाँ, `MspDbSettings` पर `Schema` प्रॉपर्टी सेट करें।

## Project DB के लिए डेटाबेस स्कीमा कैसे निर्दिष्ट करें

**डेटाबेस स्कीमा** को **निर्दिष्ट करने** की आवश्यकता क्यों हो सकती है, इसे समझना महत्वपूर्ण है। कई एंटरप्राइज़ वातावरण में Project Server डेटाबेस एक कस्टम स्कीमा (जैसे `dbo`, `psdata`) के तहत रहता है। स्कीमा को स्पष्ट रूप से सेट करके आप सुनिश्चित करते हैं कि Aspose.Tasks सही तालिकाओं को क्वेरी करे, जिससे रन‑टाइम त्रुटियों से बचा जा सके और डेटा आयात सटीक हो।

## पूर्वापेक्षाएँ

1. Aspose.Tasks for .NET: Aspose.Tasks लाइब्रेरी को [यहाँ](https://releases.aspose.com/tasks/net/) से डाउनलोड और इंस्टॉल करें।  
2. Microsoft Project डेटाबेस तक पहुँच: आपको डेटा आयात करने के लिए Microsoft Project डेटाबेस तक पहुँच होनी चाहिए।  

## नेमस्पेस आयात करें

पहले, सुनिश्चित करें कि आप अपने प्रोजेक्ट में आवश्यक नेमस्पेस आयात कर रहे हैं:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## चरण 1: कनेक्शन स्ट्रिंग बनाएं

अपने Microsoft Project डेटाबेस के लिए कनेक्शन स्ट्रिंग बनाएं। यहाँ आप **.NET कनेक्शन स्ट्रिंग** बनाते हैं और यह भी परिभाषित करते हैं कि **Project Server से कैसे कनेक्ट करें**।

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

> **प्रो टिप:** `DataSource` और `InitialCatalog` मानों को दोबारा जांचें; इन्हें आपके सर्वर के पते और प्रकाशित डेटाबेस नाम से मेल खाना चाहिए।

## चरण 2: MspDbSettings कॉन्फ़िगर करें

`MspDbSettings` का एक इंस्टेंस बनाएं, कनेक्शन स्ट्रिंग पास करें, और `Schema` प्रॉपर्टी सेट करके **डेटाबेस स्कीमा निर्दिष्ट** करें। यह Aspose.Tasks को बताता है कि कौन सा स्कीमा क्वेरी करना है।

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

यहाँ हम वह प्रोजेक्ट GUID भी प्रदान करते हैं जो उस विशिष्ट प्रोजेक्ट की पहचान करता है जिसे आप लोड करना चाहते हैं।

## चरण 3: प्रोजेक्ट डेटा लोड करें

कॉन्फ़िगर किए गए सेटिंग्स का उपयोग करके एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें। यह चरण प्रभावी रूप से डेटाबेस से **प्रोजेक्ट डेटा आयात करने** का काम करता है और उसे .NET ऑब्जेक्ट में बदलता है।

```csharp
var project = new Project(settings);
```

## चरण 4: प्रोजेक्ट डेटा सहेजें

अंत में, लोड किए गए प्रोजेक्ट को डिस्क पर एक MPP फ़ाइल में सहेजें। यह Aspose.Tasks API का उपयोग करके **प्रोजेक्ट को MPP के रूप में सहेजने** का प्रदर्शन है।

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

कोड चलाने के बाद, आपको आउटपुट डायरेक्टरी में `ImportProjectDataFromDatabase_out.mpp` फ़ाइल मिलेगी, जो Microsoft Project में खोलने के लिए तैयार है।

## निष्कर्ष

इस ट्यूटोरियल में, आपने **डेटाबेस स्कीमा** को Microsoft Project डेटाबेस के लिए कैसे **निर्दिष्ट** करें, **कनेक्शन को कॉन्फ़िगर** करें, **प्रोजेक्ट डेटा आयात** करें, और Aspose.Tasks for .NET का उपयोग करके **प्रोजेक्ट को MPP के रूप में सहेजें** यह सब सीखा। ये कदम Project Server डेटा को आपके कस्टम अनुप्रयोगों में सहजता से एकीकृत करने में मदद करते हैं, जिससे आप मजबूत प्रोजेक्ट‑मैनेजमेंट समाधान बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.Tasks को Microsoft Project डेटाबेस के विभिन्न संस्करणों के साथ उपयोग कर सकता हूँ?
**A1:** हाँ, Aspose.Tasks विभिन्न संस्करणों के Microsoft Project डेटाबेस को सपोर्ट करता है, जिससे एकीकरण में लचीलापन मिलता है।

### Q2: डेटाबेस के साथ कनेक्शन समस्याओं का समाधान कैसे करूँ?
**A2:** सुनिश्चित करें कि आपका कनेक्शन स्ट्रिंग उचित क्रेडेंशियल्स और डेटाबेस विवरणों के साथ सही ढंग से कॉन्फ़िगर किया गया है। आप दस्तावेज़ीकरण देख सकते हैं या [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) से सहायता ले सकते हैं।

### Q3: क्या Aspose.Tasks के लिए ट्रायल संस्करण उपलब्ध है?
**A3:** हाँ, आप [यहाँ](https://releases.aspose.com/) से एक मुफ्त ट्रायल संस्करण प्राप्त कर सकते हैं।

### Q4: क्या मैं डेटाबेस इंटरैक्शन के लिए स्कीमा को कस्टमाइज़ कर सकता हूँ?
**A4:** हाँ, आप अपने डेटाबेस संरचना के अनुसार `MspDbSettings` ऑब्जेक्ट के लिए स्कीमा निर्दिष्ट कर सकते हैं।

### Q5: Aspose.Tasks के उपयोग पर अधिक विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?
**A5:** आप Aspose.Tasks की कार्यक्षमताओं के विस्तृत अंतर्दृष्टि के लिए व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/tasks/net/) देख सकते हैं।

**प्रश्न:** क्या यह तरीका Azure SQL डेटाबेस के साथ काम करता है?  
**उत्तर:** बिल्कुल। बस `DataSource` को अपने Azure सर्वर नाम पर समायोजित करें और TLS/SSL सेटिंग्स को सक्षम रखें।

**प्रश्न:** बड़े Project डेटाबेस को टाइम‑आउट के बिना कैसे संभालूँ?  
**उत्तर:** कनेक्शन स्ट्रिंग में `ConnectTimeout` मान बढ़ाएँ और आवश्यक होने पर प्रोजेक्ट्स को बैच में लोड करने पर विचार करें।

---

**अंतिम अपडेट:** 2026-03-14  
**परीक्षण किया गया:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}