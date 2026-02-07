---
date: 2026-02-07
description: जाने कि कैसे Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों से
  मुद्रा गुण java पढ़ें और मुद्रा प्रतीक java निकालें। इस चरण‑दर‑चरण गाइड का पालन
  करके प्रोग्रामेटिक रूप से मुद्रा कोड, प्रतीक, अंकों और स्थिति निकालें।
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks प्रोजेक्ट्स के साथ जावा में मुद्रा गुण पढ़ें
url: /hi/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks प्रोजेक्ट्स के साथ Java में मुद्रा गुण पढ़ें

## Introduction
इस ट्यूटोरियल में आप Aspose.Tasks for Java API का उपयोग करके Microsoft Project फ़ाइलों से **read currency properties java** को पढ़ेंगे। Aspose.Tasks आपको .mpp फ़ाइलों के साथ काम करने की सुविधा देता है बिना Microsoft Project इंस्टॉल किए, जिससे यह स्वचालित रिपोर्टिंग, डेटा माइग्रेशन या Java‑आधारित एंटरप्राइज़ एप्लिकेशनों में इंटीग्रेशन के लिए आदर्श बन जाता है। इस गाइड के अंत तक, आप प्रोजेक्ट फ़ाइल से सीधे मुद्रा कोड, प्रतीक, दशमलव अंकों की संख्या और प्रतीक की स्थिति निकाल सकेंगे।

## Quick Answers
- **What does “read currency properties java” mean?** यह Java कोड का उपयोग करके MS Project फ़ाइल से मुद्रा‑संबंधी मेटाडेटा (कोड, प्रतीक, अंकों की संख्या, स्थिति) प्राप्त करने को दर्शाता है।  
- **Do I need a license to try this?** Aspose.Tasks का एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **Which JDK version is required?** Java 8 या उससे ऊपर।  
- **Can I modify the currency settings after reading them?** हाँ, Aspose.Tasks मुद्रा गुणों पर पढ़ने और लिखने दोनों ऑपरेशन की अनुमति देता है।  
- **Is this compatible with all .mpp versions?** API Microsoft Project 2003‑2021 द्वारा निर्मित फ़ाइलों को सपोर्ट करता है।

## What is read currency properties java?
Java में मुद्रा गुण पढ़ना का अर्थ है Microsoft Project फ़ाइल में परिभाषित प्रोजेक्ट‑स्तर की सेटिंग्स तक पहुँच प्राप्त करना, जो यह निर्धारित करती हैं कि मौद्रिक मान कैसे प्रदर्शित होते हैं। इन सेटिंग्स में ISO मुद्रा कोड (जैसे **USD**), प्रतीक (**$**), दशमलव अंकों की संख्या, और राशि से पहले या बाद में प्रतीक का स्थान शामिल है।

## Why read currency properties java with Aspose.Tasks?
- **No Microsoft Project installation needed** – API किसी भी प्लेटफ़ॉर्म पर काम करती है जो Java को सपोर्ट करता है।  
- **Fast, in‑process extraction** – बड़ी संख्या में प्रोजेक्ट फ़ाइलों के बैच प्रोसेसिंग के लिए आदर्श।  
- **Full control** – आप प्राप्त मानों को कस्टम रिपोर्टिंग के साथ जोड़ सकते हैं या ERP सिस्टम में इंटीग्रेट कर सकते हैं।  
- **Cross‑version support** – Project 2003 से लेकर नवीनतम 2021 रिलीज़ तक की .mpp फ़ाइलों के साथ काम करता है।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – Java 8 या उससे नया, `PATH` में कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java JAR** – नवीनतम लाइब्रेरी [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और अपने प्रोजेक्ट की classpath में जोड़ें।  

## Import Packages
प्रोजेक्ट मैनिपुलेशन के लिए आवश्यक Aspose.Tasks नेमस्पेस को इम्पोर्ट करें:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
उस फ़ोल्डर को परिभाषित करें जिसमें वह `.mpp` फ़ाइल है जिसे आप विश्लेषण करना चाहते हैं। पाथ को एक वेरिएबल में रखने से कोड पुन: प्रयोज्य बनता है:

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"` को उस फ़ोल्डर के पूर्ण या सापेक्ष पाथ से बदलें जहाँ `project.mpp` स्थित है।*

## Step 2: Create a Project Reader Instance
Microsoft Project फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करें। यह ऑब्जेक्ट आपको सभी प्रोजेक्ट गुणों, जिसमें मुद्रा सेटिंग्स भी शामिल हैं, तक पहुँच देता है:

```java
Project project = new Project(dataDir + "project.mpp");
```

*यदि आपकी फ़ाइल का नाम अलग है, तो `"project.mpp"` को उसी अनुसार बदलें।*

## Step 3: Display Currency Properties
अब `Prj` एनेमरेशन का उपयोग करके प्रत्येक मुद्रा एट्रिब्यूट प्राप्त करें और परिणाम को कंसोल पर प्रिंट करें। API ऑब्जेक्ट्स को स्ट्रिंग में बदलकर प्रदर्शित किया जा सकता है:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**What you’ll see:**  
- **Currency Code** – `USD`, `EUR`, `JPY` जैसे ISO‑4217 कोड।  
- **Currency Digits** – अधिकांश मुद्राओं के लिए सामान्यतः `2`, जापानी येन के लिए `0`।  
- **Currency Symbol** – रिपोर्ट में दिखाया गया अक्षर (`$`, `€`, `¥`)।  
- **Currency Symbol Position** – राशि से पहले के लिए `0`, बाद में के लिए `1`।

## How to extract currency symbol java?
यदि आपका केवल रुचि प्रतीक में है, तो आप `Prj.CURRENCY_SYMBOL` प्रॉपर्टी पर ध्यान केंद्रित कर सकते हैं। वही `project.get(...)` कॉल प्रतीक लौटाता है, जिसे आप स्टोर, लॉग या आगे की प्रोसेसिंग के लिए किसी अन्य सर्विस को पास कर सकते हैं। यह विशेष रूप से वित्तीय डैशबोर्ड या स्थानीयकृत UI घटकों के लिए **extract currency symbol java** करने में उपयोगी है।

## Step 4: Process Completion
सिग्नल दें कि एक्सट्रैक्शन सफलतापूर्वक समाप्त हो गया। यह सरल संदेश बड़े बैच जॉब के हिस्से के रूप में कोड चलाने पर सहायक होता है:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` पाथ गलत है या फ़ाइल नाम में टाइपो है। | डायरेक्टरी स्ट्रिंग की जाँच करें और सुनिश्चित करें कि निर्दिष्ट स्थान पर `.mpp` फ़ाइल मौजूद है। |
| **NullPointerException on `project.get(...)`** | प्रोजेक्ट फ़ाइल में मुद्रा जानकारी नहीं है (कम संभावना) या प्रॉपर्टी कुंजी गलत है। | पढ़ने से पहले `project.contains(Prj.CURRENCY_CODE)` का उपयोग करके अस्तित्व की जाँच करें। |
| **LicenseException** | उत्पादन वातावरण में वैध Aspose.Tasks लाइसेंस के बिना चलाया गया। | `Project` ऑब्जेक्ट बनाने से पहले `License license = new License(); license.setLicense("Aspose.Tasks.lic");` का उपयोग करके लाइसेंस फ़ाइल लागू करें। |

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?**  
A: Aspose.Tasks Microsoft Project 2003‑2021 द्वारा उत्पन्न .mpp फ़ाइलों को सपोर्ट करता है, जो पुराने और नवीनतम दोनों फॉर्मेट को कवर करता है।

**Q: Can I modify currency properties using Aspose.Tasks?**  
A: हाँ, आप मुद्रा सेटिंग्स को पढ़ और लिख दोनों कर सकते हैं। `project.set(Prj.CURRENCY_CODE, "EUR");` का उपयोग करके सेट करें और फिर प्रोजेक्ट को सेव करें।

**Q: Is Aspose.Tasks suitable for commercial use?**  
A: बिल्कुल। यह एक व्यावसायिक लाइब्रेरी है; आप लाइसेंस [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**Q: Does Aspose.Tasks offer a free trial?**  
A: हाँ, एक पूर्ण कार्यात्मक ट्रायल [here](https://releases.aspose.com/) उपलब्ध है।

**Q: Where can I seek help or support for Aspose.Tasks?**  
A: आधिकारिक Aspose.Tasks फ़ोरम सबसे अच्छा सहायता स्रोत है – इसे [here](https://forum.aspose.com/c/tasks/15) पर देखें।

## Additional FAQ (AI‑Optimized)

**Q: How do I programmatically extract only the currency symbol in Java?**  
A: `project.get(Prj.CURRENCY_SYMBOL)` को कॉल करें और परिणाम को `String` में कास्ट करें। यह प्रोजेक्ट फ़ाइल में उपयोग किया गया सटीक प्रतीक लौटाता है।

**Q: Can I read currency properties from a password‑protected .mpp file?**  
A: हाँ। `Project` कन्स्ट्रक्टर के उस ओवरलोड का उपयोग करें जो पासवर्ड स्वीकार करता है, फिर ऊपर दिखाए अनुसार प्रॉपर्टीज़ पढ़ें।

**Q: What performance can I expect when processing many project files?**  
A: Aspose.Tasks इन‑प्रोसेस चलती है और सामान्य .mpp फ़ाइल को कुछ मिलीसेकंड में पढ़ लेती है। बड़े पैमाने पर ऑपरेशन्स के लिए संभव हो तो समान `Project` इंस्टेंस को पुनः उपयोग करने पर विचार करें।

## Conclusion
आपने अब **read currency properties java** और **extract currency symbol java** को Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइल से पढ़ना सीख लिया है। यह क्षमता आपको मुद्रा मेटाडेटा को कस्टम रिपोर्ट, वित्तीय विश्लेषण या इंटीग्रेशन पाइपलाइन में शामिल करने की अनुमति देती है, बिना Microsoft Project पर निर्भर हुए। प्रॉपर्टीज़ को संशोधित करने या इस डेटा को अन्य प्रोजेक्ट एट्रिब्यूट्स के साथ मिलाकर अधिक समृद्ध समाधान बनाने के लिए प्रयोग करने में संकोच न करें।

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}