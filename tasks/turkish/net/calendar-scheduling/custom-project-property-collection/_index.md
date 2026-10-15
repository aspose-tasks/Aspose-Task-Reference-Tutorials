---
date: 2026-10-15
description: Aspose.Tasks for .NET'te özel özellik eklemeyi ve özel proje özelliklerini
  yönetmeyi öğrenin, proje meta verisi kontrolünüzü artırın.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Aspose.Tasks'te Özel Proje Özellikleri Koleksiyonunu Yönetme
og_description: Aspose.Tasks for .NET ile proje dosyalarınıza özel özellik ekleyin.
  Bu kılavuz, özel özellikleri nasıl yöneteceğinizi, okuyacağınızı ve boolean ya da
  string değerlerini verimli bir şekilde ekleyeceğinizi gösterir.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Projeler için Aspose.Tasks .NET API'sı ile Özel Özellik Ekleyin
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Aspose.Tasks for .NET'te Özel Özellik Nasıl Eklenir
url: /tr/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET'te özel özellik ekleme

## Giriş

Özel özellik desteği, yerleşik alanların kapsamadığı proje‑özel meta verileri depolamanızı sağlar. Bu öğreticide **özel özellik eklemeyi**, geri okumayı ve Aspose.Tasks for .NET kullanarak tüm özel özellik koleksiyonunu yönetmeyi öğreneceksiniz. Sonunda, iş kurallarınıza uygun Boolean, DateTime, Double ve String değerleriyle proje dosyalarını özelleştirebileceksiniz.

## Hızlı cevaplar
- **Boolean bir özel özellik ekleyebilir miyim?** Evet – `CustomPropertyType.Boolean` kullanın.
- **Kaç tane özel özellik türü destekleniyor?** Dört: Boolean, DateTime, Double, String.
- **Özel özellik koleksiyonu yalnızca okunabilir mi?** Proje yalnızca okunabilir bir kaynaktan yüklendiyse koleksiyon yalnızca okunabilir olabilir.
- **Bu özelliği kullanmak için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.
- **Hangi .NET sürümleri uyumludur?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Özel özellik nedir?

Özel özellik, bir Project nesnesine eklediğiniz kullanıcı tanımlı bir meta veri alanıdır. “Risk Seviyesi”, “Müşteri ID” gibi ek bilgiler veya standart MS‑Project alanlarının kapsamadığı herhangi bir Boolean işareti gibi verileri depolamanızı sağlar.

## Aspose.Tasks'te neden özel özellik eklenir?

Aspose.Tasks, **50+ giriş ve çıkış formatını** destekler ve **10.000'e kadar görev** içeren projeleri tüm dosyayı belleğe yüklemeden işleyebilir. Özel özellikler eklemek, iş açısından kritik verileri doğrudan proje dosyasına gömmenizi sağlar, harici veritabanı ihtiyacını ortadan kaldırır ve verinin proje ile birlikte taşınmasını garantiler.

## Önkoşullar

- İş istasyonunuzda yüklü Visual Studio (herhangi bir yeni sürüm).
- Aspose.Tasks for .NET – [download link](https://releases.aspose.com/tasks/net/) adresinden indirin.
- C# sözdizimi ve .NET proje yapısı hakkında temel bilgi.

## Ad alanlarını içe aktar

Aşağıdaki ad alanları, temel proje modeline ve özel özellik API'lerine erişim sağlar.

```csharp
using Aspose.Tasks;
using System;


```

## Aspose.Tasks'te özel özellik nasıl eklenir?

Özel bir özellik eklemek için önce projeyi yükleyin, ardından bir `CustomProperty` nesnesi oluşturun, adını, tipini ve değerini ayarlayın ve son olarak projeye ait `CustomProperties` koleksiyonuna ekleyin. Bu işlem meta veriyi doğrudan proje dosyasına gömer ve değişiklikler `project.Save(...)` çağrıldığında kaydedilir.  
`CustomProperty`, bir projeye eklenen tek bir kullanıcı tanımlı alanı temsil eder.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Adım 1: projeyi başlat

`Project`, Aspose.Tasks içinde bir proje dosyasını temsil eden temel sınıftır.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Adım 2: özel özellik koleksiyonunun hazır olup olmadığını kontrol et

`CustomProperties`, bir proje için tüm özel özellik nesnelerini tutan koleksiyondur.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Adım 3: özel özellik ekle

`Add` metodu, projeye yeni bir özel özellik ekler.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Adım 4: özel özelliklere eriş

`CustomProperties` koleksiyonu IEnumerable arayüzünü uygular, böylece her bir `CustomProperty` üzerinde döngü yapılabilir.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Adım 5: bir özel özelliğin değerini al

`Get` metodu, bir özel özelliğin adını vererek değerini döndürür.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Adım 6: özel özellik adları üzerinde döngü

`Names` özelliği, koleksiyondaki tüm özel özellik adlarının bir listesini sağlar.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Adım 7: özel özellikleri kaldır veya temizle

`Remove` metodu belirli bir özelliği siler, `Clear` ise tüm koleksiyonu boşaltır.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Yaygın tuzaklar ve sorun giderme

- **Yalnızca okunabilir koleksiyon** – `project.CustomProperties.IsReadOnly` `true` dönerse, kaynak dosyanın yalnızca okuma erişimiyle açılmadığından emin olun veya düzenlemeden önce yazılabilir bir konuma kopyalayın.  
- **Tip uyuşmazlığı** – Bildirilen `CustomPropertyType` ile eşleşmeyen bir değer atandığında `ArgumentException` fırlatılır. Her zaman doğru `Type` tanımlandıktan sonra `Value`'yu ayarlayın.  
- **Değişiklikleri kaydetme** – Özellik ekleyip/çıkarınca, değişiklikleri kalıcı hale getirmek için `project.Save("output.mpp")` çağırın; aksi takdirde değişiklikler sadece bellekte kalır.

## Sıkça sorulan sorular

**S: Aspose.Tasks for .NET kullanarak projemde herhangi bir veri tipinde özel özellik ekleyebilir miyim?**  
C: Evet, Boolean, DateTime, Double ve String tiplerini destekleyen özel özellikler ekleyebilirsiniz.

**S: Aspose.Tasks for .NET içinde özel özellik adları üzerinde döngü yapmak mümkün mü?**  
C: Kesinlikle, `Names` özelliğini kullanarak özel özellik adları üzerinde döngü yapabilirsiniz.

**S: Projemden belirli bir özel özelliği nasıl kaldırabilirim?**  
C: `Remove` metodunu kullanarak özelliği adını vererek kaldırabilirsiniz.

**S: Aspose.Tasks for .NET geçici lisansları destekliyor mu?**  
C: Evet, değerlendirme amaçlı Aspose web sitesinden geçici bir lisans alabilirsiniz.

**S: Aspose.Tasks for .NET ile ilgili destek veya ek yardım nereden bulunabilir?**  
C: Herhangi bir sorunuz veya yardıma ihtiyacınız olduğunda Aspose.Tasks forumunu ziyaret edebilirsiniz: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Son Güncelleme:** 2026-10-15  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for .NET kullanarak yerleşik proje özelliklerini nasıl okuyabilirsiniz](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Aspose.Tasks içinde MS Project Öznitelik Koleksiyonunu Yönetme](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks Özel Alan Türleri – Takvim ve Zamanlama](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}