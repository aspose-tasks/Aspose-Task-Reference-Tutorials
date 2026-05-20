---
date: 2026-05-20
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को PDF में निर्यात करना,
  फुटर का अंतर कम करना, और प्रोजेक्ट को इमेज के रूप में सहेजना सीखें। अपने MS Project
  लेआउट को आसानी से अनुकूलित करें।
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Aspose.Tasks में प्रोजेक्ट को PDF में निर्यात करें और टास्क सूची और फुटर
  के बीच का अंतर कम करें
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में प्रोजेक्ट को PDF में निर्यात करें और टास्क सूची और फुटर के
  बीच का अंतर कम करें
url: /hi/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट को PDF में निर्यात करें और Aspose.Tasks में टास्क सूची और फुटर के बीच का अंतर कम करें

## परिचय
इस ट्यूटोरियल में आप **how to export project to PDF** को खोजेंगे जबकि Microsoft Project फ़ाइलों में टास्क सूची और फुटर के बीच अनावश्यक स्पेस को भी कम करेंगे। गाइड के अंत तक आप Aspose.Tasks for Java का उपयोग करके साफ़ PDFs, PNG इमेजेज, और HTML पेजेज को कॉम्पैक्ट लेआउट के साथ जेनरेट कर पाएँगे। आइए प्रक्रिया को चरण‑दर‑चरण देखें, और आप समझेंगे कि यह प्रोफेशनल रिपोर्टिंग के लिए क्यों महत्वपूर्ण है।

## त्वरित उत्तर
- **“export project to PDF” का क्या अर्थ है?** यह एक MPP फ़ाइल को PDF दस्तावेज़ में बदल देता है, जिसमें टास्क, टाइमलाइन और फ़ॉर्मेटिंग संरक्षित रहती है।  
- **फुटर गैप को क्यों कम करें?** छोटा गैप अधिक सघन, अधिक प्रोफेशनल दिखने वाली रिपोर्ट बनाता है, विशेष रूप से प्रिंटेड या वेब‑व्यूड दस्तावेज़ों के लिए।  
- **क्या मैं प्रोजेक्ट को इमेज के रूप में भी सेव कर सकता हूँ?** हाँ – Aspose.Tasks PNG, JPEG और अन्य इमेज फ़ॉर्मेट्स को सपोर्ट करता है।  
- **क्या मुझे विशेष लाइसेंस चाहिए?** एक फ्री ट्रायल उपलब्ध है; प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर का संस्करण वर्तमान Aspose.Tasks लाइब्रेरी के साथ काम करता है।  

## “export project to PDF” क्या है?
एक प्रोजेक्ट को PDF में निर्यात करने से आंतरिक MPP संरचना एक पोर्टेबल दस्तावेज़ में बदल जाती है जिसे किसी भी डिवाइस पर Microsoft Project की आवश्यकता के बिना खोला जा सकता है। यह स्टेटस रिपोर्ट, स्टेकहोल्डर अपडेट या प्रोजेक्ट प्लान को आर्काइव करने के लिए आदर्श है। यह मूल लेआउट, रंग और टास्क हायरार्की को संरक्षित रखता है, जिससे PDF स्रोत फ़ाइल के समान दिखता है।

## फुटर गैप को क्यों कम करें?
डिफ़ॉल्ट फुटर गैप अनावश्यक व्हाइट स्पेस जोड़ सकता है, जिससे पेजिनेशन समस्याएँ और असंतुलित रूप बनता है। गैप को कम करने से आपका कंटेंट पेज को प्रभावी ढंग से उपयोग करता है, जिससे अंतिम PDF या इमेज अधिक पढ़ने योग्य बनती है। सघन लेआउट कुल पेज संख्या को भी घटाता है, जिससे प्रिंटिंग लागत कम हो सकती है और ऑन‑स्क्रीन नेविगेशन बेहतर होता है।

## टास्क सूची और फुटर के बीच गैप को कैसे कम करें?
`setReduceFooterGap` एक Boolean प्रॉपर्टी है जो निर्यात के दौरान फुटर स्पेसिंग को नियंत्रित करती है.  
Aspose.Tasks `setReduceFooterGap(true)` विकल्प प्रदान करता है इमेज, PDF, और HTML सेव ऑपरेशन्स के लिए. इस फ़्लैग को सक्षम करने से इंजन अंतिम टास्क रो और पेज फुटर के बीच की जगह को संकुचित करता है. जब इसे true सेट किया जाता है, तो रेंडरर स्वचालित रूप से मार्जिन को ट्रिम कर देता है बिना किसी टास्क डेटा को काटे, जिससे एक साफ़ पेज लेआउट मिलता है।

## Aspose.Tasks के साथ प्रोजेक्ट को इमेज के रूप में सेव करें
`ImageSaveOptions` कॉन्फ़िगर करता है कि एक प्रोजेक्ट को इमेज फ़ाइल में कैसे रेंडर किया जाए.  
`ImageSaveOptions` क्लास आपको शेड्यूल स्नैपशॉट को PNG, JPEG, या BMP के रूप में एक्सपोर्ट करने देती है. जब आप `setReduceFooterGap(true)` भी सक्षम करते हैं, तो जेनरेटेड इमेज कॉम्पैक्ट PDF लेआउट को प्रतिबिंबित करती है, जिससे आप प्रेज़ेंटेशन या डैशबोर्ड के लिए एक साफ़ विज़ुअल प्राप्त करते हैं।

## Java प्रोजेक्ट को PDF में निर्यात
निम्नलिखित सेक्शन एक पूर्ण **java project export** वर्कफ़्लो को चरण‑दर‑चरण दर्शाते हैं, MPP फ़ाइल को लोड करने से लेकर इसे तीन विभिन्न फ़ॉर्मेट में सेव करने तक।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. Java Development Kit (JDK) – संस्करण 8 या बाद का।  
2. Aspose.Tasks for Java Library – इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## पैकेज इम्पोर्ट करें
कोडिंग भाग में जाने से पहले, चलिए आवश्यक पैकेज इम्पोर्ट करते हैं:

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

## चरण 1: अपने डेटा डायरेक्टरी का पाथ प्रदान करें
```java
String dataDir = "Your Data Directory";
```  
सुनिश्चित करें कि `"Your Data Directory"` को अपने वास्तविक डेटा डायरेक्टरी के पाथ से बदलें जहाँ आपका Microsoft Project फ़ाइल (`HomeMovePlan.mpp` इस उदाहरण में) स्थित है।

## चरण 2: MPP फ़ाइल पढ़ें
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
यह कोड लाइन `HomeMovePlan.mpp` नामक Microsoft Project फ़ाइल को पढ़ती है।

## चरण 3: ImageSaveOptions सेट करें (प्रोजेक्ट को इमेज के रूप में सेव करें)
`ImageSaveOptions` कॉन्फ़िगर करता है कि एक प्रोजेक्ट को इमेज फ़ाइल में कैसे रेंडर किया जाए.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
इमेज सेविंग विकल्प कॉन्फ़िगर करें, `ReduceFooterGap` को `true` सेट करके टास्क सूची और फुटर के बीच का गैप कम करें।

## चरण 4: इमेज के रूप में सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को इमेज के रूप में सेव करें।

## चरण 5: PdfSaveOptions सेट करें (प्रोजेक्ट को PDF में निर्यात करें)
`PdfSaveOptions` PDF फ़ॉर्मेट में प्रोजेक्ट को एक्सपोर्ट करने के लिए सेटिंग्स निर्दिष्ट करता है.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
PDF सेविंग विकल्प निर्धारित करें, सुनिश्चित करें कि `ReduceFooterGap` को `true` सेट किया गया है।

## चरण 6: PDF के रूप में सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को PDF के रूप में सेव करें।

## चरण 7: HtmlSaveOptions सेट करें
`HtmlSaveOptions` प्रोजेक्ट को HTML में कनवर्ट करने को नियंत्रित करता है, जिसमें स्टाइलिंग और लेआउट विकल्प शामिल हैं.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
HTML सेविंग विकल्प निर्दिष्ट करें, `ReduceFooterGap` को `true` सेट करें।

## चरण 8: HTML के रूप में सेव करें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को HTML फ़ाइल के रूप में सेव करें।

## सामान्य उपयोग केस और टिप्स
- **Stakeholder रिपोर्टिंग:** PDF को कम किए गए फुटर गैप के साथ निर्यात करें ताकि रिपोर्ट संक्षिप्त और प्रिंटर‑फ्रेंडली रहे।  
- **Dashboard स्नैपशॉट्स:** जब आपको Power BI या Confluence के लिए तेज़ विज़ुअल चाहिए तो इमेज एक्सपोर्ट का उपयोग करें।  
- **Web प्रकाशन:** HTML एक्सपोर्ट इंटरैक्टिविटी को बनाए रखता है और सीधे इंट्रानेट पोर्टल्स में एम्बेड किया जा सकता है।  
- **Pro tip:** बहुत बड़े प्रोजेक्ट्स के लिए, `ImageSaveOptions` में `Resolution` को 300 dpi तक बढ़ाएँ ताकि स्पष्टता बनी रहे और फिर भी कम किए गए गैप का लाभ मिले।

## अक्सर पूछे जाने वाले प्रश्न (अतिरिक्त)

**Q: फुटर गैप को कम करने से पेजिनेशन पर क्या प्रभाव पड़ता है?**  
A: यह प्रत्येक पेज के नीचे की खाली जगह को कम करता है, जिससे एक पेज पर अधिक टास्क फिट हो सकते हैं और कुल पेज संख्या घटती है।

**Q: क्या मैं फुटर गैप को कम करने की सेटिंग को केवल एक सिंगल पेज पर लागू कर सकता हूँ?**  
A: हाँ, `ImageSaveOptions` में `setRenderToSinglePage(true)` सेट करके आप पेजिनेशन को नियंत्रित कर सकते हैं जबकि गैप को भी कम कर सकते हैं।

**Q: क्या `setReduceFooterGap` विकल्प अन्य आउटपुट फ़ॉर्मेट्स के लिए उपलब्ध है?**  
A: वर्तमान में यह PNG, PDF, और HTML एक्सपोर्ट के लिए सपोर्टेड है। अन्य फ़ॉर्मेट्स के लिए आपको लेआउट को मैन्युअली एडजस्ट करना पड़ सकता है।

**Q: यदि मेरे प्रोजेक्ट में कस्टम फ़ील्ड्स हैं तो क्या वे संरक्षित रहते हैं?**  
A: सभी कस्टम फ़ील्ड्स एक्सपोर्ट के दौरान बरकरार रहते हैं; लेआउट समायोजन केवल स्पेसिंग को प्रभावित करता है, डेटा को नहीं।

**Q: क्या लाइब्रेरी बड़े प्रोजेक्ट्स को प्रभावी ढंग से संभालती है?**  
A: Aspose.Tasks डेटा को स्ट्रीम करता है और कई सौ पेजों वाले MPP फ़ाइलों को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है; हालांकि, हाई‑रिज़ॉल्यूशन इमेजेज एक्सपोर्ट करते समय पर्याप्त हीप स्पेस आवंटित करें।

---

**अंतिम अपडेट:** 2026-05-20  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for Java  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [प्रोजेक्ट को इमेज के रूप में सेव करें – 24bppRgb फ़ॉर्मेट Aspose.Tasks के साथ](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [प्रोजेक्ट को टेम्प्लेट, CSV, और टेक्स्ट के रूप में सेव करें Aspose.Tasks for Java के साथ](/tasks/java/project-file-operations/save-csv-text-template/)
- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सेव करें](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}