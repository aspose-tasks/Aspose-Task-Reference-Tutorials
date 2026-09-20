---
date: 2026-09-20
description: Aspose.Tasks for Java kullanarak para birimi simgesi mpp'yi nasıl çıkaracağınızı
  ve proje özelliklerini nasıl güncelleyeceğinizi öğrenin. Sadece birkaç satır kodla
  simgeyi değiştirin ve alın.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Aspose.Tasks for Java kullanarak para birimi simgesi mpp'yi çıkarın
og_description: Aspose.Tasks for Java kullanarak para birimi simgesi mpp'yi nasıl
  çıkaracağınızı ve proje özelliklerini nasıl güncelleyeceğinizi öğrenin. Hızlı, güvenilir
  ve üretime hazır.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Aspose.Tasks Java ile para birimi simgesi mpp nasıl çıkarılır
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Aspose.Tasks Java ile para birimi simgesi mpp nasıl çıkarılır
url: /tr/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java kullanarak mpp para birimi simgesini çıkarma

## Giriş
Bu öğreticide **java project properties** ile nasıl çalışılacağını öğreneceksiniz — özellikle Microsoft Project (MPP) dosyasından **extract currency symbol mpp** nasıl çıkarılacağını ve Aspose.Tasks kütüphanesini kullanarak **change currency symbol java** veya **retrieve currency symbol java** nasıl yapılacağını. Finansal raporlama aracı oluşturuyor, Project verilerini bir ERP sistemine entegre ediyor ya da UI'nizde doğru para birimi simgesini göstermeniz gerektiğinde, bu küçük ama önemli görevi ustalaşmak Java uygulamalarınızı daha sağlam ve kullanıcı‑dostu hâle getirecektir.

## Hızlı cevaplar
- **“extract currency symbol mpp” ne anlama geliyor?** MPP (Microsoft Project) dosyasında saklanan para birimi simgesini okumak anlamına gelir.  
- **Bu işlemi hangi kütüphane gerçekleştirir?** Aspose.Tasks for Java bu iş için basit bir API sağlar.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Ne kadar sürer?** Aşağıdaki kodla bir dakikadan kısa sürede simgeyi alabilirsiniz.  
- **Simgiyi de değiştirebilir miyim?** Evet – aynı `Prj.CURRENCY_SYMBOL` özelliğini kullanarak yeni bir değer ayarlayabilirsiniz.

## “extract currency symbol mpp” nedir?
MPP dosyasından para birimi simgesini çıkarmak, Microsoft Project'in dosya başlığında projenin para birimini temsil etmek için sakladığı tek karakterlik dizeyi okumak anlamına gelir. Bu işlem, değerleri sabit kodlamadan kendi uygulamalarınızda doğru simgeyi (ör. $, €, £) göstermenizi sağlar.

## Java proje özelliklerinde para birimi simgesini neden güncellemeliyiz?
Para birimi simgesini güncellemek, raporları, faturaları ve gösterge tablolarını anında yerelleştirmenizi sağlar. Birden fazla bölgede projeler yürüten işletmeler, tüm proje dosyasını kopyalamaya gerek kalmadan tek bir adımda simgeyi değiştirebilir. Aspose.Tasks, özelliği bellek içinde değiştirebilir ve dosyayı geri kaydedebilir; 2.000'e kadar görev içeren projeleri belirgin bir performans kaybı olmadan destekler.

## Önkoşullar
1. **Java Development Kit (JDK)** – version 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. Kodunuzdan referans verebileceğiniz bir klasöre yerleştirilmiş geçerli bir **project.mpp** dosyası.

## Paketleri içe aktar
İlk olarak, Project dosyalarıyla çalışmak için ihtiyaç duyacağımız sınıfları içe aktarın.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Adım 1: veri dizinini tanımla
Uygulamaya *.mpp* dosyanızın nerede olduğunu söyleyin.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `System.getProperty("user.dir")` kullanarak herhangi bir makinede çalışan mutlak bir yol oluşturun.

## Adım 2: MS Project dosyasını yükle
`Project`, Aspose.Tasks’in bellek içinde tek bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir. Bu nesneyi oluşturmak, Microsoft Project’in yüklü olmasını gerektirmeden dosya yapısını yükler.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Adım 3: para birimi simgesini al (ve isteğe bağlı olarak değiştir)
`Prj.CURRENCY_SYMBOL`, para birimi simgesini saklayan özellik anahtarıdır. Okunduğunda mevcut simgeyi döndürür; yeni bir dize atandığında projenin para birimi tanımı güncellenir.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` çağrısı, simgeyi (ör. `$`) konsola yazar, çıkarmanın başarılı olduğunu doğrular.

## Yaygın sorunlar ve nasıl düzeltilir
| Belirti | Muhtemel neden | Çözüm |
|---------|----------------|-------|
| `project.get(...)` üzerinde `NullPointerException` | Yanlış dosya yolu veya dosya bulunamadı | `dataDir` ve dosya adını doğrulayın; hata ayıklamak için `new File(dataDir).exists()` kullanın |
| Beklenmeyen simge (ör. `?`) | Proje standart olmayan bir yerel ayarla oluşturuldu | Kaynak MPP dosyasının gerçekten bir para birimi simgesi tanımladığından emin olun; yukarıda gösterildiği gibi programlı olarak bir simge ayarlayabilirsiniz |
| Lisans hatası | Geçerli bir lisans dosyası olmadan deneme sürümünü kullanmak | `Project` nesnesini oluşturmadan önce `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kodu ile lisansınızı yükleyin |

## Sıkça sorulan sorular

**Q:** Aspose.Tasks kullanarak para birimi simgelerinin yanı sıra başka proje özelliklerini de manipüle edebilir miyim?  
**A:** Evet, Aspose.Tasks görevleri, kaynakları, atamaları, takvimleri ve daha birçok proje özelliğini düzenlemenizi sağlar.

**Q:** Aspose.Tasks, MS Project dosyalarının farklı sürümleriyle uyumlu mu?  
**A:** Kesinlikle. Project 98'den en yeni sürümlere kadar MPP, MPT ve XML formatlarını destekler.

**Q:** Aspose.Tasks geliştiriciler için dokümantasyon ve destek sunuyor mu?  
**A:** Kapsamlı API belgeleri, kod örnekleri ve özel bir destek forumu Aspose.Tasks web sitesinde mevcuttur.

**Q:** Aspose.Tasks'i satın almadan önce deneyebilir miyim?  
**A:** Evet – tam işlevsel bir ücretsiz deneme sürümü [Aspose web sitesinden](https://purchase.aspose.com/buy) indirilebilir.

**Q:** Aspose.Tasks için geçici bir lisans nasıl alabilirim?  
**A:** Değerlendirme amaçlı geçici lisanslar [Aspose geçici‑lisans sayfasında](https://purchase.aspose.com/temporary-license/) sağlanır.

---

**Son Güncelleme:** 2026-09-20  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Project Properties Java – Aspose.Tasks ile Metaveri Okuma](/tasks/java/project-properties/)
- [Aspose.Tasks ile MS Project'ten Para Birimini Alma](/tasks/java/currency/currency-codes/)
- [Aspose.Tasks for Java kullanarak MS Project'te Proje Başlangıç Tarihini Ayarlama](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}