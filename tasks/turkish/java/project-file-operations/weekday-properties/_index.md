---
date: 2026-03-29
description: Aspose.Tasks for Java'da ay başına gün sayısını nasıl değiştireceğinizi
  ve diğer hafta günü özelliklerini nasıl yöneteceğinizi öğrenin. Hafta başlangıç
  tarihlerini özelleştirin, proje takvimini değiştirin ve projeyi XML olarak kaydedin.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ay Başına Gün Sayısını Aspose.Tasks Hafta Günü Özellikleriyle Değiştir
url: /tr/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Hafta Günü Özellikleriyle Ayda Gün Sayısını Değiştirme

## Giriş
Aspose.Tasks for Java, Microsoft Project yüklü olmadan **ayda gün sayısını değiştirme** ve diğer hafta günü ayarlarını ince ayar yapmanıza olanak tanır. Proje takvimini standart olmayan bir mali aya göre hizalıyor olun ya da sadece haftanın başlangıç gününü ayarlamanız gerekse, bu öğretici en yaygın senaryoları adım adım gösterir—mevcut haftanın başlangıç gününü alma, haftanın başlangıç tarihini özelleştirme, proje takvimini değiştirme ve projeyi XML olarak kaydetme.

## Hızlı Yanıtlar
- **Ayda gün sayısını değiştirebilir miyim?** Evet, `Project` nesnesinde `Prj.DAYS_PER_MONTH` kullanın.  
- **Haftanın başlangıç tarihini nasıl özelleştirebilirim?** `Prj.WEEK_START_DAY` değerini bir `DayType` değeri olarak ayarlayın (ör. `DayType.Monday`).  
- **Projeyi dışa aktarmak için hangi formatı kullanabilirim?** Örnek, dosyayı `SaveFileFormat.Xml` ile XML olarak kaydeder.  
- **Üretim kullanımında lisans gerekli mi?** Değerlendirme dışı dağıtımlar için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Hangi IDE'ler destekleniyor?** IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE'si çalışır.

## Aspose.Tasks'te “ayda gün sayısını değiştirme” nedir?
Ayda gün sayısını değiştirmek, bir `Project` örneğinin `Prj.DAYS_PER_MONTH` özelliğini güncellemek anlamına gelir. Bu özellik, motorun her ay kaç çalışma günü dikkate alması gerektiğini belirler ve bu doğrudan görev zamanlamasını ve maliyet hesaplamalarını etkiler.

## Neden proje takvim özelliklerini değiştirmelisiniz?
Proje takvimini özelleştirmek—örneğin farklı bir haftanın başlangıç gününü ayarlamak veya gün başına dakikaları değiştirmek—şunlara yardımcı olur:

- Takvimleri bölgesel çalışma haftalarıyla hizalamak.  
- Standart dışı çalışma modellerini (ör. 4 günlük haftalar) modellemek.  
- Özel takvimler kullanan sözleşmeler için doğru raporlama sağlamak.

## Önkoşullar
- **Java Development Kit (JDK)** – Oracle'dan en son JDK'yı kurun.  
- **Aspose.Tasks for Java library** – Resmi siteden [buradan](https://releases.aspose.com/tasks/java/) indirin.  
- **IDE of your choice** – IntelliJ IDEA, Eclipse veya NetBeans.

## Paketleri İçe Aktarma
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Adım 1: Proje Dosyasını Yükle
This loads an existing Microsoft Project file (`project.mpp`) from the folder you specify.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Adım 2: Hafta Günü Özelliklerini Görüntüle
Here we retrieve and print the current weekday settings, including the **week start day** and **days per month**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## Adım 3: Hafta Günü Özelliklerini Ayarlama
In this step we **change days per month** to 24, set the week to start on Monday, and adjust the minutes per day/week. This demonstrates how to **modify project calendar** values programmatically.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## Adım 4: Projeyi Kaydet
The modified project is persisted using the **save project as XML** format, which is handy for integration with other tools or for version‑controlled storage.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## Adım 5: Sonucu Görüntüle
A simple confirmation that the operations finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Hafta Başlangıç Tarihini Nasıl Özelleştirirsiniz
If your organization follows a Sunday‑first calendar, replace `DayType.Monday` with `DayType.Sunday`. The same property (`Prj.WEEK_START_DAY`) is used, making the change straightforward.

## Hafta Başlangıç Gününü Nasıl Alırsınız
You can call `project.get(Prj.WEEK_START_DAY)` at any point to **retrieve week start day** information, as shown in Step 2.

## Proje Takvimini Nasıl Değiştirirsiniz
Beyond the week start day, you can also adjust `Prj.MINUTES_PER_DAY` and `Prj.MINUTES_PER_WEEK` to reflect custom working hours or shift patterns.

## Yaygın Sorunlar ve Çözümler
- **Yanlış gün tipi değeri** – `DayType` enum'ını (ör. `DayType.Monday`) kullandığınızdan emin olun.  
- **Dosya yolu hataları** – `dataDir`'in uygun dosya ayırıcıyla (`/` veya `\`) bittiğini doğrulayın.  
- **Lisans ayarlanmamış** – Lisans uyarıları görürseniz, `Project` nesnesini oluşturmadan önce Aspose.Tasks lisansınızı kaydedin.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?**  
A: Evet, Aspose.Tasks for Java, karmaşık proje yapılarını kolaylıkla yönetmek için kapsamlı destek sağlar.

**Q: Aspose.Tasks for Java, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
A: Kesinlikle, Aspose.Tasks for Java, çeşitli Microsoft Project dosyası sürümlerini destekler ve platformlar arasında uyumluluk sağlar.

**Q: Aspose.Tasks for Java'yi mevcut Java uygulamalarıma entegre edebilir miyim?**  
A: Evet, Aspose.Tasks for Java sorunsuz entegrasyon yetenekleri sunar ve Java uygulamalarınızı güçlü proje yönetimi özellikleriyle geliştirebilmenizi sağlar.

**Q: Aspose.Tasks for Java dokümantasyon ve destek sağlıyor mu?**  
A: Evet, Aspose.Tasks for Java için kapsamlı dokümantasyon ve topluluk desteğine [web sitesinden](https://releases.aspose.com/) ulaşabilirsiniz.

**Q: Aspose.Tasks for Java için ücretsiz deneme sürümü mevcut mu?**  
A: Evet, satın almadan önce özelliklerini keşfetmek için Aspose.Tasks for Java'nın ücretsiz deneme sürümünü [web sitesinden](https://reference.aspose.com/tasks/java/) indirebilirsiniz.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}