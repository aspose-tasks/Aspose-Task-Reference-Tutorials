---
date: 2026-04-09
description: Aspose.Tasks for .NET kullanarak devreyi nasıl kontrol edeceğinizi ve
  Microsoft Project dosya bütünlüğünü nasıl doğrulayacağınızı öğrenin.
keywords:
- how to check circuit
- check project structure
- validate microsoft project
- project file integrity check
linktitle: Aspose.Tasks içinde Devreyi Kontrol Et
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Devreyi Nasıl Kontrol Edilir
url: /tr/net/calendar-scheduling/check-circuit/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Devre Kontrolü Nasıl Yapılır

## Giriş

.NET geliştirme dünyasında, görev ve projeleri verimli bir şekilde yönetmek çok önemlidir. Bir proje dosyasında **devre kontrolü** yapmak, Microsoft Project takviminin bütünlüğünü sağlamak gerektiğinde yaygın bir gereksinimdir. Aspose.Tasks for .NET, proje yapısını doğrulamanıza ve sadece birkaç satır kodla kırık görev hiyerarşilerini tespit etmenize olanak tanıyan basit bir API sunar.

## Hızlı Yanıtlar
- **“check circuit” ne yapar?** Görev hiyerarşisini dairesel referanslar veya kırık ebeveyn‑çocuk bağlantıları için tarar.  
- **Neden önemlidir?** Temiz bir proje dosyası tutmanıza yardımcı olur ve Microsoft Project'te hesaplama hatalarını önler.  
- **Hangi kütüphane kullanılır?** Aspose.Tasks for .NET.  
- **Lisans gerekli mi?** Üretim için geçici bir lisans gerekir; ücretsiz deneme sürümü test için çalışır.  
- **Desteklenen platformlar?** .NET Framework, .NET Core ve .NET 5/6+.

## Proje Devre Kontrolü Nedir?

Bir devre kontrolü (bazı zamanlar “yapı doğrulaması” olarak da adlandırılır), kök görevden başlayarak her görevi dolaşır ve her çocuğun geçerli bir ebeveyne işaret ettiğini doğrular. Bir döngü veya yetim görev bulunursa, kütüphane bir `TasksException` fırlatır ve sorunu programatik olarak ele almanıza olanak tanır.

## Microsoft Project Dosyalarını Neden Doğrulamalısınız?

- **Hesaplama hatalarını önleyin:** Dairesel referanslar takvim hesaplamalarını bozabilir.  
- **Veri bütünlüğünü koruyun:** Her görevin uygun bir hiyerarşiye ait olmasını garanti eder.  
- **Kalite kontrollerini otomatikleştirin:** Proje dosyalarının otomatik olarak oluşturulduğu veya değiştirildiği CI boru hatlarında faydalıdır.  
- **Zaman kazanın:** Sorunları erken tespit edin, Microsoft Project'te kırık bir takvimi ayıklamaktan kaçının.

## Önkoşullar

Öğreticiye başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1. Visual Studio: Sisteminizde Visual Studio yüklü olduğundan emin olun.  
2. Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini [buradan](https://releases.aspose.com/tasks/net/) indirip kurun.  
3. Temel C# Bilgisi: Örnekleri takip edebilmek için C# programlama diline aşina olmanız gerekir.

## Ad Alanlarını İçe Aktarın

C# projenizde gerekli sınıflara ve yöntemlere erişmek için aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## Adım 1: Proje Dosyasını Yükleyin

Kırık bir yapı için kontrol etmek istediğiniz Microsoft Project dosyasını (.mpp) yükleyerek başlayın. Dosyayı yüklemek için `Project` sınıfını kullanın.

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

## Adım 2: Proje Yapısını Kontrol Edin

Projede herhangi bir kırık yapı tespit etmek için `CheckCircuit` sınıfını `TaskUtils.Apply` yöntemiyle birlikte kullanacağız. Bu adım **proje yapısını kontrol eder** ve bir devre bulunduğunda bir istisna fırlatır.

```csharp
try
{
    TaskUtils.Apply(project.RootTask, new CheckCircuit(), 0);
}
catch (TasksException ex)
{
    Console.WriteLine(ex);
}
```

## Yaygın Tuzaklar ve İpuçları

- **Tuzak:** Çağrıyı bir `try/catch` bloğuna sarmayı unutmak. `CheckCircuit` işlemi bir sorun bulduğunda `TasksException` fırlatır, bu yüzden her zaman düzgün bir şekilde ele alın.  
- **İpucu:** Giriş noktası olarak `project.RootTask` kullanın; başka bir görev gönderildiğinde üst akıştaki problemler gözden kaçabilir.  
- **İpucu:** Devreyi düzelttikten sonra, proje dosyasının bütünlüğünü onaylamak için kontrolü yeniden çalıştırabilirsiniz.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for .NET'i diğer .NET çerçeveleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks for .NET, .NET Core ve .NET Framework dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.

**S: Satın almadan önce deneme sürümü mevcut mu?**  
C: Evet, [buradan](https://releases.aspose.com/) Aspose.Tasks for .NET'in ücretsiz deneme sürümünü edinebilirsiniz.

**S: Aspose.Tasks for .NET için destek nasıl alabilirim?**  
C: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım isteyebilirsiniz.

**S: Test amaçlı geçici bir lisansa ihtiyacım var mı?**  
C: Evet, test için [buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans alabilirsiniz.

**S: Aspose.Tasks for .NET'i nereden satın alabilirim?**  
C: Tam sürümü [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç

Bu rehberi izleyerek Aspose.Tasks projesinde **devre kontrolü** nasıl yapılır öğrenmiş oldunuz; proje dosyasının bütünlüğünü etkili bir şekilde doğruluyor ve temiz bir görev hiyerarşisi sağlıyorsunuz. Bu kontrolü derleme veya içe aktarma sürecinize entegre etmek, saatlerce süren manuel hata ayıklamayı önleyebilir ve takvimlerinizin güvenilirliğini artırır.

---

**Son Güncelleme:** 2026-04-09  
**Test Edilen:** Aspose.Tasks for .NET (latest version)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}