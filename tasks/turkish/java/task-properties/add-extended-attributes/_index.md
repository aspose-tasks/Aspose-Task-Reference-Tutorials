---
date: 2026-09-30
description: Aspose.Tasks for Java kullanarak task extended attribute nasıl oluşturulacağını
  öğrenin, custom task fields eklemek için önde gelen java project management library.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Aspose.Tasks Java ile task extended attribute nasıl oluşturulur
og_description: Aspose.Tasks for Java kullanarak task extended attribute nasıl oluşturulacağını
  öğrenin, custom task fields eklemek için önde gelen java project management library.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Aspose.Tasks Java ile task extended attribute nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Aspose.Tasks Java ile task extended attribute nasıl oluşturulur
url: /tr/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Java ile görev genişletilmiş özniteliği nasıl oluşturulur

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak bir Microsoft Project dosyasında **görev genişletilmiş özniteliği** oluşturmayı öğreneceksiniz. Özel alanlar eklemek, yerleşik sütunlarda yer almayan proje‑özel verileri yakalamanızı sağlar ve raporlama ile kaynak planlaması üzerinde daha ince kontrol sunar. Kılavuzun sonunda, herhangi bir göreve düz‑metin, arama‑etkinleştirilmiş ve süre özniteliklerini ekleyebileceksiniz.

## Hızlı cevaplar
- **“Genişletilmiş öznitelik” ne anlama gelir?** Görev, kaynak veya atamaya ekleyebileceğiniz, tanımladığınız bir özel alandır.  
- **Bu yeteneği hangi kütüphane ekliyor?** Aspose.Tasks for Java, bir java proje yönetimi kütüphanesidir.  
- **Denemek için lisansa ihtiyacım var mı?** Evet – Aspose web sitesinden ücretsiz 30‑günlük bir deneme sürümü mevcuttur.  
- **Arama değerleri ekleyebilir miyim?** Kesinlikle; metin veya süre alanları için izin verilen değerlerin bir listesini sağlayabilirsiniz.  
- **API Java 8 ve sonrası ile uyumlu mu?** Evet, Java 8+ desteklenir ve tüm büyük işletim sistemlerinde çalışır.

## Görev genişletilmiş özniteliği nedir?
Görev genişletilmiş özniteliği, bir Project dosyasındaki her görev için ek bilgi depolayan, kullanıcı‑tanımlı bir sütundur. Yerleşik bir alan gibi davranır ancak metin, sayı, tarih veya süre gibi ihtiyacınız olan herhangi bir veri tipini tutabilir.

## Neden Aspose.Tasks for Java kullanmalısınız?
Aspose.Tasks **50+ dosya formatını** destekler ve **10.000+ görev** içeren projeleri Microsoft Project yüklü olmadan işleyebilir. Kütüphane tamamen çevrim dışı çalışır, veri gizliliğini garanti eder ve kurumsal ölçekli çözümler için deterministik performans sunar.

## Önkoşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- Temel Java programlama bilgisi.  
- Aspose.Tasks for Java kütüphanesi yüklü. [web sitesi](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.  
- Makinenizde bir Java IDE (IntelliJ IDEA, Eclipse veya VS Code) kurulu.

## Paketleri içe aktar
`import` ifadeleri, `Project`, `ExtendedAttributeDefinition` ve `ExtendedAttribute` gibi ihtiyaç duyacağınız temel sınıflara erişim sağlar.  

`Project`, bir Microsoft Project dosyasını temsil eder ve dosyayı okuma, değiştirme ve kaydetme yöntemleri sunar.  
`ExtendedAttributeDefinition`, görevlere, kaynaklara veya atamalara eklenebilen bir özel alanı tanımlar.  
`ExtendedAttribute`, belirli bir varlık için gerçek değeri tutan tanımın bir örneğidir.

## Bir göreve düz metin genişletilmiş özniteliği nasıl eklenir?
Düz metin genişletilmiş özniteliği eklemek için önce projeyi yüklersiniz, ardından Text türünde bir tanım oluşturur, tanımı projenin koleksiyonuna eklersiniz, bir görev oluşturur, tanımdan özniteliği örnekler, metin değerini ayarlarsınız, göreve ekler ve son olarak projeyi kaydedersiniz.

### 1. Belge dizini yolunu ayarla
Kaynak ve çıktı dosyalarınızın bulunduğu yeri belirtin.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Yeni bir proje oluştur
Bir `Project` nesnesi oluşturun, isteğe bağlı olarak mevcut bir .mpp dosyasını yükleyebilirsiniz.

```java
String dataDir = "Your Document Directory";
```

### 3. Text1 türünde bir genişletilmiş öznitelik tanımı oluştur
Özel alanı “Text1” adlı düz metin sütunu olarak tanımlayın.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Tanımı projenin genişletilmiş öznitelikler koleksiyonuna ekle
Projenin tanıyabilmesi için yeni tanımı kaydedin.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Projeye bir görev ekle
Özel alanı alacak bir görev oluşturun.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Öznitelik tanımından bir genişletilmiş öznitelik oluştur
Belirli bir göreve bağlayabileceğiniz bir örnek oluşturun.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Oluşturulan genişletilmiş özniteliğe bir değer ata
Depolamak istediğiniz gerçek metni ayarlayın, ör. “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Genişletilmiş özniteliği göreve ekle
Öznitelik örneğini görevin `ExtendedAttributes` koleksiyonuna ekleyin.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Projeyi kaydet
Güncellenen projeyi istenen formatta diske yazın.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Bir metin özniteliğine arama seçeneği nasıl eklenir?
Arama içeren bir metin özniteliği eklerken, düz‑metin özniteliği için izlediğiniz adımları uygularsınız, ancak tanımı eklemeden önce `LookupValues` koleksiyonunu izin verilen dizelerle doldurursunuz. Bu değerler Microsoft Project içinde bir açılır liste olarak görünür ve veri tutarlılığını sağlar.

## Bir süre özniteliğine arama seçeneği nasıl eklenir?
Süre özniteliği eklemek için tanım oluştururken `Text1` tipini `Duration2` ile değiştirin, ardından `LookupValues` koleksiyonunu “1 day”, “2 days” gibi süre dizeleriyle doldurun. Tanım projeye eklendikten sonra öznitelik örneğini oluşturur, bir süre değeri atar, göreve ekler ve dosyayı kaydedersiniz.

## Yaygın sorunlar ve sorun giderme
- **Arama değerleri görünmüyor** – `project.getExtendedAttributes().add(definition)` çağrısından *önce* her arama girişini `LookupValues` koleksiyonuna eklediğinizden emin olun.  
- **Öznitelik değeri kaydedilmiyor** – Değeri ayarladıktan *sonra* `ExtendedAttribute` örneğini göreve eklediğinizi doğrulayın.  
- **Dosya boyutu beklenmedik şekilde artıyor** – Çok büyük projelerle çalışırken, artımlı kaydetmeyi etkinleştirmek için `project.setSaveOptions(new ProjectSaveOptions())` çağrısını düşünün.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java’yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java, Spring, Hibernate ve Apache POI dahil olmak üzere herhangi bir Java ekosistemiyle sorunsuz bir şekilde bütünleşir.

**S: Aspose.Tasks for Java büyük ölçekli proje yönetimi uygulamaları için uygun mu?**  
C: Kesinlikle. Kütüphane, binlerce görev içeren projeleri işlemek üzere tasarlanmıştır ve bellek kullanımını düşük tutmak için akış (streaming) desteği sunar.

**S: Aspose.Tasks for Java’yı ticari bir projede kullanırken lisansla ilgili hususlar var mı?**  
C: Evet, geçerli bir ticari lisansa ihtiyacınız var. Ayrıntıları [Aspose.Tasks web sitesi](https://purchase.aspose.com/buy) üzerinden inceleyebilirsiniz.

**S: Aspose.Tasks for Java için destek veya yardım nasıl alınır?**  
C: Topluluk yardımı için [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin veya Aspose hesabınız üzerinden bir destek bileti açın.

**S: Aspose.Tasks for Java’yı satın almadan önce deneyebilir miyim?**  
C: Evet, [Aspose.Tasks ücretsiz deneme](https://releases.aspose.com/) sayfasından ücretsiz deneme sürümüne erişebilirsiniz.

---

**Son güncelleme:** 2026-09-30  
**Test edilen sürüm:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## İlgili Eğitimler

- [Java proje yönetiminde özel sütunlar ve genişletilmiş öznitelikler](/tasks/java/project-management/extended-attributes/)
- [Aspose.Tasks for Java ile Genişletilmiş Görev Özniteliklerini Okuma](/tasks/java/task-properties/extended-task-attributes/)
- [Project aspose.tasks – Yeni Görev Öznitelikleri Ayarlama](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}