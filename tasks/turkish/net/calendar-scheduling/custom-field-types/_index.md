---
date: 2026-07-19
description: Aspose.Tasks for .NET'te özel alan türlerini eklemeyi, adım adım kod,
  ön koşullar ve SSS ile öğrenin.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks'te Özel Alan Türleri
og_description: Aspose.Tasks for .NET'te özel alan türlerini eklemeyi öğrenin. Bu
  adım adım kılavuzu izleyerek extended attributes'ı verimli bir şekilde oluşturun,
  tanımlayın ve kullanın.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Aspose.Tasks for .NET'te Özel Alan Türlerini Nasıl Eklenir
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Aspose.Tasks for .NET'te Özel Alan Türlerini Nasıl Eklenir
url: /tr/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Özel Alan Türleri Nasıl Eklenir

## Giriş

Bu öğreticide Aspose.Tasks for .NET kullanarak bir Microsoft Project dosyasına **custom field** türlerini nasıl ekleyeceğinizi keşfedeceksiniz. Custom field'lar, risk puanları, departman kodları veya özel notlar gibi ek bilgileri doğrudan görevlerde, kaynaklarda veya projenin kendisinde depolamanızı sağlar. Ortamı kurmaktan tanımlamaya, eklemeye ve bir custom text alanını doğrulamaya kadar tüm süreci adım adım göstereceğiz.

## Hızlı Yanıtlar
- **What is a custom field?** Kullanıcı tanımlı bir sütundur ve görevlerde/kaynaklarda metin, sayı, tarih veya işaretçi tutabilir.  
- **Which class defines a custom field?** `ExtendedAttributeDefinition`.  
- **Can I add a custom field to an existing project?** Evet—projeyi yükleyin, tanımı oluşturun ve ardından koleksiyona ekleyin.  
- **Do I need a license for Aspose.Tasks?** Üretim için bir lisans gerekir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Tasks'te “custom field ekleme” nedir?
**How to add custom field** terimi, bir `ExtendedAttributeDefinition` oluşturup bunu bir projenin `ExtendedAttributes` koleksiyonuna ekleme sürecini ifade eder. Bu, standart Project şemasının bir parçası olmayan ekstra meta verileri depolamanızı sağlar. Görevler, kaynaklar veya proje için kullanılabilir ve risk seviyeleri, departman kodları veya varsayılan alanlarda bulunmayan özel notlar gibi bilgileri yakalamanıza olanak tanır.

## Proje yönetiminde custom field'lar neden kullanılır?
Aspose.Tasks **50+ yerleşik genişletilmiş nitelik türü** sunar ve dosya boyutunu önemli ölçüde etkilemeden **istediğiniz sayıda custom field** tanımlamanıza izin verir. Custom field'lar sayesinde:
- Bu alanlar Microsoft Project'te ek sütunlar olarak görünür ve formüllerde, raporlarda ve filtrelerde kullanılabilir.
- Proje dosyasının içinde saklanır ve dosyayla birlikte taşınır, böylece downstream araçlar da özel verileri korur.

## Önkoşullar

### 1. Visual Studio Kurulu
Visual Studio'nun (2019 veya daha yeni) makinenizde kurulu olduğundan emin olun. Microsoft web sitesinden indirebilirsiniz.

### 2. Aspose.Tasks for .NET
Aspose.Tasks NuGet paketini projenize ekleyin. En son sürümü [buradan](https://releases.aspose.com/tasks/net/) indirebilirsiniz.

### 3. Temel C# Bilgisi
C# sözdizimi, sınıflar ve .NET proje yapısı konusunda rahat olmalısınız.

## Ad Alanlarını İçe Aktarma

`Project`, `ExtendedAttributeDefinition` ve ilgili enum'lar `Aspose.Tasks` ad alanında bulunur. Dosyanızın en üstüne ekleyin:

`Aspose.Tasks` ad alanı Microsoft Project dosyalarını işlemek için gerekli tüm temel tipleri sağlar.

```csharp

```

## Bir projeye custom field nasıl eklenir?

Mevcut projeyi yükleyin, bir custom field tanımı oluşturun ve bunu projenin genişletilmiş nitelikler koleksiyonuna ekleyin—tam üç adımda. Bu desen görevler, kaynaklar ve proje için çalışır ve dosyayı kaydettiğinizde custom field'ın kalıcı olmasını sağlar.

### Adım 1: Project Nesnesi Oluşturma
`Project`, Aspose.Tasks'in bellek içinde tek bir Project dosyasını temsil eden üst‑seviye nesnesidir. Oluşturulduğunda dosya yüklenir ve görevler, kaynaklar ve genişletilmiş niteliklere erişim sağlanır.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Adım 2: Custom Field Tanımlama
`ExtendedAttributeDefinition` yeni bir sütunu tanımlar. Bu örnekte görevler için **Text** tipinde bir custom field oluşturuyor ve takma adını “MyText” olarak belirliyoruz. `ExtendedAttributeTask.Text1` enum değeri, Aspose.Tasks'in değeri nerede saklayacağını belirtir.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Adım 3: Custom Field Tanımını Projeye Ekleme
Projenin `ExtendedAttributes` koleksiyonu tüm custom field tanımlarını tutar. Tanımı eklemek, projenin her görevi için kullanılabilir olmasını sağlar.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Yaygın Sorunlar ve Çözümler
- **Field not appearing in MS Project UI** – `Alias` özelliğini ayarladığınızdan emin olun; MS Project alias'ı sütun başlığı olarak gösterir.  
- **Saving throws an exception** – Proje dosyasının salt okunur olmadığını ve geçerli bir lisansınız olduğunu doğrulayın.  
- **Custom field values are lost after reload** – Görevlere değer atadıktan sonra `project.Save("output.mpp")` çağrısını yaptığınızdan emin olun.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks'i diğer .NET framework'leriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks .NET Framework, .NET Core ve .NET 5/6/7 ile çalışır.

**Q: Aspose.Tasks kurumsal düzey uygulamalar için uygun mu?**  
A: Kesinlikle. **10.000 göreve kadar** projeleri işleyebilir ve çok iş parçacıklı sunucu ortamlarında çalışabilir.

**Q: Aspose.Tasks birden fazla proje dosyası formatını destekliyor mu?**  
A: Evet—Aspose.Tasks MPP, XML, HTML ve CSV formatlarını okuyup yazar, **tüm ana Microsoft Project sürümlerini** kapsar.

**Q: Aspose.Tasks ile kaynak verilerini manipüle edebilir miyim?**  
A: Evet, kaynakları ekleyebilir, güncelleyebilir ve silebilir, ayrıca onlara custom field atayabilirsiniz.

**Q: Aspose.Tasks kullanıcıları için bir topluluk forumu var mı?**  
A: Evet, diğer kullanıcılarla etkileşime geçmek ve Aspose ekibinden destek almak için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**Son Güncelleme:** 2026-07-19  
**Test Edilen:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks'te MS Project için Genişletilmiş Nitelik Tanımlarını Öğren](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Aspose.Tasks ile MS Project Genişletilmiş Niteliklerini Manipüle Et](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks'te Field Helper MS Project Entegrasyonu](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}