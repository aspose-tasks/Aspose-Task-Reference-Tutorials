---
date: 2026-04-01
description: Aspose.Tasks for .NET’te tekrarlamayı nasıl ayarlayacağınızı öğrenin,
  yinelenen görev ekleyin ve aylık, haftalık ve günlük olarak yinelenen görevleri
  otomatikleştirin.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Aspose.Tasks'te Ay, Hafta ve Gün Bazlı Tekrarlama
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Tekrarlamayı Nasıl Ayarlarsınız (Ay, Hafta, Gün)
url: /tr/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Tekrarlamayı Nasıl Ayarlarsınız (Ay, Hafta, Gün)

## Giriş

Bir projedeki görevler için **tekrarlamayı nasıl ayarlayacağınızı** öğrenmeniz gerekiyorsa, Aspose.Tasks for .NET, ay, hafta veya gün bazında çalışan tekrarlayan görev tanımlarını eklemenin temiz ve programatik bir yolunu sunar. Bu öğreticide, **tekrarlayan görev** girişlerini nasıl **ekleyeceğinizi**, **tekrarlayan görevleri otomatikleştireceğinizi** ve bunları doğrudan C# kodundan nasıl yöneteceğinizi gösteren gerçek bir örnek üzerinden ilerleyeceğiz. Sonunda, bu yeteneği herhangi bir zamanlama veya proje yönetimi çözümüne entegre etmeye hazır olacaksınız.

## Hızlı Yanıtlar
- **Aspose.Tasks'te “tekrarlama” ne anlama gelir?** Bir tarih aralığında görev örneklerini otomatik olarak oluşturan bir desen (günlük, haftalık, aylık) tanımlar.  
- **Tekrarlamayı oluşturan temel yöntem hangisidir?** Belirli bir `RecurrencePattern` ile birleştirilen `RecurringTaskParameters`.  
- **Bu kodu çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için bir deneme sürümü çalışır; üretim için ticari bir lisans gereklidir.  
- **Aylık yerine haftalık görevler planlayabilir miyim?** Evet – `MonthlyRecurrencePattern` yerine `WeeklyRecurrencePattern` kullanın.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 ve sonrası.

## Aspose.Tasks'te Tekrarlama Nedir?

Tekrarlama, Aspose.Tasks'e görev örneklerini düzenli aralıklarla—günlük, haftalık veya aylık—manuel olarak kopyalamadan oluşturmasını söyleyen bir dizi kuraldır. Bu özellik, durum toplantıları, denetimler veya bakım çalışmaları gibi rutin faaliyetleri içeren projeler için çok önemlidir.

## Neden Tekrarlama Özelliklerini Kullanmalısınız?

- **Zaman kazanın:** Görevleri manuel olarak kopyalayıp yapıştırmaya gerek yok.  
- **Hataları azaltın:** Kütüphane tutarlı tarih ve süreler sağlar.  
- **Esneklik:** Desenleri birleştirin (örn., “her 2 ayda bir ilk Pazar”).  
- **Otomasyon:** CI boru hatlarında veya raporlama araçlarında takvim oluşturmak için mükemmeldir.

## Önkoşullar

1. **C# Temel Anlayışı** – birkaç satır C# kodu yazacaksınız.  
2. **Aspose.Tasks for .NET yüklü** – [download page](https://releases.aspose.com/tasks/net/) adresinden edinin.  
3. **Bir .mpp proje dosyası** – kaynak dosya olarak `Project1.mpp` kullanacağız.

## Ad Alanlarını İçe Aktarın

Başlamak için gerekli Aspose.Tasks ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Adım 1: Proje Dosyasını Yükleyin

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

`Project` örneğini, mevcut bir Microsoft Project dosyasına işaret edecek şekilde oluştururuz.

### Adım 2: Tekrarlayan Görev Parametrelerini Tanımlayın

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Burada **tekrarlayan görev** parametrelerini oluşturuyoruz:

- **TaskName** – oluşturulan görevin adı.  
- **Duration** – her bir oluşumun süresi.  
- **RecurrencePattern** – her 2 ayda bir ilk Pazar tekrarlanan aylık bir desen.  
- **RecurrenceRange** – takvimi sınırlayan başlangıç ve bitiş tarihleri.

### Adım 3: Tekrarlayan Görevi Projeye Ekleyin

```csharp
project.RootTask.Children.Add(parameters);
```

Bu satır, **tekrarlayan görevi** proje hiyerarşisinin köküne ekler.

### Adım 4: Güncellenmiş Projeyi Kaydedin

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Proje, artık otomatik takvimi içeren yeni bir `.mpp` dosyası olarak kaydedilir.

## Yaygın Sorunlar ve Çözümleri

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Görev görünmüyor** | Tekrarlama aralığı proje tarihleri dışındadır. | `Start` ve `Finish` değerlerinin proje takviminde olduğundan emin olun. |
| **Yanlış gün** | `WeekDay` enum uyumsuzluğu. | Gerekli olduğunda `DayOfWeek.Monday` … `DayOfWeek.Sunday` kullanın. |
| **Lisans istisnası** | Üretimde geçerli bir lisans olmadan çalıştırılıyor. | Kaydetmeden önce geçici veya tam bir lisans uygulayın. |

## Sıkça Sorulan Sorular

### S1: Sağlanan örneklerin ötesinde tekrarlama desenini özelleştirebilir miyim?

Evet, Aspose.Tasks for .NET, tekrarlama desenleri için kapsamlı özelleştirme seçenekleri sunar ve bunları belirli gereksinimlerinize göre uyarlamanıza olanak tanır.

### S2: Aspose.Tasks for .NET için deneme sürümü mevcut mu?

Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü [releases page](https://releases.aspose.com/) adresinden edinebilirsiniz.

### S3: Aspose.Tasks for .NET için destek nasıl alabilirim?

Yardım alabilir ve toplulukla etkileşime geçmek için [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresini kullanabilirsiniz.

### S4: Aspose.Tasks for .NET için geçici lisanslar mevcut mu?

Evet, test ve değerlendirme amaçları için [purchase page](https://purchase.aspose.com/temporary-license/) adresinden geçici lisanslar alabilirsiniz.

### S5: Aspose.Tasks for .NET için kapsamlı belgeleri nerede bulabilirim?

Kütüphaneyi derinlemesine kullanmak için Aspose web sitesinde bulunan ayrıntılı [documentation](https://reference.aspose.com/tasks/net/) adresine başvurabilirsiniz.

---

**Son Güncelleme:** 2026-04-01  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}