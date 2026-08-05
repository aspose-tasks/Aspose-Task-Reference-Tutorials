---
date: 2026-02-13
description: Java’da bir proje nesnesi oluşturarak, genişletilmiş öznitelikler ekleyerek
  ve Aspose.Tasks ile değerlendirme fonksiyonlarını kullanarak proje raporu oluşturmayı
  öğrenin.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Proje Raporu Oluştur – Java'da Proje Nesnesi Oluştur
url: /tr/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Formüllerinde Değerlendirme Fonksiyonlarını Destekleme

## Giriş
Aspose.Tasks for Java, Java'da bir **project object** oluşturarak ve Microsoft Project fonksiyonlarını doğrudan kodunuz içinde değerlendirerek **project report** oluşturmanıza olanak tanır. Bu formülleri gömerek, karmaşık hesaplamalar çalıştırabilir, özel raporlar oluşturabilir ve geliştirme ortamınızdan çıkmadan proje analizini otomatikleştirebilirsiniz. Bu öğreticide bir proje nesnesi oluşturmayı, genişletilmiş bir özellik eklemeyi ve değerlendirme fonksiyonlarını kullanarak **add custom field task** verilerini nasıl ekleyeceğinizi adım adım göstereceğiz.

## Hızlı Yanıtlar
- **“create project object java” ne anlama geliyor?** Programatik olarak manipüle edebileceğiniz bellek içi bir `Project` örneği oluşturur.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (resmi siteden indirin).  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçici veya tam bir Aspose.Tasks lisansı gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Özel alanlar kullanabilir miyim?** Evet – görevlere **add extended attribute** ekleyebilir ve bunları özel alanlar olarak kullanabilirsiniz.  
- **Bu, tüm Project dosya formatlarıyla uyumlu mu?** Aspose.Tasks, MPP, MPT ve XML formatlarını destekler.

## Önkoşullar
1. **Java Geliştirme Ortamı** – JDK 8+ ve IntelliJ IDEA veya Eclipse gibi bir IDE.  
2. **Aspose.Tasks for Java Kütüphanesi** – Kütüphaneyi [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirip projenize ekleyin.

## Paketleri İçe Aktarın
Aspose.Tasks ad alanını Java sınıfınıza ekleyin, böylece projeler, görevler ve genişletilmiş özelliklerle çalışabilirsiniz:

```java
import com.aspose.tasks.*;
```

## Proje Raporu Oluşturma – Create Project Object Java
Yeni bir `Project` nesnesi örnekleyin. Bu, tanımlayacağınız tüm görevler, kaynaklar ve özel veriler için bir kapsayıcı görevi görecektir.

```java
Project project = new Project();
```

Yukarıdaki satır, **creates project object java** ifadesiyle, boş ve özelleştirmeye hazır bir proje nesnesi oluşturur.

## Genişletilmiş Özellik Nasıl Eklenir
Her görev için özel sayısal veri (ör. bir sinüs değeri) depolayacak bir genişletilmiş özellik tanımlayın.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Burada, `Number` türünde “Sine” adlı bir **add extended attribute** ekliyor ve bunu görevlerle ilişkilendiriyoruz.

## Genişletilmiş Özelliği Projeye Ekleyin
Özellik tanımını projeye kaydedin, böylece her görev ona başvurabilir.

```java
project.getExtendedAttributes().add(attr);
```

## Yeni Bir Görev Oluşturun
Projenin kök görevi altında “Task” adlı basit bir görev ekleyin.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Genişletilmiş Özelliği Göreve Bağlayın
Daha önce tanımlanan genişletilmiş özelliği yeni oluşturulan görevle bağlayın.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Artık görev, formüllerde veya hesaplamalarda kullanabileceğiniz özel bir “Sine” alanına sahiptir. Bu aynı zamanda **add custom field task** verilerini programlı olarak eklemenin yoludur.

## Değerlendirme Fonksiyonlarını Neden Kullanmalısınız?
Aspose.Tasks formüllerine MS Project fonksiyonlarını gömmek şunları sağlar:
- Harici araçlar kullanmadan (ör. `Sin([Start])`) anlık hesaplamalar yapın.  
- Tüm proje mantığını tek, sürdürülebilir bir kod tabanında tutun.  
- Gerçek zamanlı veri değişikliklerini yansıtan dinamik raporlar oluşturun, böylece **generate project report** işlemini otomatikleştirin.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Formula returns `NaN`** | Özel alan tipinin beklenen sayısal tip ile eşleştiğini doğrulayın. |
| **Extended attribute not visible** | Özellik tanımının görevler oluşturulmadan **önce** projeye eklendiğinden emin olun. |
| **License exception** | Geçici veya tam bir **Aspose.Tasks lisansı** kurun; deneme modu bazı özellikleri kısıtlayabilir. |
| **Missing temporary license** | Aspose web sitesinden bir **geçici Aspose lisansı** edinin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java karmaşık MS Project formüllerini işleyebilir mi?**  
C: Evet, Aspose.Tasks for Java, geniş bir MS Project fonksiyon yelpazesinin değerlendirilmesini destekler ve Java uygulamaları içinde karmaşık hesaplamalara olanak tanır.

**S: Aspose.Tasks for Java farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks for Java, MPP, MPT ve XML formatları dahil olmak üzere çeşitli Microsoft Project dosya sürümlerini destekler.

**S: Aspose.Tasks for Java'ı satın almadan önce deneyebilir miyim?**  
C: Evet, Aspose.Tasks for Java'ın ücretsiz deneme sürümünü [buradan](https://purchase.aspose.com/buy) indirebilirsiniz.

**S: Aspose.Tasks for Java için destek nasıl alınır?**  
C: Aspose.Tasks topluluk forumundan [buradan](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans mevcut mu?**  
C: Evet, test amaçlı bir geçici lisansı Aspose web sitesinden [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç
Bu adımları izleyerek **create project object**, **add extended attribute** ve değerlendirme fonksiyonlarını kullanarak **generate project report** otomatik olarak oluşturmayı öğrendiniz. Artık bu temeli, daha zengin proje analizleri, özel panolar veya otomatik zamanlama araçları geliştirmek için genişletebilirsiniz — tümü Aspose.Tasks for Java tarafından desteklenmektedir.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}