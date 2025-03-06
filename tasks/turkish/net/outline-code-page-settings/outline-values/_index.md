---
title: Aspose.Tasks ile MS Project Outline Değerlerinde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Anahat Değerlerini Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project anahat değerlerini verimli bir şekilde nasıl yöneteceğinizi öğrenin. Proje ana hatlarını kolaylıkla özelleştirin.
weight: 16
url: /tr/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MS Project Outline Değerlerinde Uzmanlaşmak

## giriiş
Bu eğitimde, .NET için Aspose.Tasks kitaplığını kullanarak Microsoft Project anahat değerlerinin nasıl yönetileceğini inceleyeceğiz. Aspose.Tasks ile anahat kodlarını kolayca değiştirebilir, yeni anahat değerleri oluşturabilir ve proje ana hatlarını gereksinimlerinize göre özelleştirebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET kütüphanesini şuradan indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: .NET framework uyumluluğuna sahip Visual Studio gibi bir geliştirme ortamı kurduğunuzdan emin olun.
3. C# Programlamanın Temel Anlayışı: Aspose.Tasks kütüphanesiyle çalışmak için C# kullanacağımız için C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# kodunuza aktararak başlayın:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Adım 1: Proje Dosyasını Yükleyin
```csharp
// Belgeler dizininin yolu.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Bu adım, yeni bir Project nesnesini başlatır ve Microsoft Project dosyasını belirtilen dizinden yükler.
## Adım 2: Anahat Kodu Tanımlarını Tanımlayın
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Burada iki OutlineCodeDefinition nesnesi tanımlayıp bunları projenin OutlineCodes koleksiyonuna ekliyoruz.
## 3. Adım: Anahat Maskesini Tanımlayın
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Bu adım, anahat kodu tanımı için bir OutlineMask oluşturur.
## Adım 4: Anahat Değerleri Oluşturun
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Bu adımda iki OutlineValue nesnesi oluşturup bunların değer, değer kimliği, tür, açıklama ve çökme durumu gibi özelliklerini ayarlıyoruz.

## Çözüm
Aspose.Tasks for .NET'i kullanarak MS Project anahat değerlerini yönetmek, sağlanan işlevler sayesinde basittir. Bu öğreticide özetlenen adımları izleyerek, proje ana hatlarını ihtiyaçlarınıza göre özelleştirmek için ana hat kodlarını ve değerlerini verimli bir şekilde değiştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks'ı diğer .NET çerçeveleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks çeşitli .NET çerçeveleriyle uyumludur ve geliştirme ortamınızda esneklik sağlar.
### S: Aspose.Tasks'ın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nasıl destek alabilirim?
 C: Destek ve yardım için Aspose.Tasks forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için geçici lisans satın alabilir miyim?
C: Evet, Aspose.Tasks için geçici lisansı şu adresten satın alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks için ayrıntılı belgeleri nerede bulabilirim?
 C: Mevcut kapsamlı belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
