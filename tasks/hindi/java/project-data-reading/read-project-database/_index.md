---
date: 2025-12-13
description: Microsoft Project डेटाबेस को Aspose.Tasks for Java का उपयोग करके पढ़ना
  सीखें। कोड उदाहरणों और सर्वोत्तम प्रथाओं के साथ चरण-दर-चरण गाइड।
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ माइक्रोसॉफ्ट प्रोजेक्ट डेटाबेस पढ़ें
url: /hi/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ Microsoft Project डेटाबेस पढ़ें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **read microsoft project database** को सीधे Microsoft Project Server से Aspose.Tasks Java API का उपयोग करके कैसे पढ़ा जाए। चाहे आपको रिपोर्ट बनानी हो, डेटा माइग्रेट करना हो, या प्रोजेक्ट जानकारी को अपने स्वयं के एप्लिकेशन में एकीकृत करना हो, यह गाइड आपको हर चरण में ले जाता है—डेटाबेस कनेक्शन सेटअप से लेकर प्रोजेक्ट को XML में एक्सपोर्ट करने तक। अंत तक, आपके पास एक ठोस, प्रोडक्शन‑रेडी समाधान होगा जो होस्ट मशीन पर Microsoft Project इंस्टॉल किए बिना काम करता है।

## त्वरित उत्तर
- **Aspose.Tasks क्या करता है?** यह एक शुद्ध‑Java API प्रदान करता है जिससे आप Microsoft Project फ़ाइलों और डेटाबेस को पढ़, लिख और संशोधित कर सकते हैं।  
- **क्या मुझे Microsoft Project इंस्टॉल करना आवश्यक है?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **कौन सा डेटाबेस प्रकार समर्थित है?** Microsoft SQL Server (Project Server का बैकएंड)।  
- **क्या मैं अन्य फ़ॉर्मेट में एक्सपोर्ट कर सकता हूँ?** हाँ, XML के अलावा आप PDF, HTML, CSV और अधिक फ़ॉर्मेट में सहेज सकते हैं।  
- **मुख्य पूर्वापेक्षाएँ क्या हैं?** JDK, Aspose.Tasks for Java लाइब्रेरी, और SQL Server JDBC ड्राइवर।

## “read microsoft project database” क्या है?
Microsoft Project डेटाबेस पढ़ना मतलब Project Server के SQL Server रिपॉज़िटरी से कनेक्ट होकर संग्रहीत प्रोजेक्ट डेटा को निकालना और उसे एक `Project` ऑब्जेक्ट में लोड करना है जिसे Aspose.Tasks द्वारा मैनीपुलेट किया जा सकता है। यह तरीका स्वचालित रिपोर्टिंग, डेटा माइग्रेशन या कस्टम एनालिटिक्स के लिए आदर्श है।

## Aspose.Tasks for Java का उपयोग क्यों करें?
- **Microsoft Project निर्भरता नहीं** – किसी भी सर्वर या CI वातावरण में चलाएँ।  
- **समृद्ध ऑब्जेक्ट मॉडल** – कार्य, संसाधन, असाइनमेंट, कैलेंडर और कस्टम फ़ील्ड को प्रोग्रामेटिकली एक्सेस करें।  
- **एकाधिक एक्सपोर्ट विकल्प** – XML, PDF, HTML, PNG आदि, एक ही API कॉल से।  
- **उच्च प्रदर्शन** – बड़े एंटरप्राइज़ प्रोजेक्ट्स के लिए अनुकूलित।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. एक कार्यशील Java विकास वातावरण (JDK 8 या नया)।  
2. Aspose.Tasks for Java लाइब्रेरी आपके प्रोजेक्ट के क्लासपाथ में जोड़ी गई हो।  
3. Project Server SQL डेटाबेस के एक्सेस क्रेडेंशियल (सर्वर नाम, पोर्ट, डेटाबेस नाम, उपयोगकर्ता नाम, पासवर्ड)।  
4. Microsoft JDBC Driver for SQL Server (जैसे `sqljdbc4.jar`)।

## पैकेज आयात करें
सबसे पहले, उन क्लासों को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। सूची में Aspose.Tasks कोर क्लास और मानक Java यूटिलिटीज़ शामिल हैं।

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

## चरण 1: डेटाबेस कनेक्शन सेट अप करें
एक `MspDbSettings` इंस्टेंस बनाएं जो JDBC कनेक्शन स्ट्रिंग रखता है। प्लेसहोल्डर मानों को अपने वास्तविक सर्वर विवरण से बदलें।

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** कनेक्शन स्ट्रिंग को हार्ड‑कोडिंग करने के बजाय सुरक्षित कॉन्फ़िगरेशन फ़ाइल या एनवायरनमेंट वैरिएबल में रखें।

## चरण 2: JDBC ड्राइवर जोड़ें
रनटाइम पर Microsoft SQL Server JDBC ड्राइवर लोड करें ताकि JVM डेटाबेस से संवाद कर सके।

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** सुनिश्चित करें कि ड्राइवर का संस्करण आपके SQL Server संस्करण से मेल खाता हो। असंगत ड्राइवर से कनेक्शन विफल हो सकता है।

## चरण 3: प्रोजेक्ट डेटा पढ़ें
`MspDbSettings` को पास करके एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें। Aspose.Tasks स्वचालित रूप से डेटाबेस से प्रोजेक्ट डेटा फ़ेच करेगा।

```java
Project project = new Project(settings);
```

इस बिंदु पर आप `project` ऑब्जेक्ट का अन्वेषण कर सकते हैं—टास्क, रिसोर्स सूचीबद्ध करें या आवश्यकतानुसार फ़ील्ड संशोधित करें।

## चरण 4: प्रोजेक्ट डेटा सहेजें
लोड किए गए प्रोजेक्ट को अपनी पसंद के फ़ॉर्मेट में एक्सपोर्ट करें। नीचे दिया गया उदाहरण प्रोजेक्ट को XML के रूप में सहेजता है, जिसे बाद में Microsoft Project में इम्पोर्ट या आगे प्रोसेस किया जा सकता है।

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

आप `SaveFileFormat.Xml` को `Pdf`, `Html`, `Csv` आदि से बदल सकते हैं, अपनी रिपोर्टिंग आवश्यकताओं के अनुसार।

## सामान्य समस्याएँ और समाधान
| समस्या | सामान्य कारण | समाधान |
|-------|---------------|-----|
| **Connection timeout** | गलत सर्वर/पोर्ट या फ़ायरवॉल ब्लॉक कर रहा है | सर्वर एड्रेस सत्यापित करें, पोर्ट 1433 खोलें, और एक साधारण JDBC टेस्ट प्रोग्राम से कनेक्टिविटी जांचें। |
| **Authentication error** | अमान्य उपयोगकर्ता नाम/पासवर्ड या SQL Server में SQL ऑथेंटिकेशन कॉन्फ़िगर नहीं है | वैध SQL लॉगिन उपयोग करें या सर्वर पर मिक्स्ड‑मोड ऑथेंटिकेशन सक्षम करें। |
| **Driver not found** | JDBC jar क्लासपाथ में नहीं है | सुनिश्चित करें कि `addJDBCDriver` सही `.jar` फ़ाइल की ओर इशारा कर रहा है और पाथ में डबल बैकस्लैश (`\\`) उपयोग किया गया है। |
| **Empty project after load** | Project Server टेबल पढ़ने के लिए अपर्याप्त अनुमतियाँ | लॉगिन को Project Server डेटाबेस स्कीमा पर SELECT अधिकार प्रदान करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks को Microsoft Project के अलावा अन्य डेटाबेस से प्रोजेक्ट डेटा पढ़ने के लिए उपयोग किया जा सकता है?**  
A: हाँ, Aspose.Tasks विभिन्न स्रोतों से प्रोजेक्ट डेटा पढ़ने का समर्थन करता है, जिसमें XML फ़ाइलें, Primavera, और Microsoft Project डेटाबेस शामिल हैं।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों के Microsoft Project के साथ संगत है?**  
A: हाँ, Aspose.Tasks कई Microsoft Project संस्करणों के साथ काम करने के लिए डिज़ाइन किया गया है, जिससे सहज एकीकरण सुनिश्चित होता है।

**Q: क्या मैं सहेजने से पहले प्रोजेक्ट डेटा को संशोधित कर सकता हूँ?**  
A: बिल्कुल, Aspose.Tasks एक समृद्ध API प्रदान करता है जिससे आप टास्क जोड़ सकते हैं, रिसोर्स अपडेट कर सकते हैं, और एक्सपोर्ट से पहले प्रोजेक्ट प्रॉपर्टीज़ सेट कर सकते हैं।

**Q: क्या Aspose.Tasks कई आउटपुट फ़ॉर्मेट का समर्थन करता है?**  
A: हाँ, आप प्रोजेक्ट को XML, PDF, HTML, CSV, PNG, JPEG और अधिक फ़ॉर्मेट में सहेज सकते हैं।

**Q: मैं Aspose.Tasks के बारे में अतिरिक्त समर्थन या सहायता कहाँ पा सकता हूँ?**  
A: अतिरिक्त मदद के लिए, Aspose.Tasks फ़ोरम देखें या वेबसाइट पर उपलब्ध दस्तावेज़ीकरण का अन्वेषण करें [here](https://forum.aspose.com/c/tasks/15)।

## निष्कर्ष
इस चरण‑दर‑चरण गाइड का पालन करके, अब आप **read microsoft project database** को Aspose.Tasks for Java का उपयोग करके पढ़ना, डेटा प्रोग्रामेटिकली मैनीपुलेट करना, और अपनी आवश्यक फ़ॉर्मेट में एक्सपोर्ट करना जानते हैं। यह तरीका Microsoft Project पर निर्भरता को समाप्त करता है, स्वचालित रिपोर्टिंग को सरल बनाता है, और शक्तिशाली कस्टम इंटीग्रेशन के द्वार खोलता है।

---

**अंतिम अपडेट:** 2025-12-13  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.5 (लेखन के समय नवीनतम)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
