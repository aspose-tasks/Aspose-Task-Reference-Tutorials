---
title: Aspose.Tasks'ta MS Project Anahat Kodu İşleme Tanımları
linktitle: Aspose.Tasks'ta Anahat Kodu Tanımlarını İşleme
second_title: Aspose.Tasks .NET API'si
description: Proje yönetimi uygulamalarınızı güçlendiren Aspose.Tasks for .NET'i kullanarak MS Project anahat kod tanımlarını nasıl kullanacağınızı öğrenin.
type: docs
weight: 12
url: /tr/net/outline-code-page-settings/outline-code-definitions/
---
## giriiş
Microsoft Project, projeleri yönetmek için güçlü bir araçtır ve Aspose.Tasks for .NET, proje dosyalarının programlı olarak işlenmesi için kapsamlı destek sağlar. Proje yönetiminin önemli bir yönü, taslak kodları kullanarak görevleri organize etmektir. Bu eğitimde, Aspose.Tasks for .NET kullanarak MS Project anahat kodu tanımlarının nasıl ele alınacağını keşfedeceğiz.
## Önkoşullar
Uygulamaya geçmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. Aspose.Tasks for .NET'in Kurulumu
 Aspose.Tasks for .NET'i geliştirme ortamınıza yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
### 2. C# ve .NET Framework'ün Temel Anlayışı
Bu eğitim orta düzeyde C# bilgisi gerektirdiğinden, C# programlama dili ve .NET çerçevesi hakkında bilgi edinin.
### 3. Entegre Geliştirme Ortamı (IDE)
Kodlama ve hata ayıklama için sisteminizde Visual Studio gibi bir IDE yüklü olsun.
## Ad Alanlarını İçe Aktar
Kodlamaya başlamadan önce Aspose.Tasks for .NET ile çalışmak için gerekli ad alanlarını içe aktaralım.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Şimdi, daha net bir anlayış için verilen örneği birden çok adıma ayıralım.
## Adım 1: Proje Dosyasını Yükleyin
Öncelikle MS Project dosyasını uygulamamıza yüklememiz gerekiyor.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Adım 2: Anahat Kodu Tanımı Oluşturun
Şimdi yeni bir anahat kodu tanımı oluşturalım.
```csharp
var outline = new OutlineCodeDefinition();
```
## 3. Adım: Alan Numarasını ve Adını Ayarlayın
Anahat kodu için alan numarasını ve adını ayarlayın.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## 4. Adım: GUID'i ve Diğer Özellikleri Ayarlayın
Anahat kodunun GUID'sini ve diğer özelliklerini ayarlayın.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Adım 5: Anahat Maskesi Ekle
Anahat koduna bir anahat maskesi ekleyin.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Adım 6: Diğer Özellikleri Ayarlayın
Anahat kodunun ek özelliklerini ayarlayın.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Adım 7: Anahat Değeri Ekleyin
Son olarak anahat koduna bir anahat değeri ekleyelim.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Çözüm
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak MS Project anahat kodu tanımlarını nasıl ele alacağımızı öğrendik. Adım adım kılavuzu izleyerek proje dosyalarınızdaki anahat kodlarını programlı olarak verimli bir şekilde değiştirebilirsiniz.
## SSS'ler
### S1: Aspose.Tasks for .NET'i MS Project dosyalarının farklı sürümleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, MPP ve XML formatları da dahil olmak üzere MS Project dosyalarının çeşitli sürümlerini destekler.
### S2: Aspose.Tasks for .NET, .NET Core ile uyumlu mu?
C: Evet, Aspose.Tasks for .NET, .NET Core ile uyumludur ve platformlar arası uygulamalar geliştirmenize olanak tanır.
### S3: Aspose.Tasks for .NET'i kullanarak kaynak atamalarını değiştirebilir miyim?
C: Evet, Aspose.Tasks for .NET, kaynak atamalarını yönetmek için atama ekleme, güncelleme ve kaldırma gibi kapsamlı özellikler sağlar.
### S4: Aspose.Tasks for .NET, MS Project dosyalarından özel alanların okunmasını destekliyor mu?
C: Aspose.Tasks for .NET kesinlikle MS Project dosyalarından anahat kodları da dahil olmak üzere özel alanların okunmasını ve yazılmasını destekler.
### S5: Aspose.Tasks for .NET için bir topluluk forumu var mı?
 C: Evet, Aspose.Tasks for .NET topluluk forumuna katılabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15) Soru sormak, bilgi paylaşmak ve diğer geliştiricilerle işbirliği yapmak.