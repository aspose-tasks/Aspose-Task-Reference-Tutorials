---
date: 2025-12-17
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को PDF में निर्यात करना,
  फुटर गैप को कम करना, और प्रोजेक्ट को इमेज के रूप में सहेजना सीखें। अपने MS Project
  लेआउट को आसानी से अनुकूलित करें।
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में प्रोजेक्ट को PDF में निर्यात करें और टास्क सूची व फुटर के
  बीच का अंतर कम करें
url: /hi/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में प्रोजेक्ट को PDF में निर्यात करें और टास्क सूची व फुटर के बीच का गैप कम करें

## परिचय  
इस ट्यूटोरियल में आप **प्रोजेक्ट को PDF में निर्यात करने** का तरीका सीखेंगे, साथ ही Microsoft Project फ़ाइलों में टास्क सूची और फुटर के बीच अनावश्यक स्पेस को कम करेंगे। गाइड के अंत तक आप Aspose.Tasks for Java का उपयोग करके साफ़ PDF, PNG इमेज, और HTML पेजेज़ को कॉम्पैक्ट लेआउट के साथ जेनरेट कर पाएँगे। चलिए प्रक्रिया को चरण‑दर‑चरण देखते हैं।

## जल्दी जवाब
- **“export project to PDF” क्या है?** यह एक MPP फ़ाइल को PDF दस्तावेज़ में बदल देता है, जिसमें टास्क, टाइमलाइन और फ़ॉर्मेटिंग संरक्षित रहती है।  
- **footer gap को क्यों कम करें?** छोटा गैप अधिक सघन, पेशेवर‑दिखावट वाले रिपोर्ट बनाता है, विशेषकर प्रिंटेड या वेब‑व्यू दस्तावेज़ों के लिए।  
- **क्या मैं प्रोजेक्ट को इमेज के रूप में भी सेव कर सकता हूँ?** हाँ – Aspose.Tasks PNG, JPEG और अन्य इमेज फ़ॉर्मेट्स को सपोर्ट करता है।  
- **क्या मुझे विशेष लाइसेंस चाहिए?** एक फ्री ट्रायल उपलब्ध है; प्रोडक्शन उपयोग के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर का संस्करण वर्तमान Aspose.Tasks लाइब्रेरी के साथ काम करता है।

## “एक्सपोर्ट प्रोजेक्ट टू PDF” क्या है?  
प्रोजेक्ट को PDF में निर्यात करना आंतरिक MPP स्ट्रक्चर को एक पोर्टेबल डॉक्यूमेंट में बदल देता है, जिसे किसी भी डिवाइस पर Microsoft Project की आवश्यकता के बिना खोला जा सकता है। यह स्टेटस रिपोर्ट, स्टेकहोल्डर अपडेट या प्रोजेक्ट प्लान को आर्काइव करने के लिए आदर्श है।

## फुटर गैप क्यों कम करें?  
डिफ़ॉल्ट फुटर गैप अनावश्यक व्हाइट स्पेस जोड़ सकता है, जिससे पेजिनेशन समस्याएँ और असंतुलित लुक बनता है। गैप को कम करने से आपका कंटेंट पेज का अधिकतम उपयोग करता है, जिससे अंतिम PDF या इमेज अधिक पठनीय बनती है।

## टास्क लिस्ट और फुटर के बीच गैप कैसे कम करें?  
Aspose.Tasks इमेज, PDF और HTML सेव ऑपरेशन्स के लिए `setReduceFooterGap(true)` विकल्प प्रदान करता है। इस फ़्लैग को एनेबल करने से इंजन अंतिम टास्क रो और पेज फुटर के बीच की स्पेस को संकुचित कर देता है।

## Aspose.Tasks के साथ प्रोजेक्ट को इमेज के तौर पर सेव करें  
यदि आपको अपने शेड्यूल का विज़ुअल स्नैपशॉट चाहिए, तो आप **प्रोजेक्ट को इमेज (PNG) के रूप में सेव** कर सकते हैं, साथ ही वही गैप‑रिडक्शन सेटिंग्स लागू कर सकते हैं।

## Java प्रोजेक्ट एक्सपोर्ट टू PDF  
निम्नलिखित सेक्शन एक पूर्ण **java प्रोजेक्ट एक्सपोर्ट** वर्कफ़्लो को कवर करते हैं, MPP फ़ाइल लोड करने से लेकर तीन अलग‑अलग फ़ॉर्मेट्स में सेव करने तक।

## ज़रूरी शर्तें
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स हैं:
1. Java Development Kit (JDK) – संस्करण 8 या बाद का।  
2. Aspose.Tasks for Java Library – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## पैकेज इंपोर्ट करें
कोडिंग भाग में डुबकी लगाने से पहले, आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## स्टेप 1: अपनी डेटा डायरेक्टरी का पाथ दें
```java
String dataDir = "Your Data Directory";
```
सुनिश्चित करें कि `"Your Data Directory"` को उस वास्तविक डेटा डायरेक्टरी के पाथ से बदलें जहाँ आपका Microsoft Project फ़ाइल (`HomeMovePlan.mpp` इस उदाहरण में) स्थित है।

## स्टेप 2: MPP फ़ाइल पढ़ें
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
यह कोड लाइन `HomeMovePlan.mpp` नामक Microsoft Project फ़ाइल को पढ़ती है।

## स्टेप 3: ImageSaveOptions सेट करें (प्रोजेक्ट को इमेज के तौर पर सेव करें)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
इमेज सेव ऑप्शन को कॉन्फ़िगर करें, `ReduceFooterGap` को `true` सेट करके टास्क सूची और फुटर के बीच का गैप कम करें।

## स्टेप 4: इमेज के तौर पर सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को इमेज के रूप में सेव करें।

## स्टेप 5: PdfSaveOptions सेट करें (प्रोजेक्ट को PDF में एक्सपोर्ट करें)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
PDF सेव ऑप्शन को परिभाषित करें, सुनिश्चित करें कि `ReduceFooterGap` को `true` सेट किया गया है।

## स्टेप 6: PDF के तौर पर सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को PDF के रूप में सेव करें।

## स्टेप 7: HtmlSaveOptions सेट करें
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
HTML सेव ऑप्शन निर्दिष्ट करें, `ReduceFooterGap` को `true` सेट करें।

## स्टेप 8: HTML के तौर पर सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को HTML फ़ाइल के रूप में सेव करें।

## निष्कर्ष
संक्षेप में, Microsoft Project फ़ाइलों में टास्क सूची और फुटर के बीच का गैप कम करना Aspose.Tasks for Java के साथ एक सरल प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके आप प्रभावी रूप से **प्रोजेक्ट को PDF में निर्यात**, इमेज के रूप में सेव, या HTML जेनरेट कर सकते हैं, जबकि लेआउट सघन और प्रोफेशनल बना रहता है।

## अक्सर पूछे जाने वाले सवाल (और भी)

**Q: फुटर गैप को कम करने से पेजिनेशन पर क्या असर पड़ता है?**  
A: यह प्रत्येक पेज के नीचे के खाली स्पेस को न्यूनतम करता है, जिससे एक पेज पर अधिक टास्क फिट हो पाते हैं और कुल पेज काउंट घट जाता है।

**Q: क्या मैं केवल एक ही पेज पर वही गैप‑रिडक्शन सेटिंग लागू कर सकता हूँ?**  
A: हाँ, `ImageSaveOptions` में `setRenderToSinglePage(true)` सेट करके आप पेजिनेशन को नियंत्रित कर सकते हैं जबकि गैप को अभी भी कम कर सकते हैं।

**Q: क्या `setReduceFooterGap` विकल्प अन्य आउटपुट फ़ॉर्मेट्स के लिए उपलब्ध है?**  
A: वर्तमान में यह PNG, PDF और HTML एक्सपोर्ट्स के लिए सपोर्टेड है। अन्य फ़ॉर्मेट्स के लिए आपको लेआउट को मैन्युअली समायोजित करना पड़ सकता है।

**Q: यदि मेरे प्रोजेक्ट में कस्टम फ़ील्ड्स हैं—क्या वे संरक्षित रहते हैं?**  
A: सभी कस्टम फ़ील्ड्स एक्सपोर्ट के दौरान बरकरार रहते हैं; लेआउट समायोजन केवल स्पेसिंग को प्रभावित करता है, डेटा को नहीं।

**Q: क्या लाइब्रेरी बड़े प्रोजेक्ट्स को कुशलता से संभालती है?**  
A: Aspose.Tasks डेटा को स्ट्रीम करता है और बड़े MPP फ़ाइलों को प्रोसेस कर सकता है; हालांकि, हाई‑रेज़ोल्यूशन इमेजेज़ में एक्सपोर्ट करते समय पर्याप्त मेमोरी सुनिश्चित करें।

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}