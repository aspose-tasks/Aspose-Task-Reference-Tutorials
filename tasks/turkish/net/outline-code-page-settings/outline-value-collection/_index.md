---
title: Aspose.Tasks ile MS Project Outline Değerlerini Yönetin
linktitle: Aspose.Tasks'ta Anahat Değerlerinin Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarındaki anahat değerlerini nasıl yöneteceğinizi öğrenin. Kod örnekleriyle adım adım eğitim.
weight: 17
url: /tr/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MS Project Outline Değerlerini Yönetin

## giriiş
Aspose.Tasks for .NET, Microsoft Project dosyalarıyla etkileşim kurmak için kapsamlı bir dizi özellik sunar. Bu özelliklerden biri, bir proje içindeki anahat değerlerini yönetme yeteneğidir. Bu eğitimde Aspose.Tasks for .NET'i kullanarak anahat değerlerinin nasıl toplanıp değiştirileceğini inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Kütüphaneyi şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir IDE'nin kurulu olduğundan emin olun.
3. Temel C# Bilgisi: C# programlama diline aşina olmak faydalı olacaktır.
## Ad Alanlarını İçe Aktar
Aspose.Tasks sınıflarına ve yöntemlerine erişmek için C# kod dosyanıza gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Tasks;
using System;

```
Sağlanan örneği birden çok adıma ayıralım:
## Adım 1: Proje Dosyasını Yükleyin
 İlk olarak, bir başlat`Project` Mevcut bir Microsoft Project dosyasını yükleyerek nesne:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Adım 2: Mevcut Anahat Değerlerini Temizleyin
Daha sonra projedeki mevcut anahat değerlerini temizleyin:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## 3. Adım: Yeni Anahat Kodunu Tanımlayın
Şimdi bir açıklama ve değerle yeni bir taslak kodu tanımlayın:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## 4. Adım: Anahat Değerini Güncelleyin
Anahat kodunun değerini güncelleyin:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Adım 5: Anahat Değerleri Üzerinde Yineleme Yapın
Anahat değerlerini yineleyin ve ayrıntılarını yazdırın:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Adım 6: Anahat Değerlerini Yönetin
Gerektiğinde anahat değerlerini kaldırma, ekleme ve kopyalama gibi işlemleri gerçekleştirin:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Çözüm
Bu eğitimde Aspose.Tasks for .NET kullanarak Microsoft Project dosyalarındaki anahat değerleriyle nasıl çalışılacağını öğrendik. Sağlanan adımları izleyerek projelerinizdeki anahat değerlerini verimli bir şekilde yönetebilir, daha fazla kontrol ve esneklik sağlayabilirsiniz.
## SSS'ler
### S: Birden fazla anahat kodunu aynı anda işleyebilir miyim?
C: Evet, Aspose.Tasks'ı kullanarak bir proje içinde birden fazla taslak kodu tanımlayabilir ve değiştirebilirsiniz.
### S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, MPP ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S: Anahat değerleriyle çalışırken hataları nasıl halledebilirim?
C: İstisnaları düzgün bir şekilde yönetmek için try-catch blokları gibi hata işleme mekanizmalarını uygulayabilirsiniz.
### S: Projemdeki anahat değerlerinin görünümünü özelleştirebilir miyim?
C: Evet, Aspose.Tasks, anahat değerlerinin görünümünü ve davranışını gereksinimlerinize göre özelleştirmeniz için kapsamlı API'ler sağlar.
### S: Aspose.Tasks için ek kaynakları ve desteği nerede bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği için ve keşfetmek için[dokümantasyon](https://reference.aspose.com/tasks/net/) API'ler ve özellikler hakkında ayrıntılı bilgi için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
