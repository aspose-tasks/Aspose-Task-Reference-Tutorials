---
title: Aspose.Tasks'ta Yıl Hafta Gününe Göre Tekrarlama
linktitle: Aspose.Tasks'ta Yıl Hafta Gününe Göre Tekrarlama
second_title: Aspose.Tasks .NET API'si
description: Yinelenen görevleri verimli bir şekilde yönetme konusunda Aspose.Tasks for .NET'in gücünü keşfedin. Yıl Hafta Gününe Göre Tekrarlama özelliğini uygulamaya yönelik adım adım kılavuz.
weight: 28
url: /tr/net/advanced-features/repetition-by-year-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Yıl Hafta Gününe Göre Tekrarlama

## giriiş

Proje yönetimi alanında verimlilik ve hassasiyet çok önemlidir. Aspose.Tasks for .NET, proje yönetimini kolaylaştırmak için çok sayıda özellik sunan güçlü bir araç olarak ortaya çıkıyor. Cephaneliği arasında yinelenen görevleri olağanüstü bir esneklikle yönetme yeteneği de vardır. Bu tür özelliklerden biri, kullanıcıların haftanın belirli günlerinde, belirlenen aylarda ve birden fazla yılda tekrarlanan görevleri ayarlamasına olanak tanıyan "Yılın Hafta Gününe Göre Tekrarlama" işlevidir.

## Önkoşullar

Aspose.Tasks for .NET'teki "Yıllara Göre Hafta Gününe Göre Tekrarlama" özelliğini kullanmanın inceliklerine dalmadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:

### 1. .NET Framework Bilgisi

Nesne yönelimli programlama kavramları ve C# sözdizimi de dahil olmak üzere .NET Framework'ün temellerini öğrenin.

### 2. Aspose.Tasks for .NET'in Kurulumu

 Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/). Kitaplığı geliştirme ortamınıza entegre etmek için sağlanan kurulum talimatlarını izleyin.

### 3. Dokümantasyona Erişim

 Bakın[dokümantasyon](https://reference.aspose.com/tasks/net/) Sınıfların, yöntemlerin ve kullanım örneklerinin ayrıntılı açıklamalarını içeren Aspose.Tasks for .NET hakkında kapsamlı rehberlik için.

## 4. Geliştirme Ortamı Kurulumu

Visual Studio veya .NET geliştirme için uyumlu herhangi bir IDE gibi uygun bir geliştirme ortamının yapılandırılmış olduğundan emin olun.

Artık önkoşulları yerine getirdiğinize göre, Aspose.Tasks for .NET'te "Yılın Hafta Gününe Göre Tekrarlama" uygulamasına ilişkin adım adım kılavuzu inceleyelim.


## Gerekli Ad Alanlarını İçe Aktarma

Başlamak için, .NET uygulamanızdaki Aspose.Tasks sınıflarına ve işlevlerine erişmek için gerekli ad alanlarını içe aktarın.

C# kod dosyanıza aşağıdaki ad alanı bildirimlerini ekleyin:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Bu ad alanları Aspose.Tasks kütüphanesine ve görevler ve proje dosyalarıyla çalışmak için gereken sınıflara erişim sağlar.

Şimdi Aspose.Tasks for .NET'teki "Yılın Hafta Gününe Göre Tekrarlama" özelliğini kullanarak yinelenen bir görev oluşturma sürecini yönetilebilir adımlara ayıralım.

## Adım 1: Proje ve Görev Parametrelerini Başlatın

Öncelikle projeyi başlatın ve yinelenen görevin parametrelerini tanımlayın.

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

Bu kod bölümü yeni bir projeyi başlatır ve yinelenen bir görev için parametreleri belirtir. Görev adını, süresini belirler ve yinelenme modelini tanımlar.

## Adım 2: Projeye Parametreler Ekleme

Daha sonra tanımlanan parametreleri projeye ekleyin.

```csharp
project.RootTask.Children.Add(parameters);
```

Bu satır, yinelenen görev yapılandırmasını da dahil ederek görev parametrelerini projenin kök görevine ekler.

## Adım 3: Proje Dosyasını Kaydet

Son olarak proje dosyasını yapılandırılan yinelenen görevle birlikte kaydedin.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Bu kod parçası, belirtilen yinelenen görev yapılandırmasına sahip proje dosyasını belirtilen çıktı dizinine kaydeder.

## Çözüm

Sonuç olarak, Aspose.Tasks for .NET'teki "Yılın Hafta Gününe Göre Tekrarlama" özelliğinde uzmanlaşmak, proje yöneticilerine ve geliştiricilere, yinelenen görevleri hassas ve esnek bir şekilde verimli bir şekilde ele alma gücü verir. Bu makalede özetlenen adım adım kılavuzu takip ederek, bu işlevselliği proje yönetimi iş akışlarınıza sorunsuz bir şekilde entegre ederek üretkenliği ve organizasyonu artırabilirsiniz.

## SSS'ler

### S1: Yinelenme modelini sağlanan örneklerin ötesinde özelleştirebilir miyim?

C: Evet, Aspose.Tasks for .NET, yinelenen görevler için kapsamlı özelleştirme seçenekleri sunarak yineleme modelini özel gereksinimlerinize göre uyarlamanıza olanak tanır.

### S2: Aspose.Tasks for .NET diğer proje yönetimi yazılımlarıyla uyumlu mu?

C: Aspose.Tasks for .NET, çeşitli proje yönetimi formatlarıyla birlikte çalışabilirliği destekleyerek popüler yazılım paketleriyle kusursuz entegrasyon sağlar.

### S3: Yinelenen görevlerdeki istisnaları veya değişiklikleri nasıl halledebilirim?

C: Aspose.Tasks for .NET, yinelenen görevlerdeki istisnaları ve değişiklikleri ele almak için API'ler sağlayarak, gelişen proje gereksinimlerinin yönetilmesinde esneklik sağlar.

### S4: Aspose.Tasks for .NET, bulut tabanlı proje yönetimi çözümleri için destek sunuyor mu?

C: Evet, Aspose.Tasks for .NET, bulut tabanlı proje yönetimi çözümleri için destek sunarak çeşitli platformlarda işbirliğini ve erişilebilirliği kolaylaştırır.

### S5: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?

C: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[İnternet sitesi](https://releases.aspose.com/)satın alma kararı vermeden önce özelliklerini keşfetmenize olanak tanır.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
