---
date: 2026-08-13
description: Aspose.Tasks kullanarak Java'da standart bir MS Project takvimi oluşturmayı
  öğrenin. Bu adım adım kılavuz, standart bir MS Project takvimi oluşturmayı, varsayılan
  olarak eklemeyi ve dosyayı kaydetmeyi gösterir.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks'te Standart Takvim Oluştur
og_description: Aspose.Tasks ile Java'da takvim nasıl oluşturulur. Standart bir MS
  Project takvimi oluşturmayı, varsayılan olarak ayarlamayı ve proje dosyasını dakikalar
  içinde kaydetmeyi öğrenin.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Takvim nasıl oluşturulur – Aspose.Tasks'te standart takvim oluşturma
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Takvim nasıl oluşturulur – Aspose.Tasks'te standart takvim oluşturma
url: /tr/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvim nasıl oluşturulur – Aspose.Tasks'te standart takvim oluşturma

## Giriş
Bu öğreticide, Aspose.Tasks for Java kütüphanesini kullanarak Microsoft Project dosyaları için **takvim nasıl oluşturulur** nesnelerini öğreneceksiniz. Standart bir MS Project takvimi oluşturmayı, onu varsayılan (standart) takvim haline getirmeyi ve proje dosyasını kaydetmeyi adım adım göstereceğiz. Kılavuzun sonunda, takvim oluşturmayı herhangi bir Java tabanlı proje yönetimi çözümüne entegre edebileceksiniz.

## Hızlı cevaplar
- **“standart takvim” ne anlama gelir?** Varsayılan çalışma zamanı tanımıdır ve özel bir takvim atanmamış görevlerde uygulanır.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java – Microsoft Project yüklü olmadan çalışan saf Java API'si.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim dağıtımları için ticari lisans gereklidir.  
- **Hangi dosya formatı üretilir?** XML tabanlı bir Microsoft Project dosyası (`.xml`).  
- **Uygulama ne kadar sürer?** Temel bir takvim kurulumu için yaklaşık 5‑10 dakika.

## Microsoft Project'te standart takvim nedir?
Standart takvim, bir projenin varsayılan çalışma günlerini ve saatlerini tanımlar; genellikle Pazartesi‑Cuma, sabah 8’den akşam 5’e kadar. Standart bir takvim eklediğinizde, özel takvim atanmamış tüm görevler bu çalışma zamanlarını devralır ve proje boyunca tutarlı bir zamanlama sağlar.

## Takvim oluşturmak için neden Aspose.Tasks kullanılmalı?
Aspose.Tasks for Java, **50+ giriş ve çıkış formatını** destekler ve tüm dosyayı belleğe yüklemeden **10.000'e kadar görev** içeren projeleri işleyebilir. Bu saf Java kütüphanesi, sunucularda, CI boru hatlarında veya herhangi bir Java uygulamasında Project dosyası oluşturmayı otomatikleştirmenizi sağlar ve lisanslı bir Microsoft Project kurulumuna ihtiyaç duymaz.

## Önkoşullar
Başlamadan önce, aşağıdakilerin hazır olduğundan emin olun:

### Java Development Kit (JDK) kurulumu
Oracle web sitesinden veya bir OpenJDK dağıtımından en son JDK'yı kurun.

### Aspose.Tasks for Java kütüphanesi
Kütüphaneyi [download page](https://releases.aspose.com/tasks/java/) adresinden indirin. JAR dosyasını projenizin sınıf yoluna ekleyin.

## Paketleri içe aktar
Bu öğretici için yalnızca bir içe aktarma gereklidir:

```java
import com.aspose.tasks.*;
```

## Adım adım kılavuz

### Adım 1: veri dizinini ayarlama
Oluşturulan proje dosyasının nereye kaydedileceğini tanımlayın.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini makinenizdeki mutlak yol ile değiştirin (örnek: `C:/Projects/Output/`).

### Adım 2: bir proje örneği oluşturma
`Project`, Aspose.Tasks'in bellek içinde tek bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir. Bir örnek oluşturmak, takvimler, görevler, kaynaklar ve diğer proje verileri için bir kapsayıcı sağlar.

```java
Project project = new Project();
```

### Adım 3: takvimi tanımlama ve standart yapma
`Calendar`, çalışma zamanı takvimini modelleyen sınıftır. **“My Cal”** adlı yeni bir takvim ekleyip `makeStandardCalendar` metodunu çağırmak, onu tüm proje için varsayılan takvim haline getirir.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro ipucu:** `makeStandardCalendar` yöntemi, sağlanan takvimi proje için varsayılan olarak otomatik işaretler; bu, **standart takvim ekleme** işlevine ihtiyacınız olduğunda tam olarak ihtiyacınız olan şeydir.

### Adım 4: projeyi kaydetme
SaveFileFormat, bir proje kaydedilirken kullanılacak dosya formatını belirten bir enum'dur.  
Projeyi (yeni takvim dahil) bir XML dosyasına kalıcı olarak kaydedin.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Farklı bir Project sürümü tercih ediyorsanız dosya adını veya formatı (`SaveFileFormat.Pp`) değiştirebilirsiniz.

### Adım 5: tamamlanma mesajını gösterme
İşlemin hatasız tamamlandığını gösteren görsel bir uyarı verin.

```java
System.out.println("Process completed Successfully");
```

## Yaygın sorunlar ve çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Dosya bulunamadı** | `dataDir` points to a non‑existent folder | Create the folder or use an absolute path |
| **Lisans istisnası** | Running without a valid Aspose.Tasks license in production | Apply a license file via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Boş takvim** | Forgetting to add working time definitions | Use `cal1.getWeekDays().add(WeekDay.DayType.Monday)` etc., if you need custom hours |

## Sıkça sorulan sorular

**S: Aspose.Tasks tüm Microsoft Project sürümleriyle uyumlu mu?**  
**C:** Evet, Aspose.Tasks 2000'den en son sürümlere kadar geniş bir Microsoft Project sürüm yelpazesini destekler.

**S: Takvim ayarlarını daha da özelleştirebilir miyim?**  
**C:** Kesinlikle! `WeekDay` ve `WorkingTime` sınıflarını kullanarak çalışma günlerini değiştirebilir, istisnalar ekleyebilir ve belirli çalışma zamanlarını tanımlayabilirsiniz.

**S: Aspose.Tasks kurumsal‑düzey uygulamalar için uygun mu?**  
**C:** Kesinlikle. Kütüphane yüksek performanslı, ölçeklenebilir ortamlar için tasarlanmıştır ve büyük Project dosyaları için kapsamlı destek sunar.

**S: Aspose.Tasks geliştiricilere teknik destek sağlıyor mu?**  
**C:** Evet, Aspose özel forumlar, bilet‑tabanlı destek ve kapsamlı belgeler sunarak sorunları hızlı bir şekilde çözmenize yardımcı olur.

**S: Satın almadan önce Aspose.Tasks'i deneyebilir miyim?**  
**C:** Evet, [website](https://purchase.aspose.com/buy) adresinde bulunan ücretsiz deneme sürümünü inceleyebilir, tüm özellikleri değerlendirdikten sonra karar verebilirsiniz.

---

**Son Güncelleme:** 2026-08-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [Aspose.Tasks ile Java'da Proje Takvimini Ayarlama](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java ile Özel Takvim İstisnaları Oluşturma](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}