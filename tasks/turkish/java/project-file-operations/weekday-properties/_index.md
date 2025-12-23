---
date: 2025-12-23
description: Aspose Tasks Java'yı kullanarak proje takvimini güncelleme, haftanın
  başlangıç gününü ayarlama, ay başına gün sayısını değiştirme ve proje takvimini
  verimli bir şekilde özelleştirme yöntemlerini öğrenin.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Hafta İçi Özelliklerini Yönetme
url: /tr/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Hafta İçi Özelliklerini Yönetme

## Introduction
Aspose.Tasks for Java (aspose tasks java), Java geliştiricilerinin Microsoft Project yüklü olmadan Microsoft Project dosyalarıyla çalışmasını sağlayan sağlam bir API'dir. Bu öğreticide **bir MPP dosyası yüklemeyi**, **hafta başlangıç gününü ayarlamayı**, **ayda gün sayısını değiştirmeyi** ve ayrıca **proje takvimini özelleştirmeyi** öğreneceksiniz—bütün bunlar bir proje takvimini güncellemek için gerekli adımlardır. Sonunda, hafta içi özelliklerini programlı olarak ayarlayabilecek ve değişiklikleri ihtiyacınız olan formatta kaydedebileceksiniz.

## Quick Answers
- **Projeleri yönetmek için birincil sınıf nedir?** `Project` Aspose.Tasks kütüphanesinden.  
- **Hafta başlangıç gününü nasıl değiştiririm?** `project.set(Prj.WEEK_START_DAY, DayType.Monday)` kullanın.  
- **Mevcut bir .mpp dosyasını yükleyebilir miyim?** Evet—`Project` nesnesini dosya yolu ile başlatın.  
- **Projeyi XML olarak kaydeden yöntem hangisidir?** `project.save(path, SaveFileFormat.Xml)`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme sürümü çalışır; üretim için lisans gereklidir.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK)** – en son sürüm yüklü.  
- **Aspose.Tasks for Java kütüphanesi** – [buradan](https://releases.aspose.com/tasks/java/) indirin.  
- **Bir IDE** örneğin IntelliJ IDEA, Eclipse veya NetBeans.  

## Import Packages
Başlamak için gerekli Aspose.Tasks sınıflarını içe aktarın:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Şimdi hafta içi özelliklerini yönetmenin her adımını inceleyelim.

## Step 1: Load an MPP File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Burada **mevcut bir .mpp dosyasını** (`load mpp file`) yüklüyoruz, böylece takvim ayarlarını inceleyip değiştirebiliriz.*

## Step 2: Display Current Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Bu kod mevcut **hafta başlangıç gününü**, **ayda gün sayısını**, **gün başına dakika**, ve **hafta başına dakika** yazdırır—genellikle **proje takvimini özelleştirmeniz** gereken temel öğelerdir.

## Step 3: Set New Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Bu adımda **hafta başlangıç gününü** Pazartesi olarak **ayda gün sayısını** 24'e **değiştiriyoruz** ve günlük ve haftalık dakika sayılarını ayarlıyoruz. Bu ayarlar, standart olmayan bir çalışma takvimine uyacak şekilde **proje takvimini güncellemeniz** gerektiğinde tipiktir.

## Step 4: Save the Updated Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Değiştirilen proje bir XML dosyası olarak kaydedilir, bu da diğer araçlarla paylaşmayı veya içe aktarmayı kolaylaştırır.

## Step 5: Confirm the Operation
```java
System.out.println("Process completed Successfully");
```
Basit bir konsol mesajı, iş akışının hatasız tamamlandığını bildirir.

## Common Issues & Tips
- **Yanlış dosya yolu** – `dataDir`'in bir slash ile bittiğini doğrulayın veya platform bağımsız yollar için `Paths.get(...)` kullanın.  
- **Lisans ayarlanmamış** – Üretim ortamında, `Project` oluşturulmadan önce `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` çağırın.  
- **Beklenmeyen hafta başlangıç günü** – Doğru `DayType` enum değerini kullandığınızdan emin olun (ör. `DayType.Sunday`).  

## Frequently Asked Questions

**S: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?**  
C: Evet, Aspose.Tasks for Java, karmaşık proje yapılarını kolaylıkla yönetmek için kapsamlı destek sağlar.

**S: Aspose.Tasks for Java farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Kesinlikle, Aspose.Tasks for Java çeşitli Microsoft Project dosya sürümlerini destekler ve platformlar arasında uyumluluk sağlar.

**S: Aspose.Tasks for Java'ı mevcut Java uygulamalarıma entegre edebilir miyim?**  
C: Evet, Aspose.Tasks for Java sorunsuz entegrasyon yetenekleri sunar, böylece Java uygulamalarınızı güçlü proje yönetimi özellikleriyle geliştirebilirsiniz.

**S: Aspose.Tasks for Java dokümantasyon ve destek sağlıyor mu?**  
C: Evet, Aspose.Tasks for Java için kapsamlı dokümantasyon ve topluluk desteğine [web sitesinden](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Tasks for Java için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, satın almadan önce özelliklerini keşfetmek için Aspose.Tasks for Java'ın ücretsiz deneme sürümünü [web sitesinden](https://reference.aspose.com/tasks/java/) indirebilirsiniz.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}