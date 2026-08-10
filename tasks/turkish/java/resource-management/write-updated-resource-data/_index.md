---
date: 2026-06-30
description: Aspose.Tasks for Java kullanarak birden çok kaynağı nasıl güncelleyeceğinizi
  ve kaynak grup verilerini nasıl değiştireceğinizi öğrenin, ardından projeyi MPP
  olarak dışa aktarın ve projeyi MPP olarak kaydedin.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Aspose.Tasks for Java'da Birden Çok Kaynağı Güncelleme
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java'da Birden Çok Kaynağı Güncelleme
url: /tr/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java'da Birden Çok Kaynağı Güncelle

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak bir Microsoft Project dosyasında **birden çok kaynağı güncelle**meyi öğreneceksiniz. Oranları değiştirmek, grupları yeniden atamak veya güncellenmiş dosyayı MPP olarak dışa aktarmak ister misiniz, aşağıdaki adımlar eksiksiz, üretim‑hazır bir iş akışını size gösterir. Microsoft Project kurulumu gerekmez ve API, yüzlerce kaynağa sahip projeleri verimli bir şekilde işleyebilir.

## Hızlı Yanıtlar
- **Birden fazla kaynağı aynı anda güncelleyebilir miyim?** Evet – `ResourceCollection` içinde döngü yaparak nitelikleri tek geçişte ayarlayabilirsiniz.  
- **Dosyayı MPP olarak kaydeden yöntem hangisidir?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Ticari kullanım için lisansa ihtiyacım var mı?** Üretim için ücretli bir lisans gereklidir; ücretsiz deneme mevcuttur.  
- **Hangi Java sürümleri destekleniyor?** Java 6 ve üzeri, Java 17 LTS dahil.  
- **Toplu güncelleme performanslı mı?** Aspose.Tasks, tipik bir sunucuda 500 kaynaklu projeleri 2 saniyenin altında işler.

## “Birden çok kaynağı güncelleme” nedir?
**“Update multiple resources”**, tek bir Project dosyası içinde birden fazla kaynak kaydının özelliklerini—örneğin oranlar, gruplar, takvimler veya özel alanlar—programlı olarak değiştirmeyi ifade eder. Bu işlem, proje verilerini kurumsal kaynak planlama sistemleriyle senkronize ederken, birçok kaynakta bütçeleri ayarlarken veya organizasyon çapında politika değişiklikleri uygularken sıkça gereklidir.

## Kaynak grubunu değiştirmek ve projeyi MPP olarak dışa aktarmak için Aspose.Tasks neden kullanılmalı?
Aspose.Tasks, MPP, XML ve CSV dahil **50+ giriş ve çıkış formatını** destekler ve **projeyi MPP olarak dışa aktarmayı** tüm dosyayı belleğe yüklemeden yapabilir. Kütüphane, **2 GB** kadar büyük dosyaları işleyebilir, böylece **projeyi MPP olarak kaydetmeyi** hızlı ve güvenilir bir şekilde yapabilirsiniz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Sisteminizde yüklü Java Development Kit (JDK).  
2. Aspose.Tasks for Java kütüphanesi. Bunu [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
3. Java programlama temelleri.

## Paketleri İçe Aktarma

`import` ifadeleri, gerekli Aspose.Tasks sınıflarını kaynak dosyanıza getirir.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Adım 1: Veri Dizinini Ayarlama

Veri dosyalarınızın bulunduğu dizini tanımlayın:

```java
String dataDir = "Your Data Directory";
```

## Adım 2: Giriş ve Çıkış Dosyalarını Belirtme

Giriş MS Project dosyasının ve ortaya çıkan güncellenmiş dosyanın yollarını tanımlayın:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Adım 3: Projeyi Yükleme

`Project`, belleğe yüklenmiş bir Microsoft Project dosyasını temsil eder ve görevlere, kaynaklara ve diğer proje verilerine erişim sağlar.

```java
Project project = new Project(file);
```

## Adım 4: Bir Kaynak Ekleme ve Nitelikleri Ayarlama

`Resource`, bireysel bir proje kaynağını modeller ve oranları, grupları, takvimleri ve diğer nitelikleri ayarlamanıza olanak tanır.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Adım 5: Birden Çok Kaynağı Verimli Şekilde Güncelleme

`ResourceCollection`, bir projedeki tüm kaynakların koleksiyonudur ve `project.getResources()` ile erişilebilir.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Adım 6: Projeyi Kaydetme

`SaveFileFormat`, MPP, XML ve PDF gibi proje kaydetme için desteklenen dosya formatlarını listeler.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Bir projede birden çok kaynağı nasıl güncellerim?
Mevcut projeyi yükleyin, `ResourceCollection`'ını alın ve her `Resource` nesnesi üzerinde döngü yapın. Her kaynak için oranlar, gruplar veya özel nitelikler gibi gerekli alanları değiştirin, ardından bir sonraki öğeye geçin. Tüm kaynaklar işlendiğinde, değişiklikleri verimli bir şekilde kalıcı hâle getirmek için `project.save(...)` metodunu bir kez çağırın.

## Yaygın Sorunlar ve Çözümler
- **Kaynak ID'leri çakışıyor** – `project.getResources().add(new Resource())` kullanarak her yeni kaynağın benzersiz bir ID almasını sağlayın.  
- **Oran biçimi hataları** – `ResourceRate` nesnelerini kullanın ve `RateType`'ı `StandardRate` veya `OvertimeRate` olarak ayarlayın.  
- **Büyük dosyalar bellek baskısı oluşturuyor** – Bellek kullanımını azaltmak için yüklemeden önce `Project.setReadOnly(true)` etkinleştirin.

## Sık Sorulan Sorular
**Q: Aynı projede Aspose.Tasks for Java kullanarak birden çok kaynağı güncelleyebilir miyim?**  
A: Evet, kaynaklar üzerinde döngü yaparak ve niteliklerini uygun şekilde ayarlayarak birden çok kaynağı güncelleyebilirsiniz.

**Q: Aspose.Tasks, MS Project dışındaki diğer dosya formatlarını destekliyor mu?**  
A: Evet, Aspose.Tasks XML, MPP ve daha fazlası dahil çeşitli dosya formatlarını destekler.

**Q: Aspose.Tasks farklı Java sürümleriyle uyumlu mu?**  
A: Aspose.Tasks, Java 6 ve üzeri sürümlerle uyumludur.

**Q: Aspose.Tasks ile MS Project dosyalarında başka işlemler yapabilir miyim?**  
A: Evet, görevleri, kaynakları ve takvimleri okuma, yazma ve manipüle etme gibi geniş bir yelpazede işlem yapabilirsiniz.

**Q: Aspose.Tasks için ek yardım veya destek nereden bulunabilir?**  
A: Herhangi bir yardım veya soru için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**Q: Güncellenmiş dosyayı MPP formatına nasıl dışa aktarırım?**  
A: Tüm kaynak değişikliklerini yaptıktan sonra `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` metodunu çağırın.

**Q: Bir kaynak grubunu değiştirmek için en iyi yöntem nedir?**  
A: Projeyi kaydetmeden önce her `Resource` nesnesinde `Resource.Group` özelliğini ayarlayın.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye kaynak ekleme](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java ile MS Project kaynak maliyetlerini yönetme](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks for Java ile MPP'yi Excel'e dışa aktarma](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}