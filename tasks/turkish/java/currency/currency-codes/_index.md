---
date: 2026-09-25
description: Aspose.Tasks for Java kullanarak MS Project dosyalarından para birimi
  kodlarını nasıl alacağınızı öğrenin – Java geliştiricilerinin ihtiyaç duyduğu para
  birimi kodunu hızlı bir şekilde elde etmenin yolu.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Aspose.Tasks'te Para Birimi Kodlarını Yönetin
og_description: Aspose.Tasks kullanarak MS Project dosyalarından Java para birimi
  kodunu alın. Bu kılavuz, projeyi nasıl okuyacağınızı, ISO para birimi tanımlayıcısını
  nasıl çıkaracağınızı ve Java uygulamalarında nasıl kullanacağınızı gösterir.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: MS Project'ten Java para birimi kodunu alın
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Aspose.Tasks ile MS Project'ten Java para birimi kodunu alın
url: /tr/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'ten Aspose.Tasks ile Java para birimi kodunu alın

## Giriş
Bu öğreticide, Aspose.Tasks Java API'sini kullanarak bir MS Project dosyasından **java para birimi kodunu nasıl alacağınızı** öğreneceksiniz. Çoklu para birimli finansal raporlar oluşturmanız, farklı bölgelerdeki projeleri birleştirmeniz veya yalnızca bir alt sistemde doğru para birimi simgesini göstermeniz gerekse, aşağıdaki adımlar ortam kurulumundan ISO para birimi tanımlayıcısını döndüren tek satırlık çağrıya kadar sizi yönlendirecek. Kılavuzun sonunda, desteklenen herhangi bir Project dosya formatını yükleyebilecek ve `USD`, `EUR` veya `GBP` gibi üç harfli para birimi kodunu çıkarabilecek konforlu bir hâle geleceksiniz.

## Hızlı cevaplar
- **API ne yapar?** MS Project dosyalarını okur ve para birimi kodu gibi özellikleri ortaya çıkarır.  
- **Hangi dil kullanılıyor?** Java, Aspose.Tasks for Java kütüphanesi aracılığıyla.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Kodu tek satırda alabilir miyim?** Evet—`prj.get(Prj.CURRENCY_CODE)` para birimi kodu dizesini anında döndürür.  
- **Tüm Project sürümleriyle uyumlu mu?** Aspose.Tasks, eski MPP, XML ve XER dosyaları dahil olmak üzere 20'den fazla giriş formatını destekler.

## MS Project dosyasını okumak ne demektir?
Bir MS Project dosyasını okumak, programlı olarak bir *.mpp* (veya XML veya XER gibi desteklenen diğer bir format) dosyasını açmak ve iç veri yapılarına erişmek anlamına gelir. Bu yapılar görevleri, kaynakları, takvimleri, maliyet tablolarını ve finansal ayarları içerir. Dosyayı ayrıştırarak Microsoft Project'i başlatmadan bilgi çıkarabilir, otomatik raporlama, taşıma ve entegrasyon iş akışlarını etkinleştirebilirsiniz.

## Aspose.Tasks'i msproject dosyalarını okumak için neden kullanmalısınız?
Aspose.Tasks, COM etkileşimi veya yerel bir Microsoft Project kurulumuna ihtiyaç duymayan saf Java çözümü sunar. 20'den fazla dosya formatını destekler, binlerce görevi olan projeleri 100 MB'den az bellek kullanarak işleyebilir ve zengin bir nesne modeli sağlar. `Prj.CURRENCY_CODE` gibi sabitlere doğrudan erişim, para birimi bilgilerini anında ve güvenilir bir şekilde almanızı sağlar.

## Önkoşullar
Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

### Java geliştirme kiti (JDK) yüklü
11 veya daha yeni bir JDK gereklidir. Resmi Oracle sitesinden indirin: [burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java kütüphanesi
En son Aspose.Tasks for Java ikili dosyalarını edinin ve projenizin sınıf yoluna ekleyin. Tam dokümantasyon ve indirme bağlantıları [burada](https://reference.aspose.com/tasks/java/) mevcuttur.

## Paketleri içe aktar
`Project` sınıfı ve `Prj` sabitleri `com.aspose.tasks` ad alanında bulunur. Bunları Java kaynak dosyanızın en üstüne içe aktarın:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Adım adım kılavuz

### Adım 1: veri dizinini ayarla
*.mpp* dosyanızın bulunduğu klasörü tanımlayın. Çalışma zamanının proje dosyasını bulabilmesi için yolu ortamınıza göre ayarlayın.

```java
String dataDir = "Your Data Directory";
```

### Adım 2: proje dosyasını yükle
`Project` sınıfı, Aspose.Tasks'in bellekte tek bir MS Project dosyasını temsil eden üst‑seviye nesnesidir. Bir örnek oluşturmak dosyayı okur ve sorgulayabileceğiniz bellek içi bir model oluşturur.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Adım 3: para birimi kodunu al
`Prj.CURRENCY_CODE` sabiti, ISO para birimi tanımlayıcısını saklayan özelliği belirler. `prj.get(Prj.CURRENCY_CODE)` çağrısı, üç harfli kodu tek bir işlemde döndürür.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Çıktı, projenin kullanmak üzere yapılandırıldığı üç harfli ISO para birimi kodu (ör. `USD`, `EUR`, `GBP`) olacaktır.

### Adım 4: Java'da para birimi kodunu nasıl alırsınız (ek bağlam)
Projenizi yükleyin, `prj.get(Prj.CURRENCY_CODE)` çağırın ve sonucu bir `String` içinde saklayın. Ardından bu değeri para birimi tanımlayıcısı gerektiren herhangi bir finansal hizmete, raporlama motoruna veya UI bileşenine aktarabilirsiniz.

### Adım 5: (isteğe bağlı) para birimi kodunu kullan
Tipik alt sistem senaryoları şunları içerir:
- **Rapor oluşturma** – kodu maliyet sütunlarının önüne ekleyin (`USD 1,200`).  
- **API entegrasyonu** – para birimi parametresi isteyen ödeme geçitlerine ISO kodunu gönderin.  
- **Veri birleştirme** – portföy düzeyinde analiz için birden fazla projeyi para birimine göre gruplayın.

## Yaygın sorunlar ve çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Null çıktı** | Proje dosyası bir para birimi tanımlamıyor (varsayılan boş). | Microsoft Project'te para birimini ayarlayın veya okumadan önce `prj.set(Prj.CURRENCY_CODE, "USD");` ile atayın. |
| **Dosya bulunamadı** | `dataDir` yolu hatalı. | Yolu doğrulayın ve dosya adının büyük/küçük harf duyarlılığı dahil tam olarak eşleştiğinden emin olun. |
| **Desteklenmeyen dosya sürümü** | Çok eski veya bozuk *.mpp* dosyası. | En son Aspose.Tasks sürümüne yükseltin veya önce Microsoft Project'te dosyayı daha yeni bir formata dönüştürün. |

## Sıkça sorulan sorular

**Q: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?**  
A: Evet, API çok seviyeli görev hiyerarşilerini, kaynak havuzlarını, özel alanları ve takvimleri sınırsız şekilde okur.

**Q: Aspose.Tasks farklı MS Project dosya sürümleriyle uyumlu mu?**  
A: Kesinlikle. Project 98'den en son Office sürümlerine kadar MPP, XML, XER ve diğer formatları destekler.

**Q: Aspose.Tasks dokümantasyon ve destek sağlıyor mu?**  
A: Kapsamlı API referansı, kod örnekleri ve özel teknik destek Aspose web sitesinde mevcuttur.

**Q: Aspose.Tasks'i satın almadan önce deneyebilir miyim?**  
A: Tüm özellikleri, para birimi kodu çıkarımı dahil, değerlendirebilmeniz için ücretsiz bir deneme sunulur.

**Q: Değerlendirme için geçici bir lisans nereden temin edebilirim?**  
A: Geçici lisanslar [web sitesi](https://purchase.aspose.com/temporary-license/) adresinden temin edilebilir.

**Son Güncelleme:** 2026-09-25  
**Test Edilen:** Aspose.Tasks for Java (latest version)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Project Özellikleri Java – Aspose.Tasks ile Meta Verileri Okuma](/tasks/java/project-properties/)
- [Microsoft Project'ten Proje Bilgilerini Aspose.Tasks for Java ile Okuma](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks içinde MS Project Taslak Kodlarını Al](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}