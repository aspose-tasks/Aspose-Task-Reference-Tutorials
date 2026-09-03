---
date: 2026-05-26
description: Aspose.Tasks for Java kullanarak MPP'yi CSV'ye dışa aktarmayı, projeyi
  şablon olarak kaydetmeyi ve MPP'yi text'e dönüştürmeyi öğrenin.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: Aspose.Tasks Java ile MPP'yi CSV, Text & Template olarak dışa aktar
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java ile MPP'yi CSV, Text & Template olarak dışa aktar
url: /tr/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP'yi CSV, Metin ve Şablon Olarak Aspose.Tasks for Java ile Dışa Aktarma

## Giriş
Bu öğreticide **MPP'yi CSV olarak nasıl dışa aktarılır** keşfedecek, yeniden kullanılabilir proje şablonları oluşturacak ve Aspose.Tasks Java kütüphanesini kullanarak düz‑metin çıktıları üreteceksiniz. Raporlama boru hattı oluşturuyor, proje oluşturmayı otomatikleştiriyor ya da diğer sistemlerle entegrasyon sağlıyor olun, bu adımlar ham MPP dosyasını ihtiyacınız olan tam çıktıya—hızlı bir şekilde ve Microsoft Project kurmadan—taşımanızı sağlar.

## Hızlı Yanıtlar
- **MPP'yi CSV olarak dışa aktarabilir miyim?** Evet – `project.save("output.csv", SaveFileFormat.CSV)` çağrısını yapın.  
- **Düz metin olarak nasıl dışa aktarırım?** `save` metoduyla `SaveFileFormat.TEXT` kullanın.  
- **“save project as template” ne yapar?** `.mpt` dosyası oluşturur; tarih ve temel çizgileri kaldırır, sadece iskeleti bırakır.  
- **Bir lisansa ihtiyacım var mı?** Değerlendirme için bir deneme sürümü çalışır; ticari lisans değerlendirme sınırlamalarını kaldırır.  
- **Hangi Java sürümü gereklidir?** Java 8 veya daha yenisi tam olarak desteklenir.

## “save project as template” nedir?
Bir projeyi şablon (`.mpt`) olarak kaydetmek, yapıyı, görev hiyerarşisini ve kaynak atamalarını yakalar; aynı zamanda gerçek başlangıç/bitiş tarihlerini ve temel çizgi verilerini kaldırır. Bu, şablonu birden çok yeni proje için standart bir proje düzeni yeniden kullanmak için ideal kılar. Tüm özel alanları, maliyet oranlarını ve atama detaylarını korur, böylece şablon yeni bir projeye uygulanırken önemli yapılandırmalar kaybolmaz.

## Neden Aspose.Tasks for Java Kullanmalı?
Microsoft Project olmadan doğrudan Java’dan MPP'yi CSV, metin veya şablon olarak dışa aktarın. Aspose.Tasks **20+ Microsoft Project sürümünü** (2000‑2024) destekler ve **500 MB**'a kadar dosyayı bellek‑verimli modda işleyebilir; bu da sunucu‑tarafı otomasyon, CI boru hatları ve çapraz‑platform araçları için idealdir.

## Önkoşullar
- Java Development Kit 8 veya daha yüksek bir sürüm yüklü olmalıdır.  
- Aspose.Tasks for Java kütüphanesi projenize eklenmiş olmalı – [buradan](https://releases.aspose.com/tasks/java/) indirin.  
- Diğer Aspose kütüphanelerini de [buradan](https://releases.aspose.com/) keşfedebilirsiniz.  
- Java ve Maven/Gradle proje yapılandırması hakkında temel bilgi.

## Paketleri İçe Aktarma
`Project` sınıfı, Aspose.Tasks'in bir Microsoft Project dosyasını bellekte temsil eden çekirdek nesnesidir. Kütüphaneyi derleme dosyanıza ekledikten sonra gerekli sınıfları içe aktarın:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Projeyi CSV Olarak Kaydet (MPP'yi CSV'ye Dışa Aktarma)
MPP dosyasını CSV’ye dışa aktarmak, görev verilerini Excel, Power BI veya herhangi bir analiz platformuna beslemenizi sağlar.

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: CSV Olarak Kaydet
`SaveFileFormat.CSV` Aspose.Tasks'e projeyi CSV formatında çıkarmasını söyler.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Projeyi Metin Olarak Kaydet (Metin Dışa Aktarma)
Düz‑metin dosyası, görevleri, kaynakları ve atamaları hızlı ve insan tarafından okunabilir bir döküm olarak sunar.

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: Metin Olarak Kaydet
`SaveFileFormat.TEXT` kütüphaneyi projenin düz‑metin temsilini üretmeye yönlendirir.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Projeyi Şablon Olarak Kaydet (Java'da Proje Şablonu Oluşturma)

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: Şablon Seçeneklerini Ayarla
Tarih ve temel çizgileri kaldıran bir şablon dosyası oluşturmak için `Project.save` metodunu `SaveFileFormat.MPT` (veya `SaveFileFormat.TEMPLATE`) ile kullanın.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Adım 3: Şablon Olarak Kaydet
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Yaygın Sorunlar ve İpuçları
- **Dosya Bulunamadı:** `YourProject.mpp` yolunu doğrulayın veya mutlak bir yol kullanın.  
- **Lisans İstisnaları:** Geçerli bir lisans olmadan kütüphane değerlendirme modunda çalışır ve filigran ekleyebilir. Lisansınızı erken uygulayın (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Büyük Projeler:** 200 MB'den büyük dosyalar için JVM yığınını (`-Xmx2g`) artırarak `OutOfMemoryError` hatasını önleyin.  
- **Performans:** Birçok projeyi dönüştürürken, mümkün olduğunca tek bir `Project` örneğini yeniden kullanarak nesne oluşturma yükünü azaltın.

## Sonuç
**MPP'yi CSV olarak dışa aktarma**, **MPP'yi metne dönüştürme** ve **projeyi şablon olarak kaydetme** işlemlerini Aspose.Tasks for Java ile nasıl yapacağınızı gösterdik. Bu yetenekler, raporlamayı otomatikleştirmenize, standart proje iskeletleri oluşturmanıza ve proje verilerini herhangi bir downstream sisteme—Microsoft Project kurulumuna ihtiyaç duymadan—entegre etmenize olanak tanır.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java karmaşık, çok‑fazalı projeleri yönetebilir mi?**  
C: Evet, görevleri, kaynakları, atamaları, temel çizgileri ve özel alanları 2024'e kadar tüm Project sürümlerinde tam olarak destekler.

**S: Deneme sürümü mevcut mu?**  
C: Kesinlikle – ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Sorun yaşarsam nereden yardım alabilirim?**  
C: Resmi destek forumu [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresindedir; burada personel ve topluluk üyeleri sorulara yanıt verir.

**S: Kısa vadeli değerlendirme için geçici bir lisans alabilir miyim?**  
C: Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.

**S: Aspose.Tasks Linux ve macOS'ta çalışıyor mu?**  
C: Tamamen çapraz‑platformdur; Windows, macOS ve Linux'ta herhangi bir Java 8+ çalışma zamanı ile çalışır.

**Son Güncelleme:** 2026-05-26  
**Test Edilen:** Aspose.Tasks for Java 24.12 (latest)  
**Yazar:** Aspose

## İlgili Eğitimler

- [MPP Dosyası Nasıl Oluşturulur – Aspose.Tasks ile Boş Projeyi MPP Formatında Oluşturma ve Kaydetme](/tasks/java/project-configuration/create-save-mpp/)
- [MPP Dosyasını Java'da Yükle – Aspose.Tasks ile Proje Özelliklerini Yönetme](/tasks/java/project-management/default-properties/)
- [MPP'yi Excel'e Nasıl Dışa Aktarılır – Aspose.Tasks for Java ile](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}