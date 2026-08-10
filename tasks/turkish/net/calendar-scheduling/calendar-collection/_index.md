---
date: 2026-04-13
description: Aspose.Tasks for .NET'te çalışma saatlerini nasıl ayarlayacağınızı ve
  takvim koleksiyonlarını nasıl yöneteceğinizi öğrenin. Microsoft Project'ten takvimleri
  içe aktarın, takvimi projeden kaldırın ve takvimi isme göre kolayca alın.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Aspose.Tasks'te Takvim Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks Takvim Koleksiyonunda Çalışma Saatlerini Ayarlama
url: /tr/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Takvim Koleksiyonunda Çalışma Saatlerini Ayarlama

Bu öğreticide, **çalışma saatlerini ayarlamayı** ve takvim koleksiyonlarını Aspose.Tasks for .NET ile yönetmeyi öğreneceksiniz. Takvimler çalışma günlerini, tatilleri ve istisnaları tanımlar; bu sayede proje takvimlerini hassas bir şekilde kontrol edebilirsiniz. Ayrıca takvimleri Microsoft Project'ten içe aktarma, bir takvimi projeden kaldırma ve takvimi adına göre alma konularını da göstereceğiz.

## Hızlı Yanıtlar
- **Takvimler için birincil sınıf nedir?** `Project.Calendars` koleksiyonu.
- **Çalışma saatlerini nasıl ayarlarım?** Bir `Calendar` nesnesi oluşturup veya değiştirip `WorkingTime` özelliğini tanımlayın.
- **Microsoft Project'ten takvimleri içe aktarabilir miyim?** Evet – bir MPP dosyası yükleyin ve takvimlerine erişin.
- **Bir takvimi projeden nasıl kaldırırım?** `Project.Calendars.Remove(calendar)` kullanın.
- **Takvimi adına göre nasıl alırım?** `Project.Calendars.GetByName("YourCalendar")` çağırın.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: .NET geliştirme için Visual Studio veya başka bir uyumlu IDE kurun.  
2. Aspose.Tasks for .NET: Aspose.Tasks for .NET'i [buradan](https://releases.aspose.com/tasks/net/) indirin ve kurun.  
3. C# temelleri: C# programlama dili hakkında temel bilgi faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Aspose.Tasks ile çalışmak için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Yeni Bir Takvim Oluşturma

### Adım 1: Yeni bir `Project` nesnesi başlatın.
```csharp
var project = new Project();
```

### Adım 2: Takvimleri projenin takvim koleksiyonuna ekleyin.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Adım 3: Takvimler üzerinde döngü kurarak adlarını görüntüleyin.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Bir Takvim İçin Çalışma Saatleri Nasıl Ayarlanır?

**Çalışma saatlerini ayarlamak** için bir `Calendar` nesnesinin `WorkingTime` koleksiyonunu değiştirirsiniz.  
Örneğin, standart bir 9 – 17 çalışma gününü tanımlayabilir veya özel istisnalar ekleyebilirsiniz.  
Bu kod, daha sonra standart bir takvim oluştururken gösterilen örneklerle aynıdır.

## Bir Takvimi Yeni Bir Takvimle Değiştirme

### Adım 1: Mevcut bir projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Mevcut takvimi (varsa) kaldırın.  
Bu, **takvim kaldırma** senaryosunu gösterir.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Adım 3: Yeni bir takvim ekleyin.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Takvimi Adına veya Kimliğine Göre Alma

### Adım 1: Projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Takvimleri ad veya UID ile alın.  
Bu, **adına göre takvim alma** işlemini gösterir.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Adım 3: Takvim ayrıntılarını görüntüleyin.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Takvimler Üzerinde Döngü

### Adım 1: Projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Takvim sayısını alın.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Adım 3: Takvim koleksiyonu üzerinde döngü kurarak adları görüntüleyin.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Standart Bir Takvim Oluşturma

### Adım 1: Yeni bir proje başlatın.
```csharp
var project = new Project();
```

### Adım 2: Yeni bir takvim tanımlayın ve onu standart yapın.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Adım 3: Projeyi kaydedin.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler

- **`GetByName` kullanırken takvim bulunamıyor** – Takvim eklenirken kullanılan tam adı, büyük/küçük harf duyarlılığıyla aynı olduğundan emin olun.  
- **Çalışma saatleri uygulanmıyor** – `WorkingTime` ayarlandıktan sonra projeyi kaydedin; aksi takdirde değişiklikler yalnızca bellekte kalır.  
- **MPP dosyasından takvim içe aktarma başarısız** – Kaynak dosyanın geçerli bir Microsoft Project dosyası olduğundan ve okuma izinlerinizin bulunduğundan emin olun.

## SSS'ler

### S1: Aspose.Tasks'te özel çalışma günleri oluşturabilir miyim?

C1: Evet, takvimlere istisnalar ekleyerek özel çalışma günleri oluşturabilirsiniz.

### S2: Microsoft Project dosyalarından takvimleri içe aktarabilir miyim?

C2: Kesinlikle, Aspose.Tasks Microsoft Project dosyalarından takvim içe aktarmayı destekler.

### S3: Bir projeden belirli bir takvimi nasıl kaldırırım?

C3: Takvimi koleksiyondan alıp `Remove` metodunu çağırarak kaldırabilirsiniz.

### S4: Aspose.Tasks takvimleri farklı formatlara dışa aktarmayı destekliyor mu?

C4: Evet, Aspose.Tasks takvimleri XML, MPP gibi çeşitli formatlara dışa aktarabilir.

### S5: Takvimde belirli günler için çalışma saatlerini özelleştirebilir miyim?

C5: Tabii ki, takvimdeki istisnalar aracılığıyla tek tek günler için çalışma saatleri tanımlayabilirsiniz.

## Sıkça Sorulan Sorular

**S: 24 saatlik vardiya takvimini nasıl ayarlarım?**  
C: Yeni bir takvim oluşturun, mevcut `WorkingTime` girişlerini temizleyin ve her hafta içi günü için 00:00‑24:00 aralığını tek bir `WorkingTime` olarak ekleyin.

**S: Bir takvimi bir projeden diğerine kopyalayabilir miyim?**  
C: Evet—takvimi `project.Save` ile XML olarak dışa aktarın ve ardından `new Project(xmlPath)` ile başka bir projeye içe aktarın.

**S: Microsoft Project'ten takvimleri programlı olarak nasıl içe aktarırım?**  
C: `new Project("source.mpp")` ile MPP dosyasını yükleyin; takvimler `project.Calendars` üzerinden erişilebilir.

**S: Bir projedeki takvim sayısına bir limit var mı?**  
C: Pratikte yok; koleksiyon belleğin izin verdiği kadar takvim tutabilir, ancak performans için listeyi yönetilebilir tutmanız önerilir.

**S: Bir takvimdeki değişiklikler, onu kullanan görevleri otomatik olarak günceller mi?**  
C: Evet—takvime bağlı görevler, projeyi kaydettikten sonra güncellenmiş çalışma zamanlarını yansıtır.

---

**Son Güncelleme:** 2026-04-13  
**Test Edilen Sürüm:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}