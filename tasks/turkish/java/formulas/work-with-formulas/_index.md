---
date: 2026-10-05
description: Aspose.Tasks for Java kullanarak test projesi oluşturmayı ve tarihler
  arasındaki günleri hesaplamayı, özel bir alan eklemeyi ve MPP dosyalarını verimli
  bir şekilde yönetmeyi öğrenin.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Aspose.Tasks'te formüllerle çalışın
og_description: Aspose.Tasks for Java kullanarak test projesi oluşturun ve tarihler
  arasındaki günleri hesaplayın. Bu kılavuz, özel bir alan eklemeyi, görev son tarihlerini
  ayarlamayı ve projeyi MPP dosyası olarak kaydetmeyi gösterir.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Test projesi oluşturun ve tarihler arasındaki günleri hesaplayın
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Test projesi oluşturun ve tarihler arasındaki günleri hesaplayın
url: /tr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Test projesi oluşturma ve tarihler arasındaki günleri hesaplama

Bu öğreticide **test projesi oluşturacak** ve **tarihler arasındaki günleri hesaplayacaksınız** özel bir alan ekleyerek, genişletilmiş bir öznitelik tanımlayarak ve Java için Aspose.Tasks kütüphanesi aracılığıyla bir Microsoft Project formülü uygulayarak. Programlama yoluyla takvimler oluşturmanız, son tarihleri hesaplamanız veya raporlamayı otomatikleştirmeniz gerekirse, Aspose.Tasks, masaüstü kurulumu olmadan Project verilerini programlı olarak manipüle etmenizi sağlar, 50+ giriş ve çıkış formatını destekler ve çok sayfalı dosyaları bellek‑verimli modda işler.

## Hızlı yanıtlar
- **Bu öğreticinin kapsamı nedir?** Test projesi oluşturmayı, genişletilmiş bir öznitelik tanımlamayı, bir görev son tarihini ayarlamayı ve tarihler arasındaki günleri hesaplamak için bir formül kullanmayı gösterir.  
- **Hangi kütüphane gereklidir?** Java için Aspose.Tasks (en son sürüm).  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi IDE'yi kullanabilirim?** JDK 8+ destekleyen herhangi bir Java IDE (IntelliJ IDEA, Eclipse, VS Code).  
- **Uygulama ne kadar sürer?** Kodu kopyalayıp çalıştırmak yaklaşık 10‑15 dakika.

## Aspose.Tasks'te “tarihler arasındaki günleri hesaplama” nedir?
In Aspose.Tasks, bir formül, görev alanlarına referans verebilen ve hesaplamalar yapabilen bir dizedir. `[Deadline] - [Finish]` Aspose.Tasks'in iki tarih alanı arasındaki gün farkını sayısal olarak döndürmek için kullandığı formül sözdizimidir. Sonuç, tam günleri temsil eden sayısal bir değer olarak saklanır; bu değeri özel bir alanda görüntüleyebilir veya daha sonraki hesaplamalarda kullanabilirsiniz.

## Tarihler arasındaki günleri hesaplamak için neden Aspose.Tasks kullanılmalı?
Aspose.Tasks, her Project, Task ve Resource özelliği için **tam API kapsamı** sağlar, Windows, Linux ve macOS'ta çalışır ve **Microsoft Project veya Office'in kurulmuş olmasını gerektirmez**. Motor, tipik sunucu donanımında bir saniyeden kısa sürede **500+ görev** içeren projeleri işleyebilir; bu da CI boru hatları, Docker konteynerleri ve yüksek hacimli toplu işleme için idealdir.

## Bir görev için son tarih nasıl ayarlanır
java.util.Calendar, belirli bir anı temsil eden bir Java sınıfıdır. Bir göreve son tarih atamak için `java.util.Calendar` değerini görevin `Tsk.DEADLINE` alanına atarsınız. Calendar örneğini oluşturduktan sonra, yıl, ay ve günü istenen son tarihe ayarlayın, ardından `task.set(Tsk.DEADLINE, calendar);` metodunu çağırın. Son tarih proje dosyasında saklanır ve `[Deadline] - [Finish]` gibi formüllerde kullanılabilir.

## Genişletilmiş öznitelik nasıl tanımlanır
Genişletilmiş bir öznitelik, formülünüzün sonucunu saklayan bir özel alandır. Bunu bir kez oluşturur, dostça bir takma ad verirsiniz ve `[Deadline] - [Finish]` ifadesini ekleyerek her görevin aralığı otomatik olarak hesaplamasını sağlarsınız. `ExtendedAttribute` örneği oluşturarak, Alias'ini ayarlayarak, formülü atayarak ve projeye ekleyerek oluşturabilirsiniz.

## Önkoşullar
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – Oracle web sitesinden indirin veya OpenJDK'yi benimseyin.  
- **Aspose.Tasks for Java** – en son JAR dosyasını [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) edinin ve projenizin sınıf yoluna veya Maven/Gradle bağımlılıklarına ekleyin.

## Paketleri içe aktar
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Adım adım kılavuz

### Adım 1: Özel alanlı bir test projesi oluşturma
Öncelikle **bir test projesi oluşturuyoruz** ve daha sonra formül sonucunu tutacak bir özel alan ekliyoruz.

```java
Project project = CreateTestProjectWithCustomField();
```

> *İpucu:* `CreateTestProjectWithCustomField()` formül ataması için hazır bir genişletilmiş öznitelik oluşturan ve minimal bir takvim inşa eden yardımcı bir yöntemdir.

### Adım 2: Genişletilmiş öznitelik tanımlama (özel alan ekleme)
Sonra **genişletilmiş bir öznitelik tanımlıyoruz** – temelde özel alan – ve ona dostça bir takma ad veriyoruz. İşte **özel alan** mantığını eklediğimiz yer.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias**, alanı Project içinde okunabilir kılar.  
- **Formula**, bir görevin *Finish* tarih ile *Deadline* tarihi arasındaki gün sayısını hesaplar – *tarihler arasındaki günleri hesaplama*'nın çekirdeği.

### Adım 3: Bir görev için son tarih ayarlama (son tarih görevi ekle & görev son tarihini ayarla)
Şimdi belirli bir göreve *Deadline* özelliğini ayarlayarak **son tarih görevi** verisini ekliyoruz.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` örneği tam son tarih anını tanımlar.  
- `set(Tsk.DEADLINE, …)` **seçilen görev için görev son tarihini ayarlar**.

### Adım 4: Projeyi kaydetme (Microsoft Project dosyasını manipüle etme)
Son olarak, değişiklikleri bir MPP dosyasına kaydederek **Microsoft Project'i manipüle ediyoruz**.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp` dosyasını Microsoft Project'te açarak özel alanı, formül sonucunu ve son tarihi takvimde görebilirsiniz.

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|-------|----------|
| **Formül değerlendirilemiyor** | Özniteliğin `Formula` dizesinin doğru alan adlarını (ör. `[Deadline]`, `[Finish]`) kullandığından emin olun. |
| **Görev bulunamadı** | Görev kimliğinin (`örnekte 1`) mevcut olduğunu doğrulayın; hata ayıklamak için `project.getRootTask().getChildren().size()` kullanın. |
| **Lisans istisnası** | Herhangi bir API metodunu çağırmadan önce geçerli bir Aspose.Tasks lisansı uygulayın (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Sıkça sorulan sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, Java ve diğer platformlar için API'ler sunar; böylece Microsoft Project dosyalarını tercih ettiğiniz dilde manipüle edebilirsiniz.

**S: Aspose.Tasks için ücretsiz deneme mevcut mu?**  
C: Kesinlikle. Tam işlevsel bir denemeyi [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için ayrıntılı belgeleri nerede bulabilirim?**  
C: Resmi belgeler [Aspose.Tasks Java API Referansı](https://reference.aspose.com/tasks/java/) adresinde barındırılmaktadır.

**S: Aspose.Tasks için destek nasıl alabilirim?**  
C: Toplulukla sorularınızı paylaşmak ve deneyimlerinizi aktarmak için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**S: Değerlendirme için geçici bir lisansa ihtiyacım var mı?**  
C: Kısa vadeli testler için geçici bir lisans mevcuttur; bunu [geçici lisans talep sayfasından](https://purchase.aspose.com/temporary-license/) isteyebilirsiniz.

---

**Son Güncelleme:** 2026-10-05  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [MPP Dosyası Oluşturma – Aspose.Tasks ile Boş Proje Oluşturma ve MPP Formatında Kaydetme](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java kullanarak MS Project'te Proje Başlangıç Tarihini Ayarlama](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks ile Java'da Genişletilmiş Öznitelik Oluşturma](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}