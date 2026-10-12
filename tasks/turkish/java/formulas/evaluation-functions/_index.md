---
date: 2026-10-10
description: Aspose.Tasks içinde genişletilmiş öznitelik eklemeyi, değerlendirme fonksiyonlarını
  kullanmayı ve bu Java proje yönetimi kütüphanesiyle proje raporları oluşturmayı
  öğrenin.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Aspose.Tasks Formüllerinde Değerlendirme Fonksiyonlarını Destekleme
og_description: Aspose.Tasks içinde genişletilmiş öznitelik eklemeyi, değerlendirme
  fonksiyonlarını kullanmayı ve bu Java proje yönetimi kütüphanesiyle proje raporları
  oluşturmayı öğrenin.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Aspose.Tasks formüllerine genişletilmiş öznitelik ekleme
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Aspose.Tasks formüllerine genişletilmiş öznitelik ekleme
url: /tr/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks formüllerinde genişletilmiş öznitelik ekleme

## Giriş
Aspose.Tasks for Java, **Java proje yönetimi kütüphanesi** olup, Java'da bir `Project` nesnesi oluşturarak ve Microsoft Project işlevlerini doğrudan kodunuz içinde değerlendirerek proje raporları oluşturmanıza olanak tanır. Bu formülleri gömerek, karmaşık hesaplamalar yapabilir, özel raporlar üretebilir ve geliştirme ortamınızdan çıkmadan proje analizini otomatikleştirebilirsiniz. Bu öğreticide bir proje nesnesi oluşturmayı, genişletilmiş bir öznitelik eklemeyi ve değerlendirme işlevlerini kullanarak **add custom field task** verisini eklemeyi adım adım göstereceğiz.

## Hızlı cevaplar
- **“create project object java” ne anlama geliyor?** Bellekte bir `Project` örneği oluşturur ve bunu programlı olarak manipüle edebilirsiniz.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (resmi siteden indirin).  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçici veya tam bir Aspose.Tasks lisansı gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Özel alanları kullanabilir miyim?** Evet – görevlerine **add extended attribute** ekleyebilir ve bunları özel alanlar olarak kullanabilirsiniz.  
- **Bu tüm Project dosya formatlarıyla uyumlu mu?** Aspose.Tasks, 3 ana formatı (MPP, MPT, XML) ve 50'den fazla ek giriş/çıkış formatını destekler.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8+ ve IntelliJ IDEA veya Eclipse gibi bir IDE.  
2. **Aspose.Tasks for Java Kütüphanesi** – Kütüphaneyi [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirip projenize ekleyin.

## Paketleri içe aktar
Aspose.Tasks ad alanını Java sınıfınıza ekleyin, böylece projeler, görevler ve genişletilmiş özniteliklerle çalışabilirsiniz:

```java
import com.aspose.tasks.*;
```

## Proje raporu oluşturma – create project object java
`Project` sınıfı, bellekte bir Microsoft Project dosyasını temsil eder ve görevleri, kaynakları ve özel verileri ortaya çıkarır. Bu sınıfın bir örneğini oluşturmak, tanımlayacağınız tüm proje öğeleri için bir kapsayıcı sağlar.

```java
Project project = new Project();
```

Yukarıdaki satır, **creates project object java** boş ve özelleştirmeye hazır bir şekilde oluşturur.

## Genişletilmiş öznitelik ekleme
`ExtendedAttributeDefinition` sınıfı, görevlere eklenebilen bir özel alan tanımlar. Genişletilmiş bir öznitelik eklemek için, bu sınıfın `Number` tipinde bir örneğini oluşturun, “Sine” gibi bir takma ad atayın, projeye ait `ExtendedAttributes` koleksiyonuna ekleyin ve ardından özel alanı gerektiren her göreve bağlayın.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Burada, `Number` tipinde “Sine” adlı **add extended attribute** ekleyip görevlerle ilişkilendiriyoruz.

## Genişletilmiş özniteliği projeye ekleme
Öznitelik tanımını proje ile kaydederek, her görevin ona referans vermesini sağlayın.

```java
project.getExtendedAttributes().add(attr);
```

## Yeni bir görev oluşturma
`Task`, projedeki bir iş öğesini temsil eder ve özel alanlar içerebilir.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Projeye özel alan görevi ekleme
Önceden tanımlanmış genişletilmiş özniteliği yeni oluşturulan göreve bağlayın; böylece göreve formüllerde veya hesaplamalarda kullanabileceğiniz özel bir “Sine” alanı eklenir.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Artık görev, formüllerde veya hesaplamalarda kullanabileceğiniz özel bir “Sine” alanına sahiptir. Bu aynı zamanda **add custom field task** verisini programlı olarak eklemenin yoludur.

## Değerlendirme işlevlerini neden kullanmalısınız?
Değerlendirme işlevleri, yerel Microsoft Project formüllerini (ör. `Sin([Start])`) doğrudan Aspose.Tasks içinde gömmenizi sağlar; böylece dış işlem olmadan anlık hesaplamalar yapabilirsiniz. Bu, tüm proje mantığını tek bir yerde tutar, veri senkronizasyon hatalarını azaltır ve rapor oluşturmayı hızlandırır. Aspose.Tasks, Java içinde kapsamlı bir hesaplama motoru sağlayarak 100'den fazla MS Project işlevinin değerlendirilmesini destekler.

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|-------|----------|
| **Formül `NaN` döndürüyor** | Özel alan tipinin beklenen sayısal tip ile eşleştiğini doğrulayın. |
| **Genişletilmiş öznitelik görünmüyor** | Öznitelik tanımının görevler oluşturulmadan **önce** projeye eklendiğinden emin olun. |
| **Lisans istisnası** | Geçici veya tam bir **Aspose.Tasks lisansı** kurun; deneme modu bazı özellikleri kısıtlayabilir. |
| **Geçici lisans eksik** | **Aspose** web sitesinden bir **geçici lisans** edinin. |

## Sıkça sorulan sorular

**S: Aspose.Tasks for Java karmaşık MS Project formüllerini işleyebilir mi?**  
C: Evet, Aspose.Tasks for Java, geniş bir MS Project işlev yelpazesinin değerlendirilmesini destekler ve Java uygulamaları içinde karmaşık hesaplamalara olanak tanır.

**S: Aspose.Tasks for Java farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks for Java, MPP, MPT ve XML formatları dahil olmak üzere çeşitli Microsoft Project dosya sürümlerini destekler.

**S: Aspose.Tasks for Java'ı satın almadan deneyebilir miyim?**  
C: Evet, web sitesinden ücretsiz bir deneme sürümü indirebilirsiniz: [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**S: Aspose.Tasks for Java için nasıl destek alabilirim?**  
C: Aspose.Tasks topluluk forumundan destek alabilirsiniz: [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**S: Aspose.Tasks for Java için geçici bir lisans mevcut mu?**  
C: Evet, test amaçlı geçici bir lisansı Aspose web sitesinden edinebilirsiniz: [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Sonuç
Bu adımları izleyerek **create project object**, **add extended attribute** ve değerlendirme işlevlerini kullanarak **generate project report** otomatik olarak oluşturmayı öğrendiniz. Artık bu temeli, daha zengin proje analizleri, özel panolar veya otomatik zamanlama araçları oluşturmak için genişletebilirsiniz — tümü Aspose.Tasks for Java tarafından desteklenir.

**Son Güncelleme:** 2026-10-10  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java proje yönetiminde özel sütunlar ve genişletilmiş öznitelikler](/tasks/java/project-management/extended-attributes/)
- [Aspose.Tasks for Java ile Genişletilmiş Görev Özniteliklerini Okuma](/tasks/java/task-properties/extended-task-attributes/)
- [Aspose.Tasks for Java Kullanımı – Kaynak Atamalarına Genişletilmiş Öznitelik Ekleme](/tasks/java/resource-assignments/add-extended-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}