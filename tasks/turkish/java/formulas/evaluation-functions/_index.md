---
date: 2025-12-09
description: Java kullanarak proje nesnesi oluşturmayı ve Aspose.Tasks formüllerinde
  değerlendirme işlevlerini desteklemeyi öğrenin. Görevler için genişletilmiş öznitelik
  oluşturmayı keşfedin.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Java’da Proje Nesnesi Oluştur – Aspose.Tasks’te Değerlendirme Fonksiyonlarını
  Destekle
url: /tr/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Formüllerinde Değerlendirme Fonksiyonlarını Destekleme

## Giriş
Aspose.Tasks for Java, **create project object java** örnekleri oluşturmanıza ve Microsoft Project fonksiyonlarını doğrudan Java kodunuz içinde değerlendirmenize olanak tanır. Bu formülleri gömerek, karmaşık hesaplamalar çalıştırabilir, özel raporlar oluşturabilir ve proje analizini geliştirme ortamınızdan çıkmadan otomatikleştirebilirsiniz. Bu öğretici, proje nesnesini kurmaktan özel veri tutabilecek bir genişletilmiş öznitelik eklemeye kadar tüm süreci adım adım gösterir.

## Hızlı Yanıtlar
- **“create project object java” ne anlama geliyor?** Programatik olarak manipüle edebileceğiniz bellek içi bir `Project` örneği oluşturur.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (resmi siteden indirin).  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçici veya tam lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Özel alanlar kullanabilir miyim?** Evet – görevlerine genişletilmiş öznitelikler tanımlayabilir ve ekleyebilirsiniz.  
- **Bu, tüm Project dosya formatlarıyla uyumlu mu?** Aspose.Tasks, MPP, MPT ve XML formatlarını destekler.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8+ ve IntelliJ IDEA veya Eclipse gibi bir IDE.  
2. **Aspose.Tasks for Java Kütüphanesi** – Kütüphaneyi [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin ve projenize ekleyin.

## Paketleri İçe Aktarma
Projeler, görevler ve genişletilmiş özniteliklerle çalışabilmeniz için Aspose.Tasks ad alanını Java sınıfınıza ekleyin:

```java
import com.aspose.tasks.*;
```

## Adım 1: Project Object Java Oluşturma
Yeni bir `Project` nesnesi oluşturun. Bu, tanımlayacağınız tüm görevler, kaynaklar ve özel veriler için bir kapsayıcı görevi görecektir.

```java
Project project = new Project();
```

Yukarıdaki satır, **creates project object java** ifadesiyle, boş ve özelleştirmeye hazır bir proje nesnesi oluşturur.

## Adım 2: Genişletilmiş Öznitelik Nasıl Oluşturulur
Her görev için özel sayısal veri (ör. bir sinüs değeri) depolayacak bir genişletilmiş öznitelik tanımlayın.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Burada, `Number` türünde “Sine” adlı **create extended attribute** oluşturuyor ve görevlerle ilişkilendiriyoruz.

## Adım 3: Genişletilmiş Özniteliği Projeye Ekleyin
Öznitelik tanımını projeye kaydedin, böylece her görev ona referans verebilir.

```java
project.getExtendedAttributes().add(attr);
```

## Adım 4: Yeni Bir Görev Oluşturun
Projenin kök görevi altında “Task” adlı basit bir görev ekleyin.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Adım 5: Genişletilmiş Özniteliği Göreve Bağlayın
Önceden tanımlanan genişletilmiş özniteliği yeni oluşturulan göreve bağlayın.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Artık görev, formüllerde veya hesaplamalarda kullanabileceğiniz özel bir “Sine” alanına sahiptir.

## Değerlendirme Fonksiyonlarını Neden Kullanmalısınız?
MS Project fonksiyonlarını Aspose.Tasks formüllerine gömmek şunları yapmanızı sağlar:

- Harici araçlar kullanmadan anlık hesaplamalar yapın (ör. `Sin([Start])`).  
- Tüm proje mantığını tek, sürdürülebilir bir kod tabanında tutun.  
- Gerçek zamanlı veri değişikliklerini yansıtan dinamik raporlar oluşturun.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Formül `NaN` döndürüyor** | Özel alan tipinin beklenen sayısal tip ile eşleştiğini doğrulayın. |
| **Genişletilmiş öznitelik görünmüyor** | Öznitelik tanımının görevler oluşturulmadan **önce** projeye eklendiğinden emin olun. |
| **Lisans istisnası** | Geçici veya tam bir lisans kurun; deneme modu bazı özellikleri kısıtlayabilir. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java karmaşık MS Project formüllerini işleyebilir mi?**  
C: Evet, Aspose.Tasks for Java, geniş bir MS Project fonksiyon yelpazesinin değerlendirilmesini destekler ve Java uygulamaları içinde karmaşık hesaplamalara olanak tanır.

**S: Aspose.Tasks for Java farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks for Java, MPP, MPT ve XML formatları dahil olmak üzere çeşitli Microsoft Project dosya sürümlerini destekler.

**S: Aspose.Tasks for Java'ı satın almadan önce deneyebilir miyim?**  
C: Evet, web sitesinden ücretsiz deneme sürümünü [buradan](https://purchase.aspose.com/buy) indirebilirsiniz.

**S: Aspose.Tasks for Java için destek nasıl alabilirim?**  
C: Aspose.Tasks topluluk forumundan [buradan](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans mevcut mu?**  
C: Evet, test amaçlı geçici bir lisansı Aspose web sitesinden [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

---

**Son Güncelleme:** 2025-12-09  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}