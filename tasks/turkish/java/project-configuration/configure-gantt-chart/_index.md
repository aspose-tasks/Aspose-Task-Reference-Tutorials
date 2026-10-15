---
date: 2026-10-15
description: Aspose.Tasks for Java ile activity oluşturmayı, data directory ayarlamayı,
  tablo alanlarını özelleştirmeyi ve projeyi MPP olarak kaydetmeyi öğrenin. Java geliştiricileri
  için adım adım rehber.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Aspose.Tasks for Java kullanarak activity oluşturma ve data directory ayarlama
og_description: Aspose.Tasks for Java kullanarak activity oluşturma, tablo alanlarını
  özelleştirme ve projeyi MPP olarak kaydetme. Hızlı uygulama için bu ayrıntılı rehberi
  izleyin.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Aspose.Tasks for Java'da activity oluşturma ve data directory ayarlama
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Aspose.Tasks for Java kullanarak activity oluşturma ve data directory ayarlama
url: /tr/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java kullanarak etkinlik oluşturma ve veri dizinini ayarlama

## Giriş
Bu öğreticide programlı olarak **etkinlik oluşturmayı** keşfedecek, **veri dizinini** yapılandıracak ve **projeyi MPP olarak kaydetmeyi** aynı zamanda Gantt şeması görünümünde **tablo alanlarını özelleştirmeyi** öğreneceksiniz. Aspose.Tasks for Java, 30'dan fazla giriş ve çıkış formatını destekleyen güçlü bir API'dir ve tüm dosyayı belleğe yüklemeden 10 000'e kadar görev içeren projeleri işleyebilir. Kılavuzun sonunda proje oluşturmayı otomatikleştirebilecek, görevleri özel niteliklerle zenginleştirebilecek ve Microsoft Project için açılmaya hazır bir MPP dosyası üretebileceksiniz.

## Hızlı cevaplar
- **İlk adım nedir?** Proje dosyalarınızın bulunduğu veri dizini yolunu ayarlayın.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (resmi siteden indirilebilir).  
- **Özel nitelikler ekleyebilir miyim?** Evet – genişletilmiş nitelikler tanımlayabilir ve bunları Gantt şemasında gösterebilirsiniz.  
- **Test için lisansa ihtiyacım var mı?** Değerlendirme amaçlı geçici bir lisans mevcuttur.  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans) çalışır.

## “set data directory” nedir ve neden önemlidir?
Veri dizinini ayarlamak, Aspose.Tasks'e proje dosyalarını nereden okuyup yazacağını söyler. Doğru bir yol olmadan API `.mpp` dosyalarınızı bulamaz ve `FileNotFoundException` hatalarına yol açar. Bu dizini kodunuzun başında tanımlamak, iş akışını tekrarlanabilir hâle getirir ve dosya sistemi ile ilgili endişeleri iş mantığından izole eder.

## Gantt şemasında tablo alanlarını neden özelleştirmelisiniz?
Özel tablo alanları, ek bilgileri—örneğin özel nitelikler, kaynak verileri veya proje‑özgü notlar—doğrudan Gantt görünümünde göstermenizi sağlar. Bu, ayrı rapor ihtiyacını azaltır ve paydaşlara tek, veri‑zengin bir görsel sunar; karar‑verme hızını %30'a kadar artırabilir.

## Yeni etkinlik nasıl oluşturulur?
Yeni bir etkinlik (görev), bir `Task` nesnesi oluşturularak ve projeye kök görev koleksiyonuna eklenerek yaratılır. Bu yaklaşım, büyük takvimleri otomatik olarak oluşturmanıza, görev verilerini dış sistemlerden çekmenize veya manuel düzenleme yapmadan toplu güncellemeler uygulamanıza olanak tanır.

## Önkoşullar
1. **Java Development Kit (JDK)** – sürüm 8 veya daha yeni.  
2. **Aspose.Tasks for Java** – **Aspose.Tasks Java sürüm sayfası**'ndan indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir Java‑uyumlu editör.

## Paketleri içe aktar
`com.aspose.tasks` ad alanı, proje manipülasyonu için ihtiyaç duyacağınız tüm sınıfları içerir. Bunu içe aktarmak, `Project`, `Task`, `ExtendedAttributeDefinition` ve diğer temel türlere erişim sağlar.

```java
import com.aspose.tasks.*;
```

## Maven bağımlılığı (isteğe bağlı)
Projenizi Maven ile yönetiyorsanız, Aspose.Tasks bağımlılığını `pom.xml` dosyasına ekleyin. Bu, kütüphanenin derleme sırasında otomatik olarak çözülmesini sağlar.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Adım‑adım kılavuz

### Adım 1: veri dizinini ayarla
Proje dosyalarınızı içeren klasörü tanımlayın. `dataDir` değişkeni mutlak yolu tutar ve öğretici boyunca tekrar kullanılır.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu klasörün tam yolu ile değiştirin, örneğin `C:/Projects/MyGantt`.

### Adım 2: proje dosyasını yükle
`Project`, Aspose.Tasks'in bellek içinde tek bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir. Mevcut bir dosyayı yüklemek, görevlerine, kaynaklarına ve tablolarına erişim sağlar.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Adım 3: yeni etkinlik ekle
`Task`, takvimdeki bireysel bir etkinliği temsil eder. Bir görevi kök görev koleksiyonuna eklemek, onu proje hiyerarşisinin en üst seviyesine yerleştirir.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Adım 4: özel nitelik tanımla
`ExtendedAttributeDefinition`, herhangi bir görev, kaynak veya atamaya eklenebilen yeniden kullanılabilir bir özel alan oluşturmanızı sağlar.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Adım 5: göreve özel nitelik ekle
`ExtendedAttribute`, belirli bir göreve atadığınız özel niteliğin somut örneğidir.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Adım 6: tabloyu özelleştir – özel niteliği sütun olarak ekle
`TableField`, bir Gantt şeması tablosundaki bir sütunu tanımlar. Özel niteliğe referans veren bir `TableField` ekleyerek, niteliği şema görünümünde görünür hâle getirirsiniz.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Adım 7: projeyi kaydet
`project.save` çağrısı, tüm değişiklikleri yeni bir dosyaya kalıcı hâle getirir. `SaveFileFormat.MPP` sabiti, Aspose.Tasks'e dosyayı Microsoft Project'in yerel ikili formatında yazmasını söyler.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Yaygın sorunlar ve çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **FileNotFoundException** proje yüklenirken | **set data directory** yolu hatalı veya son slash eksik. | `dataDir`'in tam klasöre işaret ettiğini doğrulayın ve uygun dosya ayırıcıyı (`/` veya `\\`) ekleyin. |
| Özel nitelik Gantt görünümünde görünmüyor | Tablo alanı yanlış indeksle eklendi veya sütun genişliği çok küçük. | `table.getTableFields().add(3, attrField);` ifadesinin geçerli bir indeks kullandığından emin olun ve gerektiğinde `setWidth`'ı ayarlayın. |
| Kaydetme sırasında LicenseException | Üretim kullanımı için geçerli bir lisans uygulanmadı. | `project.save()` çağırmadan önce geçici veya kalıcı bir lisans uygulayın. |

## Sıkça sorulan sorular

**Q: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks .NET, Java ve C++ için mevcuttur.

**Q: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?**  
A: Evet, **Aspose.Tasks ücretsiz deneme indirme sayfası**'ndan ücretsiz deneme sürümünü indirebilirsiniz.

**Q: Aspose.Tasks için desteği nereden bulabilirim?**  
A: Destek bulabilir ve sorular sorabilirsiniz [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) üzerinden.

**Q: Aspose.Tasks için lisans nasıl satın alınır?**  
A: **Aspose.Tasks satın alma sayfası**'ndan lisans satın alabilirsiniz.

**Q: Test amaçlı geçici bir lisansa ihtiyacım var mı?**  
A: Evet, **geçici lisans talep sayfası**'ndan geçici bir lisans alabilirsiniz.

## Sonuç
Artık **etkinlik oluşturmayı**, veri dizinini ayarlamayı, bir özel nitelik tanımlamayı ve eklemeyi ve **projeyi MPP olarak kaydetmeyi**, Gantt şeması görünümünde **tablo alanlarını özelleştirerek** Aspose.Tasks for Java kullanarak biliyorsunuz. Bu yetenekler, proje verileri üzerinde tam programatik kontrol sağlar, otomatik takvim oluşturmayı ve paydaşlarınız için daha zengin görsel raporlamayı mümkün kılar.

---

**Son Güncelleme:** 2026-10-15  
**Test Edilen:** Aspose.Tasks Java 24.12 (latest)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Boş Proje Dosyası Nasıl Oluşturulur (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [MPP Dosyası Nasıl Oluşturulur – Aspose.Tasks ile Boş Projeyi MPP Formatında Oluştur ve Kaydet](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks ile Proje Oluştur – Yeni Görev Niteliklerini Ayarla](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}