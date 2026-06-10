---
date: 2026-06-10
description: Java'da genişletilmiş öznitelik nasıl oluşturulacağını, bir Microsoft
  Project dosyasını nasıl yükleneceğini, sayısal değerlerin nasıl ayarlanacağını ve
  Aspose.Tasks for Java kullanarak projenin XML olarak nasıl kaydedileceğini öğrenin.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Aspose.Tasks'te Genişletilmiş Kaynak Özniteliklerini Yönet
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Java'da Aspose.Tasks ile genişletilmiş öznitelik nasıl oluşturulur
url: /tr/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Tasks kullanarak genişletilmiş öznitelik oluşturma

## Giriş
Bu uygulamalı rehberde Aspose.Tasks kullanarak bir Microsoft Project dosyası için **Java'da genişletilmiş öznitelik oluşturacaksınız**. Mevcut bir projeyi yüklemeyi, yeni bir sayısal öznitelik tanımlamayı, bir kaynağa değer atamayı ve sonunda değişiklikleri bir XML dosyası olarak kalıcı hale getirmeyi adım adım göstereceğiz. Sonunda, herhangi bir Java tabanlı proje yönetimi çözümüne ekleyebileceğiniz yeniden kullanılabilir bir kod kalıbına sahip olacaksınız.

## Hızlı Yanıtlar
- **Genişletilmiş öznitelik nedir?**  
  Kullanıcı tanımlı bir alan (ör. Yaş, Beceri Seviyesi) ve kaynaklar veya görevler için ekstra veri depolar.  
- **Bunu hangi API oluşturur?**  
  Aspose.Tasks for Java, özel öznitelikleri tanımlamak ve yönetmek için `ExtendedAttributeDefinition` sınıfını sağlar.  
- **Lisans gerekir mi?**  
  Geliştirme için geçici bir değerlendirme lisansı yeterlidir; üretim dağıtımları için tam lisans gereklidir.  
- **Sayısal değerler depolayabilir miyim?**  
  Evet – kesin ondalık değerler atamak için `setNumericValue(BigDecimal)` kullanın.  
- **Değişiklikleri nasıl kalıcı hale getiririm?**  
  `project.save("output.xml", SaveFileFormat.Xml)` çağrısıyla güncellenen projeyi XML formatında kaydedin.

## Özel öznitelik nedir?
**Özel öznitelik** (genişletilmiş öznitelik olarak da bilinir), Microsoft Project'te kaynaklara veya görevlere ekleyebileceğiniz ek bir sütundur. Çalışan yaşı, sertifika seviyesi veya herhangi bir iş‑özel metriği gibi yerleşik alanların kapsamadığı verileri yakalamanızı sağlar.

## Java'da genişletilmiş öznitelik neden oluşturulur?
Java'da genişletilmiş öznitelik oluşturmak, proje verilerini programlı olarak zenginleştirmenizi sağlar, dosyalar arasında tutarlılığı güvence altına alır ve otomatik raporlamayı mümkün kılar. Özniteliği bir kez tanımlayarak, manuel giriş yapmadan herhangi bir sayıda kaynak veya göreve uygulayabilir, zaman tasarrufu sağlar ve hataları azaltırsınız.

- **Verileri kuruluşunuza göre özelleştirin** – size önemli olan herhangi bir metriği manuel Excel çözümleri olmadan depolayın.  
- **Daha zengin raporlamayı etkinleştirin** – özel alanı daha sonra panolar veya analizler için sorgulayın.  
- **Tutarlılığı koruyun** – aynı tanımı programlı olarak onlarca proje boyunca uygulayarak insan hatasını ortadan kaldırın.  
- **Performans testli** – Aspose.Tasks, ürün benchmark'larına göre tüm dosyayı belleğe yüklemeden 10.000 göreve ve 5.000 kaynağa kadar projeleri işler.

## Önkoşullar
1. **Java Development Kit** – JDK 8 veya daha yeni bir sürüm yüklü olmalıdır.  
2. **Aspose.Tasks for Java** – en son sürümü [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – Eclipse, IntelliJ IDEA veya herhangi bir Java uyumlu geliştirme ortamı.  

## Java'da genişletilmiş öznitelik nasıl oluşturulur?
Projenizi yükleyin, özniteliği tanımlayın, bir kaynağa ekleyin ve dosyayı kaydedin – tüm bunlar birkaç basit adımda. Aşağıdaki bölümler her adımı kısa bir açıklama ve gerçek kodunuzun bulunduğu yer tutucu ile ayırır.

### Adım‑Adım Kılavuz

#### Paketleri İçe Aktarın
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` ve ilgili sınıflar `com.aspose.tasks` ad alanında bulunur. Bunları Java dosyanızın en üstüne içe aktarın.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Adım 1: Veri Dizinini Tanımla
`Paths`, platform bağımsız bir şekilde dosya sistemi yolu elde etmek için yöntemler sağlayan bir yardımcı sınıftır.

```java
String dataDir = "Your Data Directory";
```

#### Adım 2: Microsoft Project Dosyasını Yükle
`Project`, bellekte bir Microsoft Project dosyasını temsil eder ve içeriğine okuma‑yazma erişimi sağlar.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Adım 3: Özel Özniteliği Tanımla
`ExtendedAttributeDefinition`, kaynaklara veya görevlere eklenebilen yeni bir özel alanın şemasını tanımlar.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Adım 4: Java'da Sayısal Değeri Ayarla
`ExtendedAttributeResource`, belirli bir kaynak örneği için özel öznitelik değerini tutar.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Adım 5: Kaynak Ekle ve Özel Özniteliği Bağla
`Resource`, bir kişi, ekipman veya malzeme gibi proje kaynağını modelleyen sınıftır.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Adım 6: Projeyi XML Olarak Kaydet
`SaveFileFormat`, XML dahil olmak üzere bir projeyi kaydetmek için desteklenen çıktı formatlarını listeler.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Adım 7: Sonucu Görüntüle
`System.out.println`, standart konsol çıktısına bir metin satırı yazdırır.

```java
System.out.println("Process completed Successfully");
```

## Yaygın Tuzaklar ve İpuçları
- **Öznitelik ID çakışmaları:** Yeni bir tanım oluşturmadan önce her zaman `project.getExtendedAttributes().getById(id)` çağırarak yinelenen kimlikleri önleyin.  
- **Hassasiyet yönetimi:** Raporlamada yuvarlama hatalarını önlemek için `float`/`double` yerine kesin sayısal değerler için `BigDecimal` tercih edin.  
- **Dosya yolu güvenilirliği:** `Paths.get(...).toAbsolutePath()` kullanın veya IDE'nizin çalışma dizinini yapılandırarak `FileNotFoundException` hatasını ortadan kaldırın.  

## Sıkça Sorulan Sorular

**S: Görevler için de özel öznitelikler oluşturabilir miyim?**  
C: Evet – öznitelik şemasını tanımlarken `ExtendedAttributeResource` yerine `ExtendedAttributeTask` kullanın.

**S: Aynı anda birden fazla özel öznitelik eklemek mümkün mü?**  
C: Kesinlikle. Her öznitelik için ayrı `ExtendedAttributeDefinition` nesneleri oluşturun ve istediğiniz kaynaklara veya görevlere ekleyin.

**S: Projeyi hangi formatlarda kaydedebilirim?**  
C: Aspose.Tasks, XML, MPP, PDF, HTML ve 30'dan fazla ek formatı destekler. Bu örnekte `SaveFileFormat.Xml` kullandık.

**S: Geliştirme sürümleri için lisans gerekir mi?**  
C: Test için geçici bir değerlendirme lisansı yeterlidir. Herhangi bir üretim dağıtımı için tam ticari lisans gereklidir.

**S: Daha sonra özel öznitelik değerlerini nasıl okuyabilirim?**  
C: `resource.getExtendedAttributes()` çağırıp koleksiyonu döngüyle gezerek; saklanan değeri `getNumericValue()` veya `getTextValue()` ile alın.

---

**Son Güncelleme:** 2026-06-10  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [Kaynak Oluşturma – Aspose.Tasks for Java ile Kaynak Yönetimi](/tasks/java/resource-management/)
- [Özel Alan Oluşturma – Aspose - Genişletilmiş Öznitelikleri Yönetme](/tasks/java/project-management/extended-attributes/)
- [Proje Oluşturma – Aspose.Tasks ile Yeni Görev Özniteliklerini Ayarlama](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}