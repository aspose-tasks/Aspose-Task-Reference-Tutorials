---
title: .NET के लिए Aspose.Tasks में कार्यदिवसों में महारत हासिल करना
linktitle: Aspose.Tasks में सप्ताह के दिनों को परिभाषित करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks .NET में कार्यदिवसों को परिभाषित करने की शक्ति का अन्वेषण करें। प्रोजेक्ट कैलेंडर को कुशलतापूर्वक प्रबंधित करने, कार्य समय को अनुकूलित करने आदि के लिए हमारे विस्तृत ट्यूटोरियल का पालन करें।
type: docs
weight: 10
url: /hi/net/time-recurrence-configuration/defining-weekdays/
---
## परिचय
यदि आप .NET के लिए Aspose.Tasks का उपयोग करके परियोजना प्रबंधन की दुनिया में प्रवेश कर रहे हैं, तो कार्यदिवसों को समझना और उनमें हेरफेर करना एक महत्वपूर्ण पहलू है। अपने प्रोजेक्ट कैलेंडर के भीतर साप्ताहिक दिनों को कुशलतापूर्वक प्रबंधित और अनुकूलित करने से प्रोजेक्ट की समयसीमा पर महत्वपूर्ण प्रभाव पड़ सकता है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके कार्यदिवसों को परिभाषित करने की प्रक्रिया में आपका मार्गदर्शन करेंगे, बेहतर स्पष्टता के लिए चरण-दर-चरण निर्देश और उदाहरण प्रदान करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
-  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित। यदि नहीं, तो इसे यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/net/).
## नामस्थान आयात करें
अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. कार्यदिवस समानता की जाँच करें
```csharp
// आपकी दस्तावेज़ निर्देशिका
String DataDir = "Your Document Directory";
// प्रोजेक्ट फ़ाइल लोड करें
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// साप्ताहिक दिनों तक पहुंचें
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// विभिन्न गुणों के आधार पर समानता की जाँच करें
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. एक सप्ताह के दिन क्लोन करें
```csharp
// प्रोजेक्ट फ़ाइल लोड करें
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// कार्यदिवस की एक गहरी प्रतिलिपि बनाएँ
var weekDay2 = weekDay1.Clone();
// दोनों कार्यदिवसों के आउटपुट गुण
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. कार्यदिवस का हैश कोड प्राप्त करें
```csharp
// प्रोजेक्ट फ़ाइल लोड करें
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// दोनों कार्यदिवसों के आउटपुट गुण
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. परिभाषित कार्यदिवसों के साथ एक नया कैलेंडर बनाएं
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
// कैलेंडर को परिभाषित करें
var calendar = project.Calendars.Add("Calendar1");
// कार्य दिवस और अपवाद दिवस जोड़ें
// FromDate और ToDate के लिए समान आउटपुट स्टेटमेंट जोड़ें
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// शुक्रवार के लिए कार्य समय निर्धारित करें
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. एक दिन के लिए डिफ़ॉल्ट कार्य समय निर्धारित करें
```csharp
// एक नया प्रोजेक्ट बनाएं
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// सोमवार से शुक्रवार के लिए डिफ़ॉल्ट कार्य समय जोड़ें
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// मंगलवार, बुधवार, गुरुवार और शुक्रवार के लिए दोहराएं
// शनिवार और रविवार के लिए गैर-कार्य दिवस निर्धारित करें
// डेवर्किंग, फ्रॉमडेट, टूडेट और वर्किंगटाइम्स के लिए समान आउटपुट स्टेटमेंट जोड़ें
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks में कार्यदिवसों को परिभाषित करने के आवश्यक पहलुओं को शामिल किया है। प्रभावी परियोजना प्रबंधन के लिए साप्ताहिक दिनों में हेरफेर करना एक महत्वपूर्ण कौशल है। दिए गए उदाहरणों के साथ प्रयोग करें, उन्हें अपने प्रोजेक्ट की आवश्यकताओं के अनुरूप बनाएं और Aspose.Tasks की पूरी क्षमता को अनलॉक करें।
## पूछे जाने वाले प्रश्न
### क्या मैं प्रत्येक दिन के लिए कस्टम कार्य समय परिभाषित कर सकता हूँ?
हां, आप दिए गए उदाहरणों का उपयोग करके विशिष्ट कार्यदिवसों के लिए कस्टम कार्य समय निर्धारित कर सकते हैं।
### क्या कैलेंडर में एकाधिक अपवाद दिन जोड़ना संभव है?
बिल्कुल। अतिरिक्त अपवाद दिनों को शामिल करने के लिए चौथे उदाहरण में कोड को संशोधित करें।
### मैं कैलेंडर से किसी विशिष्ट कार्यदिवस को कैसे हटा सकता हूँ?
आवश्यकतानुसार कार्यदिवसों को हटाने के लिए Aspose.Tasks लाइब्रेरी द्वारा प्रदान की गई उचित विधियों का उपयोग करें।
### क्या प्रोजेक्ट फ़ाइल में लगातार कार्यदिवसों में परिवर्तन किए गए हैं?
हाँ, कार्यदिवसों में कोई भी संशोधन सहेजे जाने पर प्रोजेक्ट फ़ाइल में दिखाई देता है।
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
Aspose.Tasks विभिन्न प्रोग्रामिंग भाषाओं का समर्थन करता है, लेकिन यहां दिए गए उदाहरण विशेष रूप से .NET के लिए हैं।