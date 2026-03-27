---
date: 2026-02-18
description: Aspose.Tasks for Java के साथ प्रोजेक्ट को PDF के रूप में सहेजना और Microsoft
  Project डेटाबेस पढ़ना सीखें, साथ ही Project Server से कनेक्ट करना, प्रोजेक्ट को
  HTML में बदलना, और प्रोजेक्ट को XML में निर्यात करना।
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट को PDF के रूप में सहेजें और Aspose.Tasks for Java के साथ प्रोजेक्ट
  DB पढ़ें
url: /hi/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट को PDF के रूप में सहेजें और Aspose.Tasks for Java के साथ Microsoft Project डेटाबेस पढ़ें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **Microsoft Project Server** से सीधे **Microsoft Project डेटाबेस** को कैसे पढ़ा जाए और फिर **Aspose.Tasks Java API** का उपयोग करके प्रोजेक्ट को PDF के रूप में कैसे सहेजा जाए। चाहे आपको रिपोर्ट बनानी हो, डेटा माइग्रेट करना हो, या प्रोजेक्ट जानकारी को अपने एप्लिकेशन में एकीकृत करना हो, यह गाइड आपको डेटाबेस कनेक्शन सेटअप से लेकर प्रोजेक्ट को PDF, XML या HTML में एक्सपोर्ट करने तक के हर चरण में मार्गदर्शन करता है। अंत तक, आपके पास एक ठोस, प्रोडक्शन‑रेडी समाधान होगा जो होस्ट मशीन पर Microsoft Project इंस्टॉल किए बिना काम करता है।

## त्वरित उत्तर
- **Aspose.Tasks क्या करता है?** यह एक शुद्ध‑Java API प्रदान करता है जिससे आप Microsoft Project फ़ाइलों और डेटाबेस को पढ़, लिख और संशोधित कर सकते हैं।  
- **क्या मुझे Microsoft Project इंस्टॉल करना होगा?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **कौन सा डेटाबेस प्रकार समर्थित है?** Microsoft SQL Server (Project Server का बैकएंड)।  
- **क्या मैं अन्य फ़ॉर्मेट में एक्सपोर्ट कर सकता हूँ?** हाँ, PDF के अलावा आप XML, HTML, CSV आदि में भी सहेज सकते हैं।  
- **मुख्य पूर्वापेक्षाएँ क्या हैं?** JDK, Aspose.Tasks for Java लाइब्रेरी, SQL Server JDBC ड्राइवर, और **Project Server से कनेक्ट करने** के लिए क्रेडेंशियल्स।

## “Microsoft Project डेटाबेस पढ़ना” क्या है?
Microsoft Project डेटाबेस पढ़ना का अर्थ है Project Server के SQL Server रिपॉज़िटरी से कनेक्ट होना, संग्रहीत प्रोजेक्ट डेटा को निकालना, और उसे एक `Project` ऑब्जेक्ट में लोड करना जिसे Aspose.Tasks मैनीपुलेट कर सकता है। यह तरीका स्वचालित रिपोर्टिंग, डेटा माइग्रेशन या कस्टम एनालिटिक्स के लिए आदर्श है।

## Aspose.Tasks for Java क्यों उपयोग करें?
- **Microsoft Project पर निर्भरता नहीं** – किसी भी सर्वर या CI वातावरण में चलाएँ।  
- **समृद्ध ऑब्जेक्ट मॉडल** – टास्क, रिसोर्स, असाइनमेंट, कैलेंडर और कस्टम फ़ील्ड्स को प्रोग्रामेटिकली एक्सेस करें।  
- **कई एक्सपोर्ट विकल्प** – PDF, XML, HTML, PNG आदि, एक ही API कॉल से।  
- **उच्च प्रदर्शन** – बड़े एंटरप्राइज़ प्रोजेक्ट्स के लिए अनुकूलित।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. एक कार्यशील Java विकास वातावरण (JDK 8 या नया)।  
2. Aspose.Tasks for Java लाइब्रेरी आपके प्रोजेक्ट के क्लासपाथ में जोड़ी गई हो।  
3. Project Server SQL डेटाबेस के लिए एक्सेस क्रेडेंशियल्स (सर्वर नाम, पोर्ट, डेटाबेस नाम, यूज़रनेम, पासवर्ड) **Project Server से कनेक्ट करने** के लिए।  
4. Microsoft JDBC ड्राइवर for SQL Server (जैसे `sqljdbc4.jar`)।

## पैकेज इम्पोर्ट करें
सबसे पहले, उन क्लासेस को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। सूची में Aspose.Tasks कोर क्लासेस और मानक Java यूटिलिटीज़ शामिल हैं।

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Project Server से कनेक्ट कैसे करें
एक विश्वसनीय कनेक्शन स्थापित करना प्रोजेक्ट डेटा पढ़ने की नींव है। सुनिश्चित करें कि SQL Server इंस्टेंस आपके Java होस्ट से पहुँच योग्य है और आपका लॉगिन Project Server स्कीमा पर **SELECT** अनुमतियों के साथ है।

## चरण 1: डेटाबेस कनेक्शन सेट अप करें
एक `MspDbSettings` इंस्टेंस बनाएं जो JDBC कनेक्शन स्ट्रिंग रखता है। प्लेसहोल्डर मानों को अपने वास्तविक सर्वर विवरणों से बदलें।

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **प्रो टिप:** कनेक्शन स्ट्रिंग को हार्ड‑कोड करने के बजाय सुरक्षित कॉन्फ़िगरेशन फ़ाइल या एनवायरनमेंट वैरिएबल में रखें।

## चरण 2: JDBC ड्राइवर जोड़ें
रनटाइम पर Microsoft SQL Server JDBC ड्राइवर लोड करें ताकि JVM डेटाबेस से संवाद कर सके।

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **चेतावनी:** ड्राइवर का संस्करण आपके SQL Server संस्करण से मेल खाना चाहिए। असंगत ड्राइवर कनेक्शन विफलता का कारण बन सकता है।

## चरण 3: प्रोजेक्ट डेटा पढ़ें
`MspDbSettings` को पास करके एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें। Aspose.Tasks डेटाबेस से स्वचालित रूप से प्रोजेक्ट डेटा फ़ेच करेगा।

```java
Project project = new Project(settings);
```

अब आप `project` ऑब्जेक्ट का अन्वेषण कर सकते हैं—टास्क, रिसोर्स लिस्ट करें या आवश्यकतानुसार फ़ील्ड्स को संशोधित करें।

## चरण 4: प्रोजेक्ट को PDF के रूप में सहेजें
लोड किए गए प्रोजेक्ट को अपनी पसंद के फ़ॉर्मेट में एक्सपोर्ट करें। नीचे दिया गया उदाहरण प्रोजेक्ट को **PDF** के रूप में सहेजता है, जो प्रिंटेबल रिपोर्ट्स के लिए उपयुक्त है। आप `SaveFileFormat` एन्नुम को बदलकर **XML** या **HTML** में भी एक्सपोर्ट कर सकते हैं।

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

यदि आप XML पसंद करते हैं, तो बस `SaveFileFormat.Pdf` को `SaveFileFormat.Xml` से बदलें। HTML आउटपुट के लिए `SaveFileFormat.Html` उपयोग करें।

## सामान्य समस्याएँ और समाधान
| समस्या | सामान्य कारण | समाधान |
|-------|---------------|-----|
| **कनेक्शन टाइमआउट** | गलत सर्वर/पोर्ट या फ़ायरवॉल ब्लॉक कर रहा है | सर्वर एड्रेस जाँचें, पोर्ट 1433 खोलें, और एक साधारण JDBC टेस्ट प्रोग्राम से कनेक्टिविटी टेस्ट करें। |
| **ऑथेंटिकेशन त्रुटि** | गलत यूज़रनेम/पासवर्ड या SQL Server पर SQL ऑथेंटिकेशन सेट नहीं है | वैध SQL लॉगिन उपयोग करें या सर्वर पर मिक्स्ड‑मोड ऑथेंटिकेशन सक्षम करें। |
| **ड्राइवर नहीं मिला** | JDBC jar क्लासपाथ में नहीं है | सुनिश्चित करें कि `addJDBCDriver` सही `.jar` फ़ाइल की ओर इशारा कर रहा है और पाथ में डबल बैकस्लैश (`\\`) उपयोग किए गए हैं। |
| **लोड के बाद प्रोजेक्ट खाली** | Project Server टेबल्स पढ़ने के लिए अपर्याप्त अनुमतियाँ | लॉगिन को Project Server डेटाबेस स्कीमा पर SELECT अधिकार दें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks को Microsoft Project के अलावा अन्य डेटाबेस से प्रोजेक्ट डेटा पढ़ने के लिए उपयोग किया जा सकता है?**  
उत्तर: हाँ, Aspose.Tasks विभिन्न स्रोतों से प्रोजेक्ट डेटा पढ़ने का समर्थन करता है, जिसमें XML फ़ाइलें, Primavera, और Microsoft Project डेटाबेस शामिल हैं।

**प्रश्न: क्या Aspose.Tasks विभिन्न संस्करणों के Microsoft Project के साथ संगत है?**  
उत्तर: हाँ, Aspose.Tasks कई Microsoft Project संस्करणों के साथ काम करने के लिए डिज़ाइन किया गया है, जिससे सहज इंटीग्रेशन सुनिश्चित होता है।

**प्रश्न: क्या मैं सहेजने से पहले प्रोजेक्ट डेटा को संशोधित कर सकता हूँ?**  
उत्तर: बिल्कुल, Aspose.Tasks एक समृद्ध API प्रदान करता है जिससे आप टास्क जोड़ सकते हैं, रिसोर्स अपडेट कर सकते हैं, और एक्सपोर्ट से पहले प्रोजेक्ट प्रॉपर्टीज़ सेट कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks कई आउटपुट फ़ॉर्मेट का समर्थन करता है?**  
उत्तर: हाँ, आप प्रोजेक्ट को PDF, XML, HTML, CSV, PNG, JPEG आदि के रूप में सहेज सकते हैं।

**प्रश्न: मैं Aspose.Tasks के बारे में अतिरिक्त समर्थन या सहायता कहाँ पा सकता हूँ?**  
उत्तर: अतिरिक्त मदद के लिए Aspose.Tasks फ़ोरम पर जाएँ या वेबसाइट पर उपलब्ध दस्तावेज़ीकरण देखें [here](https://forum.aspose.com/c/tasks/15)।

## निष्कर्ष
इस चरण‑दर‑चरण गाइड का पालन करके, अब आप जानते हैं कि **Microsoft Project डेटाबेस** को कैसे पढ़ें, **प्रोजेक्ट को PDF के रूप में सहेजें**, और Aspose.Tasks for Java का उपयोग करके अन्य फ़ॉर्मेट में एक्सपोर्ट करें। यह तरीका Microsoft Project पर निर्भरता को समाप्त करता है, स्वचालित रिपोर्टिंग को सरल बनाता है, और शक्तिशाली कस्टम इंटीग्रेशन के द्वार खोलता है।

---

**अंतिम अपडेट:** 2026-02-18  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.5 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}