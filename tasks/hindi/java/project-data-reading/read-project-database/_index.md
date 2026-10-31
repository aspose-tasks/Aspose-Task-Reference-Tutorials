---
date: 2026-10-31
description: Aspose.Tasks for Java के साथ प्रोजेक्ट को PDF के रूप में सहेजना और Microsoft
  Project डेटाबेस पढ़ना सीखें, साथ ही Project Server से कनेक्ट करें, प्रोजेक्ट को
  HTML में बदलें, और XML में निर्यात करें।
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Aspose.Tasks में Microsoft Project डेटाबेस से प्रोजेक्ट डेटा पढ़ना
og_description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को PDF के रूप में सहेजें
  और Microsoft Project डेटाबेस पढ़ें। Project Server से कनेक्ट करना, HTML, XML, और
  CSV में निर्यात करना सीखें।
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Aspose.Tasks for Java के साथ प्रोजेक्ट को PDF के रूप में सहेजें और Microsoft
  Project डेटाबेस पढ़ें
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Aspose.Tasks for Java के साथ प्रोजेक्ट को PDF के रूप में सहेजें और Microsoft
  Project डेटाबेस पढ़ें
url: /hi/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट को PDF के रूप में सहेजें और Aspose.Tasks for Java के साथ Microsoft Project डेटाबेस पढ़ें

## परिचय
इस ट्यूटोरियल में आप **Microsoft Project डेटाबेस** को सीधे Microsoft Project Server से पढ़ना और फिर **Aspose.Tasks Java API** का उपयोग करके प्रोजेक्ट को PDF के रूप में सहेजना सीखेंगे। चाहे आपको प्रिंटेबल रिपोर्ट बनानी हो, लेगेसी डेटा माइग्रेट करना हो, या प्रोजेक्ट जानकारी को कस्टम पोर्टल में एम्बेड करना हो, यह गाइड आपको प्रत्येक चरण के माध्यम से ले जाएगा—JDBC कनेक्शन को कॉन्फ़िगर करने से लेकर प्रोजेक्ट को PDF, XML, या HTML में एक्सपोर्ट करने तक। अंत तक, आपके पास एक प्रोडक्शन‑रेडी समाधान होगा जो किसी भी Java सर्वर पर Microsoft Project इंस्टॉल किए बिना चल सकता है।

## त्वरित उत्तर
- **Aspose.Tasks क्या करता है?** यह Microsoft Project फ़ाइलों और डेटाबेस को पढ़ने, लिखने और संशोधित करने के लिए एक शुद्ध‑Java API प्रदान करता है।  
- **क्या मुझे Microsoft Project इंस्टॉल करना आवश्यक है?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **कौन सा डेटाबेस प्रकार समर्थित है?** Microsoft SQL Server, जो Project Server का बैकएंड है।  
- **क्या मैं अन्य फ़ॉर्मेट में एक्सपोर्ट कर सकता हूँ?** हाँ—PDF, XML, HTML, CSV, PNG, JPEG, और अधिक।  
- **मुख्य पूर्वापेक्षाएँ क्या हैं?** JDK 8 या नया, Aspose.Tasks for Java लाइब्रेरी, SQL Server JDBC ड्राइवर, और वैध Project Server क्रेडेंशियल्स।

## “Microsoft Project डेटाबेस पढ़ना” क्या है?
Microsoft Project डेटाबेस पढ़ना का अर्थ है Project Server के SQL Server रिपॉज़िटरी से कनेक्ट होना, संग्रहीत प्रोजेक्ट डेटा को निकालना, और उसे एक `Project` ऑब्जेक्ट में लोड करना जिसे Aspose.Tasks मैनीपुलेट कर सकता है। यह तरीका स्वचालित रिपोर्टिंग, डेटा माइग्रेशन, या कस्टम एनालिटिक्स के लिए आदर्श है।

## Aspose.Tasks for Java क्यों उपयोग करें?
Aspose.Tasks for Java आपको Microsoft Project डेटा के साथ डेस्कटॉप एप्लिकेशन की आवश्यकता के बिना काम करने देता है, जिससे कोई भी प्लेटफ़ॉर्म पर चलने वाला शुद्ध‑Java समाधान मिलता है। यह टास्क, रिसोर्स, कैलेंडर, और कस्टम फ़ील्ड के लिए व्यापक ऑब्जेक्ट मॉडल प्रदान करता है, और बड़े एंटरप्राइज़ प्रोजेक्ट्स को कुशलता से संभालता है, जिससे यह स्वचालित रिपोर्टिंग, माइग्रेशन, और इंटीग्रेशन परिदृश्यों के लिए उपयुक्त बनता है।

- **Microsoft Project पर निर्भरता नहीं** – किसी भी सर्वर या CI वातावरण पर चलाएँ।  
- **समृद्ध ऑब्जेक्ट मॉडल** – टास्क, रिसोर्स, असाइनमेंट, कैलेंडर, और कस्टम फ़ील्ड को प्रोग्रामेटिकली एक्सेस करें।  
- **कई एक्सपोर्ट विकल्प** – Aspose.Tasks **20 से अधिक फ़ाइल फ़ॉर्मेट** में एक्सपोर्ट का समर्थन करता है, जिसमें PDF, XML, HTML, CSV, PNG, और JPEG शामिल हैं, एक ही API कॉल के साथ।  
- **उच्च प्रदर्शन** – लाइब्रेरी **10,000 टास्क** तक वाले प्रोजेक्ट को एक मिनट से कम समय में प्रोसेस कर सकती है, और डेटा को स्ट्रीम करके पूरी फ़ाइल को मेमोरी में लोड करने से बचाती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. एक कार्यशील Java विकास वातावरण (JDK 8 या नया)।  
2. आपके प्रोजेक्ट की क्लासपाथ में Aspose.Tasks for Java लाइब्रेरी जोड़ी गई हो।  
3. Project Server SQL डेटाबेस के लिए एक्सेस क्रेडेंशियल्स (सर्वर नाम, पोर्ट, डेटाबेस नाम, उपयोगकर्ता नाम, पासवर्ड) ताकि Project Server से कनेक्ट किया जा सके।  
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

## Project Server से कनेक्ट कैसे करें
एक विश्वसनीय कनेक्शन स्थापित करना प्रोजेक्ट डेटा पढ़ने की नींव है। सुनिश्चित करें कि SQL Server इंस्टेंस आपके Java होस्ट से पहुँच योग्य है और आपका लॉगिन Project Server स्कीमा पर **SELECT** अनुमति रखता है। नेटवर्क लेटेंसी की जाँच करें और आवश्यक SSL सेटिंग्स को कॉन्फ़िगर करके सुरक्षित संचार सुनिश्चित करें।

## चरण 1: डेटाबेस कनेक्शन सेट अप करें
`MspDbSettings` क्लास JDBC कनेक्शन विवरण को समेटे हुए है, जो Microsoft Project Server डेटाबेस तक पहुँचने के लिए आवश्यक है। एक `MspDbSettings` इंस्टेंस बनाएँ जो JDBC कनेक्शन स्ट्रिंग रखता हो। प्लेसहोल्डर मानों को अपने वास्तविक सर्वर विवरण से बदलें।

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **प्रो टिप:** कनेक्शन स्ट्रिंग को हार्ड‑कोडिंग करने के बजाय सुरक्षित कॉन्फ़िगरेशन फ़ाइल या एनवायरनमेंट वैरिएबल में रखें।

## चरण 2: JDBC ड्राइवर जोड़ें
रनटाइम पर Microsoft SQL Server JDBC ड्राइवर लोड करें ताकि JVM डेटाबेस के साथ संवाद कर सके।

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **चेतावनी:** सुनिश्चित करें कि ड्राइवर संस्करण आपके SQL Server संस्करण से मेल खाता हो। असंगत ड्राइवर के कारण कनेक्शन विफल हो सकता है।

## चरण 3: प्रोजेक्ट डेटा पढ़ें
`Project` क्लास एक Microsoft Project फ़ाइल को मेमोरी में लोड किया गया प्रतिनिधित्व करता है, जो टास्क, रिसोर्स, और असाइनमेंट को उजागर करता है। `MspDbSettings` को पास करके एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें। Aspose.Tasks स्वचालित रूप से डेटाबेस से प्रोजेक्ट डेटा फ़ेच करेगा।

```java
Project project = new Project(settings);
```

इस बिंदु पर आप `project` ऑब्जेक्ट का अन्वेषण कर सकते हैं—टास्क, रिसोर्स सूचीबद्ध करें, या आवश्यकतानुसार फ़ील्ड संशोधित करें।

## चरण 4: प्रोजेक्ट को PDF के रूप में सहेजें
`SaveFileFormat` एनेमरेशन `Project.save` मेथड के आउटपुट फ़ॉर्मेट को परिभाषित करता है, जैसे PDF, XML, या HTML। लोड किए गए प्रोजेक्ट को अपनी पसंद के फ़ॉर्मेट में एक्सपोर्ट करें। नीचे दिया गया उदाहरण प्रोजेक्ट को **PDF** के रूप में सहेजता है, जो प्रिंटेबल रिपोर्ट के लिए उपयुक्त है। आप `SaveFileFormat` एनेम को बदलकर **XML** या **HTML** में भी एक्सपोर्ट कर सकते हैं।

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

यदि आप XML पसंद करते हैं, तो `SaveFileFormat.Pdf` को `SaveFileFormat.Xml` से बदलें। HTML आउटपुट के लिए `SaveFileFormat.Html` उपयोग करें।

## सामान्य समस्याएँ और समाधान
| समस्या | सामान्य कारण | समाधान |
|-------|---------------|-----|
| **कनेक्शन टाइमआउट** | गलत सर्वर/पोर्ट या फ़ायरवॉल ब्लॉक कर रहा है | सर्वर एड्रेस सत्यापित करें, पोर्ट 1433 खोलें, और साधारण JDBC टेस्ट प्रोग्राम से कनेक्टिविटी जांचें। |
| **प्रमाणीकरण त्रुटि** | अमान्य उपयोगकर्ता नाम/पासवर्ड या SQL Server SQL प्रमाणीकरण के लिए कॉन्फ़िगर नहीं है | वैध SQL लॉगिन उपयोग करें या सर्वर पर मिश्रित‑मोड प्रमाणीकरण सक्षम करें। |
| **ड्राइवर नहीं मिला** | JDBC jar क्लासपाथ में नहीं है | सुनिश्चित करें कि `addJDBCDriver` सही `.jar` फ़ाइल की ओर इशारा कर रहा है और पाथ में डबल बैकस्लैश (`\\`) उपयोग किए गए हैं। |
| **लोड के बाद प्रोजेक्ट खाली** | Project Server टेबल्स को पढ़ने के लिए अपर्याप्त अनुमतियाँ | लॉगिन को Project Server डेटाबेस स्कीमा पर SELECT अधिकार प्रदान करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks को Microsoft Project के अलावा अन्य डेटाबेस से प्रोजेक्ट डेटा पढ़ने के लिए उपयोग किया जा सकता है?**  
उत्तर: हाँ, Aspose.Tasks XML फ़ाइलों, Primavera डेटाबेस, और अन्य मानक प्रोजेक्ट फ़ॉर्मेट से प्रोजेक्ट डेटा पढ़ने का समर्थन करता है।

**प्रश्न: क्या Aspose.Tasks विभिन्न संस्करणों के Microsoft Project के साथ संगत है?**  
उत्तर: हाँ, लाइब्रेरी Microsoft Project 2007 से लेकर नवीनतम 2024 रिलीज़ तक के साथ काम करती है, जिससे संस्करणों के बीच सहज इंटीग्रेशन सुनिश्चित होता है।

**प्रश्न: क्या मैं सहेजने से पहले प्रोजेक्ट डेटा को संशोधित कर सकता हूँ?**  
उत्तर: बिल्कुल, आप समृद्ध API का उपयोग करके टास्क, रिसोर्स, और कस्टम फ़ील्ड को जोड़, अपडेट या हटाकर एक्सपोर्ट से पहले डेटा को बदल सकते हैं।

**प्रश्न: क्या Aspose.Tasks कई आउटपुट फ़ॉर्मेट का समर्थन करता है?**  
उत्तर: हाँ, आप प्रोजेक्ट को PDF, XML, HTML, CSV, PNG, JPEG, और अधिक—कुल 20 से अधिक फ़ॉर्मेट में सहेज सकते हैं।

**प्रश्न: Aspose.Tasks के बारे में अतिरिक्त सहायता या समर्थन कहाँ प्राप्त कर सकता हूँ?**  
उत्तर: अतिरिक्त मदद के लिए Aspose.Tasks फ़ोरम देखें या वेबसाइट पर उपलब्ध दस्तावेज़ीकरण का अन्वेषण करें [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)।

## निष्कर्ष
इस चरण‑दर‑चरण गाइड का पालन करके, अब आप **Microsoft Project डेटाबेस पढ़ना**, **प्रोजेक्ट को PDF के रूप में सहेजना**, और Aspose.Tasks for Java का उपयोग करके अन्य फ़ॉर्मेट में एक्सपोर्ट करना जानते हैं। यह तरीका Microsoft Project पर निर्भरता को समाप्त करता है, स्वचालित रिपोर्टिंग को सरल बनाता है, और शक्तिशाली कस्टम इंटीग्रेशन के द्वार खोलता है।

---

**अंतिम अपडेट:** 2026-10-31  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.5 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [How to Save Project as PDF with Aspose.Tasks – Export Guide](/tasks/java/project-file-operations/save-as-pdf/)
- [Save Project as PDF – Render Task Sheet with Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}