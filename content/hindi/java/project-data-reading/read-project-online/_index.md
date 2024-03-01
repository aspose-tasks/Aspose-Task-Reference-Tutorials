---
title: Aspose.Tasks के साथ सहज एमएस प्रोजेक्ट ऑनलाइन डेटा रीडिंग
linktitle: Aspose.Tasks में प्रोजेक्ट ऑनलाइन डेटा पढ़ना
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट ऑनलाइन डेटा को आसानी से पढ़ने का तरीका जानें। अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाएँ।
type: docs
weight: 13
url: /hi/java/project-data-reading/read-project-online/
---
## परिचय
परियोजना प्रबंधन के क्षेत्र में, सुव्यवस्थित संचालन के लिए Microsoft प्रोजेक्ट ऑनलाइन डेटा को कुशलतापूर्वक संभालना महत्वपूर्ण है। जावा के लिए Aspose.Tasks ऐसे डेटा को आसानी से पढ़ने के लिए एक मजबूत समाधान प्रदान करता है। यह ट्यूटोरियल एमएस प्रोजेक्ट ऑनलाइन डेटा को निर्बाध रूप से एक्सेस करने और उसमें हेरफेर करने के लिए Aspose.Tasks का लाभ उठाने के बारे में विस्तार से बताता है।
## आवश्यक शर्तें
इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (जेडीके): जावा प्रोग्राम संकलित करने और चलाने के लिए जेडीके स्थापित करें।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी को डाउनलोड करें और अपने जावा प्रोजेक्ट में शामिल करें। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. माइक्रोसॉफ्ट प्रोजेक्ट ऑनलाइन खाता: एमएस प्रोजेक्ट ऑनलाइन डेटा तक पहुंचने के लिए वैध क्रेडेंशियल प्राप्त करें।
4. SharePoint डोमेन पता: SharePoint डोमेन पता जहां आपका MS प्रोजेक्ट ऑनलाइन डेटा रहता है।
5. उपयोगकर्ता नाम और पासवर्ड: एमएस प्रोजेक्ट ऑनलाइन तक पहुंच प्रमाणित करने के लिए क्रेडेंशियल।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, निर्बाध एकीकरण के लिए आवश्यक Aspose.Tasks पैकेज आयात करें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## चरण 1: SharePoint डोमेन पता, उपयोगकर्ता नाम और पासवर्ड सेट करें
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 प्रतिस्थापित करें`"https://contoso.sharepoint.com"` आपके SharePoint डोमेन पते के साथ,`"admin@contoso.onmicrosoft.com"` आपके उपयोगकर्ता नाम के साथ, और`"MyPassword"` आपके पासवर्ड के साथ.
## चरण 2: प्रोजेक्ट सर्वर क्रेडेंशियल्स के साथ प्रमाणित करें
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 बनाएं`ProjectServerCredentials` SharePoint डोमेन पते, उपयोगकर्ता नाम और पासवर्ड के साथ ऑब्जेक्ट। फिर आरंभ करें`ProjectServerManager` इन प्रमाण पत्रों के साथ.
## चरण 3: परियोजना सूची प्राप्त करें और जानकारी प्रदर्शित करें
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 से प्राप्त परियोजना सूची के माध्यम से पुनरावृति करें`reader.getProjectList()` और प्रोजेक्ट विवरण जैसे नाम, निर्माण तिथि और अंतिम सहेजी गई तिथि प्रदर्शित करें।
## चरण 4: व्यक्तिगत प्रोजेक्ट और आउटपुट संसाधन गणना लोड करें
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 प्रत्येक प्रोजेक्ट के लिए, इसका उपयोग करके लोड करें`reader.getProject(p.getId())` और संबंधित संसाधनों की गिनती के साथ प्रोजेक्ट का नाम आउटपुट करें।

## निष्कर्ष
जावा के लिए Aspose.Tasks एमएस प्रोजेक्ट ऑनलाइन डेटा को पढ़ने की प्रक्रिया को सरल बनाता है, डेवलपर्स को प्रोजेक्ट प्रबंधन कार्यों को सुव्यवस्थित करने के लिए एक शक्तिशाली टूलसेट प्रदान करता है। इस ट्यूटोरियल का अनुसरण करके, आप आसानी से प्रोजेक्ट डेटा तक पहुंचने और हेरफेर करने के लिए Aspose.Tasks को अपने जावा एप्लिकेशन में कुशलतापूर्वक एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं एमएस प्रोजेक्ट ऑनलाइन डेटा को संशोधित करने के लिए जावा के लिए Aspose.Tasks का उपयोग कर सकता हूं?
उत्तर: हां, Aspose.Tasks न केवल पढ़ने के लिए बल्कि एमएस प्रोजेक्ट ऑनलाइन डेटा को प्रोग्रामेटिक रूप से संशोधित करने के लिए भी व्यापक क्षमताएं प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks अन्य परियोजना प्रबंधन फ़ाइल स्वरूपों का समर्थन करता है?
उत्तर: बिल्कुल, Aspose.Tasks एमपीपी, एक्सएमएल और अन्य सहित विभिन्न फ़ाइल स्वरूपों का समर्थन करता है, जो विविध परियोजना प्रबंधन प्रणालियों के साथ संगतता सुनिश्चित करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/) Aspose.Tasks की विशेषताओं और कार्यप्रणाली का पता लगाने के लिए।
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए व्यापक दस्तावेज़ कहां पा सकता हूं?
 उ: आप विस्तृत दस्तावेज़ देख सकते हैं[यहाँ](https://reference.aspose.com/tasks/java/)आपके जावा प्रोजेक्ट्स में Aspose.Tasks के उपयोग पर व्यापक मार्गदर्शन के लिए।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए कौन से समर्थन विकल्प उपलब्ध हैं?
 उत्तर: यदि आपको कोई समस्या आती है या आपके कोई प्रश्न हैं, तो आप Aspose.Tasks सामुदायिक मंच से सहायता ले सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).