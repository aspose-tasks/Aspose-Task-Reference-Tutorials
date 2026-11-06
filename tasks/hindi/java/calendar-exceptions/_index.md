---
date: 2026-11-06
description: बिना मेहनत के custom calendar exceptions बनाएं, MS Project calendar को
  integrate करें, और Aspose.Tasks के साथ Java प्रोजेक्ट्स में calendar exceptions
  को manage, define, handle और retrieve करें। प्रभावी project management के लिए project
  workflows को streamline करें।
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Calendar Exceptions
og_description: Aspose.Tasks का उपयोग करके Java में calendar exceptions बनाना सीखें।
  project calendars को manage करें, nonworking days सेट करें, और MS Project calendars
  को efficiently modify करें।
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java के साथ calendar exceptions बनाएं
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java के साथ calendar exceptions कैसे बनाएं
url: /hi/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ कैलेंडर अपवाद कैसे बनाएं

## परिचय

`Aspose.Tasks` एक Java लाइब्रेरी है जो Microsoft Project फ़ाइलों की प्रोग्रामेटिक निर्माण, हेरफेर और रूपांतरण को सक्षम बनाती है। इस ट्यूटोरियल में आप सीखेंगे कि **कैलेंडर अपवाद** कैसे बनाएं—कस्टम गैर‑कार्यकाल अवधि जो प्रोजेक्ट के डिफ़ॉल्ट कैलेंडर को ओवरराइड करती हैं। कार्य और गैर‑कार्य दिवसों पर सटीक नियंत्रण सटीक शेड्यूल पूर्वानुमान, संसाधन आवंटन, और क्षेत्रीय छुट्टियों के अनुपालन के लिए आवश्यक है। इस गाइड के अंत तक आप यह भी जानेंगे कि **MS Project कैलेंडर** को अपने Java एप्लिकेशन में कैसे एकीकृत करें और उसके अपवादों को प्राप्त या संशोधित करें।

## त्वरित उत्तर
- **मैं क्या हासिल कर सकता हूँ?** Java प्रोजेक्ट्स में कस्टम कैलेंडर अपवाद बनाएं, संशोधित करें और प्राप्त करें।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (नवीनतम स्थिर रिलीज़)।  
- **क्या मुझे लाइसेंस चाहिए?** हाँ, उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं MS Project फ़ाइलों के साथ काम कर सकता हूँ?** बिल्कुल – आप MS Project कैलेंडर डेटा को आयात, संपादित और निर्यात कर सकते हैं।  
- **क्या कोई विशेष सेटअप आवश्यक है?** केवल Aspose.Tasks JAR को अपने classpath में जोड़ें और संबंधित क्लासेस इम्पोर्ट करें।

## Aspose.Tasks for Java में कस्टम कैलेंडर अपवाद कैसे बनाएं?

Aspose.Tasks for Java में कस्टम कैलेंडर अपवाद बनाने के लिए, लक्ष्य Project को लोड करें, उसका Calendar प्राप्त करें, अपवाद की प्रारंभ और समाप्ति तिथियों को इच्छित कार्य समय के साथ परिभाषित करें, वैकल्पिक रूप से पुनरावृत्ति पैटर्न सेट करें, और फिर प्रोजेक्ट को सहेजें। यह क्रम अपवाद को तुरंत जोड़ता है और इसे .mpp फ़ाइल में स्थायी बनाता है।

`Project` क्लास Aspose.Tasks का मुख्य ऑब्जेक्ट है जो पूरी Microsoft Project फ़ाइल को मॉडल करता है। `Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करती है और इसकी सामग्री तक पहुँच प्रदान करती है। `Calendar` ऑब्जेक्ट प्रोजेक्ट के कार्य और गैर‑कार्य समय को परिभाषित करता है। `Calendar` क्लास सभी कार्य‑समय नियमों, जिसमें अपवाद भी शामिल हैं, का कंटेनर है। `addException()` मेथड कैलेंडर में एक नया कैलेंडर अपवाद जोड़ता है। `addException()` एक सिंगल‑कॉल API है जो निर्दिष्ट तिथि सीमा के लिए गैर‑कार्य अवधि को रजिस्टर करता है।

लक्ष्य प्रोजेक्ट को `Project project = new Project("example.mpp")` के साथ लोड करें, उसका `Calendar` ऑब्जेक्ट प्राप्त करें, और इच्छित तिथि सीमा और कार्य समय सेटिंग्स के साथ `addException()` को कॉल करें। यह दो‑स्टेप पैटर्न एक नया अपवाद तुरंत बनाता है और प्रोजेक्ट को सहेजते समय इसे स्थायी बनाता है। आवर्ती छुट्टियों के लिए, सहेजने से पहले अपवाद पर `RecurrencePattern` को कॉन्फ़िगर करें।

इस तरह कैलेंडर अपवाद बनाकर आप **गैर‑कार्य दिवस** सटीक रूप से सेट कर सकते हैं, चाहे वे एकबारगी बंदी हों या वार्षिक छुट्टियां। अपवाद जोड़ने के बाद, आप `project.save("updated.mpp")` को कॉल करके बदलावों को डिस्क पर लिख सकते हैं।

### चरणों का अवलोकन
1. प्रोजेक्ट फ़ाइल लोड करें।  
2. `Calendar` इंस्टेंस प्राप्त करें या बनाएं।  
3. अपवाद की तिथि सीमा और कार्य समय परिभाषित करें।  
4. (वैकल्पिक) वार्षिक छुट्टियों के लिए पुनरावृत्ति कॉन्फ़िगर करें।  
5. प्रोजेक्ट सहेजें।

## Aspose.Tasks में कैलेंडर अपवाद प्रबंधित करें
[Aspose.Tasks for Java में कैलेंडर अपवाद जोड़ने और हटाने के बारे में प्रभावी तरीके सीखें](./add-remove/). प्रोजेक्ट प्रबंधन में लचीलापन महत्वपूर्ण है। Aspose.Tasks आपको आसानी से कैलेंडर अपवाद प्रबंधित करने की शक्ति देता है, जिससे प्रोजेक्ट टाइमलाइन में गतिशील समायोजन संभव होते हैं। यह ट्यूटोरियल चरण‑दर‑चरण मार्गदर्शिका प्रदान करता है, जिससे आप प्रक्रिया को प्रभावी रूप से समझ सकें। जानें कैसे आप अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को आसानी से सुधार सकते हैं।

## Aspose.Tasks के साथ कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करें
[Aspose.Tasks का उपयोग करके Java प्रोजेक्ट्स में कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करने की कला में निपुण बनें](./define-weekdays/). सटीक प्रोजेक्ट शेड्यूलिंग के लिए बारीकी से ध्यान देना आवश्यक है। Aspose.Tasks के साथ, आप कैलेंडर अपवादों के लिए सप्ताह के दिन सटीक रूप से निर्धारित कर सकते हैं, जिससे आपके प्रोजेक्ट विशिष्ट टाइमलाइन के साथ सहजता से संरेखित होते हैं। यह ट्यूटोरियल आपको शेड्यूलिंग को अनुकूलित करने का ज्ञान प्रदान करता है, जिससे आप प्रोजेक्ट टाइमलाइन पर नियंत्रण पा सकते हैं।

## Aspose.Tasks का उपयोग करके कैलेंडर अपवादों में घटनाओं को संभालें
[Aspose.Tasks for Java के साथ Java प्रोजेक्ट्स में कैलेंडर अपवादों को प्रभावी ढंग से संभालें](./handle-occurrences/). प्रोजेक्ट प्रबंधन एक गतिशील प्रक्रिया है, जिसमें अक्सर अप्रत्याशित घटनाओं को ध्यान में रखते हुए समायोजन की आवश्यकता होती है। Aspose.Tasks आपको कैलेंडर अपवादों को प्रभावी रूप से संभालने की शक्ति देता है, जिससे प्रोजेक्ट प्रबंधन एक सुव्यवस्थित दृष्टिकोण प्राप्त करता है। इस विस्तृत ट्यूटोरियल के माध्यम से आप प्रोजेक्ट अनिश्चितताओं को आसानी से प्रबंधित करने की कला सीखेंगे।

## Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें
[Aspose.Tasks for Java का उपयोग करके MS Project से कैलेंडर अपवाद प्राप्त करने के बारे में जानें](./retrieve/). Aspose.Tasks के साथ कैलेंडर अपवादों को अपने प्रोजेक्ट प्रबंधन प्रक्रिया में सहजता से एकीकृत करें। यह ट्यूटोरियल आपको कैलेंडर अपवाद प्राप्त करने की चरण‑दर‑चरण प्रक्रिया में मार्गदर्शन करता है, जिससे आपके प्रोजेक्ट्स में सुगम और प्रभावी एकीकरण सुनिश्चित होता है। Aspose.Tasks की शक्ति को अनलॉक करके अपने प्रोजेक्ट प्रबंधन क्षमताओं को बढ़ाएँ।

## Aspose.Tasks के साथ MS Project कैलेंडर को कैसे एकीकृत करें?
Aspose.Tasks के साथ MS Project कैलेंडर को एकीकृत करने में स्रोत .mpp फ़ाइल को Project क्लास का उपयोग करके लोड करना, उसके डिफ़ॉल्ट या कस्टम Calendar ऑब्जेक्ट्स तक पहुँच प्राप्त करना, आवश्यकतानुसार अपवादों को संशोधित या मर्ज करना, और फिर अपडेटेड प्रोजेक्ट को सहेजना शामिल है। इससे आप मैन्युअल UI इंटरैक्शन के बिना प्रोग्रामेटिक रूप से MS Project कैलेंडर के साथ काम कर सकते हैं।

`Project` क्लास Aspose.Tasks का मुख्य ऑब्जेक्ट है जो पूरी Microsoft Project फ़ाइल को मॉडल करता है। `new Project("source.mpp")` का उपयोग करके मौजूदा MS Project फ़ाइल आयात करें; लाइब्रेरी स्वचालित रूप से उसका डिफ़ॉल्ट कैलेंडर और किसी भी कस्टम अपवाद को लोड करती है। आप फिर उन अपवादों को पढ़, संशोधित या मर्ज कर सकते हैं, और प्रोजेक्ट को डिस्क पर वापस सहेजने से पहले। यह तरीका आपको **MS Project कैलेंडर** डेटा को प्रोग्रामेटिक रूप से संशोधित करने की अनुमति देता है, बिना MS Project UI में मैन्युअल संपादन के।

## सामान्य उपयोग केस
- **छुट्टी शेड्यूलिंग** – कई प्रोजेक्ट्स में राष्ट्रीय छुट्टियों को गैर‑कार्य दिवस के रूप में परिभाषित करें।  
- **शिफ्ट कार्य** – गैर‑मानक शेड्यूल पर काम करने वाली टीमों के लिए कस्टम कार्य सप्ताह सेट करें।  
- **प्रोजेक्ट फेज गेटिंग** – उन अवधियों को ब्लॉक करें जहाँ कोई कार्य निर्धारित नहीं होना चाहिए, जैसे मेंटेनेंस विंडो।  
- **लेगेसी माइग्रेशन** – पुराने MS Project फ़ाइलों से कैलेंडर आयात करें और उन्हें प्रोग्रामेटिक रूप से समायोजित करें।

## टिप्स और सर्वोत्तम प्रथाएँ
- **प्रो टिप:** नए अपवाद जोड़ने से पहले हमेशा मौजूदा कैलेंडर प्राप्त करें ताकि डुप्लिकेट से बचा जा सके।  
- **चेतावनी:** ऐसे कैलेंडर को बदलना जो पहले से टास्क्स को असाइन किया गया है, टास्क की तिथियों को बदल सकता है; संशोधनों के बाद शेड्यूल को पुनः‑गणना करें।  
- **प्रदर्शन:** फ़ाइल I/O ओवरहेड को कम करने के लिए एक ही ट्रांज़ैक्शन में कई अपवाद अपडेट को बैच करें। Aspose.Tasks 1 GB तक की फ़ाइलों को प्रोसेस करता है जबकि मेमोरी उपयोग 200 MB से कम रखता है, और सामान्य सर्वर हार्डवेयर पर प्रति सेकंड 30+ कैलेंडर‑संबंधित API कॉल संभाल सकता है।

## कैलेंडर अपवाद ट्यूटोरियल
### [Aspose.Tasks में कैलेंडर अपवाद प्रबंधित करें](./add-remove/)
Aspose.Tasks for Java में कैलेंडर अपवाद जोड़ने और हटाने के प्रभावी तरीकों को सीखें। प्रोजेक्ट प्रबंधन वर्कफ़्लो को आसानी से सुधारें।
### [Aspose.Tasks के साथ कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करें](./define-weekdays/)
Aspose.Tasks का उपयोग करके Java प्रोजेक्ट्स में कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करने के बारे में सीखें, जिससे सटीक प्रोजेक्ट शेड्यूलिंग हो सके।
### [Aspose.Tasks का उपयोग करके कैलेंडर अपवादों में घटनाओं को संभालें](./handle-occurrences/)
Aspose.Tasks for Java के साथ Java प्रोजेक्ट्स में कैलेंडर अपवादों को प्रभावी रूप से संभालना सीखें। अब अपने प्रोजेक्ट प्रबंधन प्रक्रिया को सुव्यवस्थित करें।
### [Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें](./retrieve/)
Aspose.Tasks for Java का उपयोग करके MS Project से कैलेंडर अपवाद प्राप्त करने के बारे में सीखें। सहज एकीकरण के लिए चरण‑दर‑चरण ट्यूटोरियल।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं प्रोजेक्ट प्रकाशित होने के बाद कैलेंडर अपवादों को संशोधित कर सकता हूँ?  
**उत्तर:** हाँ। कैलेंडर को अपडेट करने के लिए add‑remove और define‑weekdays API का उपयोग करें, फिर प्रोजेक्ट फ़ाइल को पुनः‑सहेजें।

**प्रश्न:** क्या Aspose.Tasks आवर्ती अपवादों (जैसे, हर महीने का पहला सोमवार) का समर्थन करता है?  
**उत्तर:** बिल्कुल। “handle occurrences” ट्यूटोरियल में आवर्ती पैटर्न सेट करने की विधि बताई गई है।

**प्रश्न:** मैं कैसे सुनिश्चित करूँ कि मेरा कस्टम कैलेंडर प्रोजेक्ट के सभी टास्क्स द्वारा उपयोग किया जाए?  
**उत्तर:** कैलेंडर को प्रोजेक्ट के डिफ़ॉल्ट कैलेंडर में असाइन करें या प्रत्येक टास्क की `Calendar` प्रॉपर्टी पर स्पष्ट रूप से सेट करें।

**प्रश्न:** क्या कई MS Project फ़ाइलों से कैलेंडर को मर्ज करना संभव है?  
**उत्तर:** हाँ। प्रत्येक कैलेंडर को प्राप्त करें, उनके अपवादों को प्रोग्रामेटिक रूप से मिलाएँ, और फिर मर्ज किए गए कैलेंडर को लक्ष्य प्रोजेक्ट में असाइन करें।

**प्रश्न:** इन सुविधाओं के लिए Aspose.Tasks का कौन सा संस्करण आवश्यक है?  
**उत्तर:** सभी सुविधाएँ Aspose.Tasks for Java के वर्तमान स्थिर रिलीज़ (2025.x) में उपलब्ध हैं।

## संबंधित ट्यूटोरियल
- [प्रोजेक्ट कैलेंडर बनाएं Aspose – कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करें](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – asp tasks java ट्यूटोरियल](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose for Java में कैलेंडर अपवाद बनाएं](/tasks/java/calendar-exceptions/add-remove/)

---

**अंतिम अपडेट:** 2026-11-06  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}