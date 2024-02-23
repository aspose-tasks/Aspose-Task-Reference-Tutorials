---
title: Aspose.Tasks for .NET'te Tablo Alanı Koleksiyonlarında Uzmanlaşma
linktitle: Aspose.Tasks'ta Tablo Alanlarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile proje yönetiminin dinamik dünyasını keşfedin. Özelleştirilmiş bir proje deneyimi için tablo alanı koleksiyonlarını nasıl değiştireceğinizi öğrenin.
type: docs
weight: 13
url: /tr/net/task-table-management/table-field-collection/
---
## giriiş
Aspose.Tasks for .NET, Microsoft Project dosyalarıyla çalışmak için kapsamlı işlevsellik sağlayarak proje yönetimini kolaylaştıran güçlü bir kütüphanedir. Bu derste Aspose.Tasks'taki tablo alanları koleksiyonunu derinlemesine inceleyeceğiz ve bunları C# kullanarak verimli bir şekilde nasıl değiştirip yönetebileceğimizi keşfedeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki kurulumlara sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi.
- Aspose.Tasks for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
- Visual Studio gibi bir Entegre Geliştirme Ortamı (IDE).
## Ad Alanlarını İçe Aktar
Öncelikle, C# dosyanızın başında gerekli ad alanlarının içe aktarıldığından emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Şimdi, adım adım kılavuz formatında her örneği birden çok adıma ayıralım.
## 1. Adım: Belge Dizinini Ayarlayın
Proje dosyanızın bulunduğu belge dizininizin yolunu ayarlayın.
```csharp
String DataDir = "Your Document Directory";
```
## Adım 2: Proje Dosyasını Yükleyin
Aspose.Tasks kütüphanesini kullanarak proje dosyasını yükleyin.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## Adım 3: Tablo Alanları Üzerinde Yineleme Yapın
Proje içindeki tablo alanları üzerinde yineleme yapın.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    // tablo alanları üzerinde yineleme
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## 4. Adım: Yeni Bir Tablo Alanı Ekleme
Mevcut tabloya yeni bir tablo alanı ekleyin.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## Adım 5: Yeni Bir Alan Ekleme
Tablo içinde belirli bir konuma yeni bir alan ekleyin.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## Adım 6: Yeni Tablo Alanını Düzenleyin
Dizin erişimini kullanarak yeni eklenen tablo alanını düzenleyin.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## Adım 7: Alanı Kaldır
Tablo alanlarını tek tek kaldırın veya koleksiyonun tamamını temizleyin.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// Alanı kaldır
table.TableFields.RemoveAt(idx);
```
## Adım 8: Koleksiyonu Temizleyin
Tablo alanı koleksiyonunu tek tek veya tamamen temizleyin.
```csharp
if (deleteOneByOne)
{
    // Tek tek kaldır
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // Koleksiyonu tamamen temizle
    table.TableFields.Clear();
}
```
Artık Aspose.Tasks for .NET'teki tablo alanları koleksiyonunu başarıyla keşfettiniz ve bunları proje gereksinimlerinize göre yönetmenize ve değiştirmenize olanak sağladınız.
## Çözüm
Sonuç olarak, Aspose.Tasks for .NET'te tablo alanı koleksiyonlarıyla nasıl çalışılacağını anlamak, verimli proje yönetimi ve özelleştirme olanaklarının kapısını açar. Aspose.Tasks'ın sağladığı esneklik sayesinde geliştiriciler, uygulamalarını belirli proje ihtiyaçlarını sorunsuz bir şekilde karşılayacak şekilde uyarlayabilirler.
## Sıkça Sorulan Sorular
### Aspose.Tasks for .NET'i Microsoft Project dosyalarının herhangi bir sürümüyle kullanabilir miyim?
Evet, Aspose.Tasks, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek uyumluluk ve esneklik sağlar.
### Çalışma zamanı sırasında tablo alanlarını dinamik olarak oluşturmak ve değiştirmek mümkün müdür?
Kesinlikle! Öğreticide gösterildiği gibi tablo alanlarını dinamik olarak gerektiği gibi ekleyebilir, düzenleyebilir ve kaldırabilirsiniz.
### Aspose.Tasks for .NET'i ticari bir projede kullanmak için herhangi bir lisanslama hususu var mı?
 Evet, Aspose.Tasks for .NET'i ticari bir projede kullanmak için geçerli bir lisansa ihtiyacınız var. Lisans alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### Aspose.Tasks for .NET ile ilgili nasıl destek alabilirim veya yardım isteyebilirim?
 ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) destek almak, sorular sormak ve toplulukla işbirliği yapmak için.
### Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Tasks for .NET'in özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. İndir[Burada](https://releases.aspose.com/).