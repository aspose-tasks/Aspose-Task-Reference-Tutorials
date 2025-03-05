---
title: Aspose.Tasks'ta Taslak Kodların MS Projesinin Toplanması
linktitle: Aspose.Tasks'ta Anahat Kodlarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project taslak kodlarını nasıl toplayacağınızı öğrenin. Bu kapsamlı eğitimde adım adım talimatlar verilmektedir.
type: docs
weight: 11
url: /tr/net/outline-code-page-settings/outline-code-collection/
---
## giriiş
Bu eğitimde Aspose.Tasks for .NET kullanarak Microsoft Project anahat kodlarının nasıl toplanacağını inceleyeceğiz. Netlik ve anlayış sağlamak için süreci adım adım talimatlara ayıracağız.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Visual Studio: Visual Studio'yu sisteminize yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. C# programlamanın temel anlayışı: C#'a aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar
Öncelikle C# projenizdeki Aspose.Tasks işlevselliğine erişmek için gerekli ad alanlarını içe aktarın.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Adım 1: Proje Dosyasını Yükleyin
 kullanarak Microsoft Project dosyasını yükleyerek başlayın.`Project` sınıf.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Adım 2: Anahat Kodlarını Toplayın
Proje görevlerindeki anahat kodlarını toplamak için bir toplayıcı oluşturun.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Adım 3: Görevleri ve Anahat Kodlarını Yineleyin
Toplanan görevleri ve ana hatlarıyla kodları yineleyerek ayrıntılarını yazdırın.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## 4. Adım: Özel Anahat Kodu Tanımını Ekleyin
Projeye özel bir anahat kodu tanımı ekleyin.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Adım 5: Anahat Kodu Oluşturun ve Ekleyin
Bir taslak kodu oluşturun ve onu bir göreve ekleyin.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Adım 6: Anahat Kodlarını Yönetin
Ekleme, çıkarma veya temizleme gibi anahat kodlarını gerektiği gibi değiştirin.
```csharp
// Manipülasyon örneği
// ...
// Kodu 2 doğru konumda olacak şekilde ekleyin
task.OutlineCodes.Insert(2, code2);
// Kodun eklenip eklenmediğini kontrol edin
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak Microsoft Project taslak kodlarını nasıl toplayacağımızı öğrendik. Bu adımları izleyerek projelerinizdeki anahat kodlarını etkili bir şekilde yönetebilir, organizasyonu ve netliği geliştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET öncelikli olarak .NET platformunu hedefler ancak aynı zamanda Aspose.Tasks for Cloud aracılığıyla diğer programlama dilleri için de destek sağlar.
### S: Aspose.Tasks for .NET'in işleyebileceği Proje dosyalarının boyutunda herhangi bir sınırlama var mı?
C: Aspose.Tasks for .NET, büyük Proje dosyalarını verimli bir şekilde işleyebilir ancak performans, dosyanın karmaşıklığına ve boyutuna bağlı olarak değişebilir.
### S: Aspose.Tasks for .NET, Microsoft Project'in en son sürümleriyle uyumlu mu?
C: Evet, Aspose.Tasks for .NET, en yenileri de dahil olmak üzere Microsoft Project'in çeşitli sürümlerini destekler.
### S: Aspose.Tasks for .NET ile çalışırken çıktı formatını özelleştirebilir miyim?
C: Aspose.Tasks for .NET kesinlikle çıktı formatını ihtiyaçlarınıza göre özelleştirmek için kapsamlı seçenekler sunuyor.
### S: Aspose.Tasks for .NET için nerede ek destek veya kaynak bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for .NET ile ilgili her türlü yardım veya sorularınız için.