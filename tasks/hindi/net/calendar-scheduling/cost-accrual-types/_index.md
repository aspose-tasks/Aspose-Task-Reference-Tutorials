---
date: 2026-07-05
description: Aspose.Tasks for .NET का उपयोग करके प्रोजेक्ट बजट को ट्रैक करना और प्रोजेक्ट
  लागतों का प्रबंधन करना सीखें। सटीक लागत ट्रैकिंग के लिए cost accrual types को परिभाषित
  करें।
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks में Cost Accrual Types
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में Cost Accrual Types के साथ प्रोजेक्ट बजट ट्रैक करें
url: /hi/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में लागत संचित प्रकारों के साथ परियोजना बजट ट्रैक करें

## परिचय

सटीक रूप से **परियोजना बजट ट्रैक** करना सफल परियोजना डिलीवरी की रीढ़ है। जब लागत जानकारी सही समय पर कैप्चर की जाती है, तो आप ओवररन की भविष्यवाणी कर सकते हैं, संसाधनों को समायोजित कर सकते हैं, और हितधारकों को सूचित रख सकते हैं। Aspose.Tasks for .NET डेवलपर्स को लागत संचित पर सूक्ष्म नियंत्रण देता है, जिससे आप तय कर सकते हैं *कब* लागत दर्ज की जाए—काम की शुरुआत में, निरंतर, या केवल काम समाप्त होने पर। यह ट्यूटोरियल आपको अवधारणाओं के माध्यम से ले जाता है, संचित प्रकार सेट करने का तरीका दिखाता है, और विश्वसनीय बजट ट्रैकिंग के लिए सर्वोत्तम प्रथाओं का प्रदर्शन करता है।

## त्वरित उत्तर
- **लागत संचित प्रकारों का मुख्य उद्देश्य क्या है?** वे एक कार्य के जीवनचक्र में वह बिंदु निर्धारित करते हैं जब लागत को मान्यता दी जाती है, जिससे सटीक बजट ट्रैकिंग संभव होती है।  
- **कौन सा enum मान लागत को तब तक विलंबित करता है जब तक कार्य समाप्त नहीं हो जाता?** `CostAccrualType.End`.  
- **क्या कोड चलाने के लिए मुझे लाइसेंस चाहिए?** हाँ, उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं कई संसाधनों के लिए एक साथ संचित प्रकार बदल सकता हूँ?** हाँ—`Resources` संग्रह के माध्यम से लूप करके वांछित प्रकार असाइन करें।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## लागत संचित प्रकार क्या है?

एक **लागत संचित प्रकार** Aspose.Tasks को बताता है कि कब किसी संसाधन की लागत को परियोजना बजट में लागू किया जाए। यह `CostAccrualType` enumeration द्वारा दर्शाया जाता है और इसे प्रति‑संसाधन या प्रति‑कार्य सेट किया जा सकता है। सही प्रकार चुनने से लागत डेटा आपके संगठन की बिलिंग नीतियों के साथ संरेखित रहता है, चाहे आपको लागत कार्य की शुरुआत में, अवधि के अनुसार प्रोरेटेड, या केवल पूर्णता के बाद रिकॉर्ड करनी हो।

## लागत संचित प्रकारों का उपयोग करके परियोजना बजट क्यों ट्रैक करें?

Aspose.Tasks **four** संचित विकल्पों—`Start`, `Prorated`, `Duration`, और `End`—को समर्थन देता है, जो सामान्य परियोजना लेखा परिदृश्यों की पूरी श्रृंखला को कवर करता है। उपयुक्त विकल्प चुनने से आप लागत मान्यता को अनुबंधीय बिलिंग चक्रों के साथ संरेखित कर सकते हैं, वित्तीय रिपोर्टों में विचलन को कम कर सकते हैं, और ERP सिस्टम के साथ सहजता से एकीकृत होने वाले लागत विवरण उत्पन्न कर सकते हैं, जबकि बड़े प्रोजेक्ट्स के लिए मेमोरी उपयोग कम रहता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

### 1. Aspose.Tasks for .NET स्थापित करें
शुरू करने के लिए, आपको अपने विकास वातावरण में Aspose.Tasks for .NET स्थापित होना चाहिए। आप लाइब्रेरी को [download page](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं और प्रदान किए गए स्थापना निर्देशों का पालन कर सकते हैं।

### 2. .NET Framework की परिचितता
ट्यूटोरियल में उदाहरणों के साथ आगे बढ़ने के लिए .NET फ्रेमवर्क और C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान आवश्यक है।

## संसाधन के लिए लागत संचित प्रकार कैसे सेट करें?

प्रोजेक्ट लोड करें, लक्ष्य संसाधन को खोजें, और वांछित `CostAccrualType` असाइन करें। नीचे दिया गया दो‑लाइन पैटर्न मानक तरीका है: एक `Project` इंस्टेंस बनाएं, उसके ID द्वारा संसाधन प्राप्त करें, फिर `CostAccrualType` सेट करें। यह संक्षिप्त क्रम सुनिश्चित करता है कि आप **परियोजना बजट ट्रैक** सटीक रूप से उस क्षण से करें जब संसाधन जोड़ा जाता है।

### चरण 1: नेमस्पेस आयात करें
आइए आवश्यक नेमस्पेस आयात करके शुरू करते हैं ताकि हमारे .NET प्रोजेक्ट में Aspose.Tasks कार्यक्षमता तक पहुंच सकें:

```csharp

```

अब नेमस्पेस तैयार हैं, हम प्रोजेक्ट फ़ाइल लोड करने की ओर बढ़ सकते हैं।

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
`Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है और इसके कार्यों, संसाधनों और अन्य डेटा तक पहुंच प्रदान करता है।

```csharp
var project = new Project("Project2.mpp");
```

पहले, हमें प्रोजेक्ट फ़ाइल को अपने एप्लिकेशन में लोड करना होगा। हम एक नया `Project` ऑब्जेक्ट बनाते हैं और उसे अपनी प्रोजेक्ट फ़ाइल के पाथ से इनिशियलाइज़ करते हैं।

### चरण 3: संसाधन तक पहुँचें
`Resources` संग्रह प्रोजेक्ट में परिभाषित सभी संसाधनों को रखता है। `GetById` मेथड एक संसाधन को उसके अद्वितीय पहचानकर्ता द्वारा प्राप्त करता है।

```csharp
var resource = project.Resources.GetById(1);
```

अब हम उस संसाधन तक पहुँचते हैं जिस पर हम लागत संचित प्रकार लागू करना चाहते हैं। हम `Resources` संग्रह के `GetById` मेथड का उपयोग करके संसाधन ID को आर्ग्यूमेंट के रूप में पास करते हैं। यह **ID द्वारा संसाधन तक पहुँचें** को दर्शाता है, जो लागत अपडेट को स्वचालित करने की सामान्य आवश्यकता है।

### चरण 4: लागत संचित प्रकार सेट करें
`Set` मेथड एक संसाधन फ़ील्ड को मान असाइन करता है।

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

यहाँ, हम संसाधन के लिए लागत संचित प्रकार सेट करते हैं। इस उदाहरण में, हम इसे `CostAccrualType.End` पर सेट कर रहे हैं, जिसका अर्थ है कि लागत तब तक संचित नहीं होगी जब तक शेष कार्य शून्य न हो जाए। `End` चुनना आदर्श है जब आप **परियोजना बजट ट्रैक** केवल कार्य पूरी तरह समाप्त होने के बाद करना चाहते हैं।

### चरण 5: प्रोजेक्ट के साथ काम जारी रखें
लागत संचित प्रकार सेट करने के बाद, आप आवश्यकतानुसार प्रोजेक्ट के साथ काम जारी रख सकते हैं, अतिरिक्त संचालन या गणनाएँ कर सकते हैं जैसे लागत रिपोर्ट बनाना, असाइनमेंट अपडेट करना, या फ़ाइल निर्यात करना।

## सामान्य गलतियों और प्रो टिप्स
- **Pro tip:** संचित प्रकारों में बदलाव करने के बाद हमेशा `project.Save` कॉल करें ताकि परिवर्तन स्थायी हो जाएँ।  
- **Pitfall:** `CostAccrualType.Start` को ऐसे संसाधन पर सेट करना जो कभी काम शुरू नहीं करता, बजट रिपोर्ट को बढ़ा देगा—पहले कार्य शेड्यूल की जाँच करें।  
- **Pro tip:** जब आपको कई संसाधनों को बैच‑अपडेट करना हो, तो `project.Resources.ToList()` का उपयोग करें; यह दोहराए गए संग्रह लुकअप को रोकता है और बड़े प्रोजेक्ट्स में प्रदर्शन सुधारता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं कई संसाधनों के लिए एक साथ लागत संचित प्रकार बदल सकता हूँ?**  
A: हाँ, `project.Resources` के माध्यम से इटररेट करके प्रत्येक संसाधन को `foreach` लूप में वांछित `CostAccrualType` असाइन करें।

**Q: `End` के अलावा अन्य उपलब्ध लागत संचित प्रकार कौन‑से हैं?**  
A: Aspose.Tasks `Start`, `Prorated`, और `Duration` प्रदान करता है—प्रत्येक अलग बिलिंग रणनीति के साथ संरेखित होता है।

**Q: किसी विशिष्ट संसाधन के वर्तमान लागत संचित प्रकार का निर्धारण कैसे करूँ?**  
A: `resource.Get(TskResource.CostAccrualType)` के माध्यम से मान प्राप्त करें; यह वर्तमान सेटिंग को दर्शाने वाला enum लौटाता है।

**Q: क्या एक ही प्रोजेक्ट में विभिन्न कार्यों पर अलग‑अलग लागत संचित प्रकार लागू करना संभव है?**  
A: बिल्कुल। कार्य और संसाधन दोनों `CostAccrualType` प्रॉपर्टी उजागर करते हैं, जिससे प्रत्येक इकाई के लिए स्वतंत्र कॉन्फ़िगरेशन संभव है।

**Q: क्या Aspose.Tasks कस्टम लागत संचित प्रकारों का समर्थन करता है?**  
A: नहीं, लाइब्रेरी वर्तमान में केवल चार बिल्ट‑इन प्रकारों का समर्थन करती है; यदि आवश्यक हो तो कस्टम लॉजिक को बाहरी रूप से लागू करना होगा।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित संस्करण:** Aspose.Tasks 24.8 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks कैलेंडर और शेड्यूलिंग](/tasks/net/calendar-scheduling/)
- [Aspose.Tasks for .NET के साथ MS Project रेट्स को संभालना](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Aspose.Tasks के साथ MS Project संसाधनों का सहज प्रबंधन](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}