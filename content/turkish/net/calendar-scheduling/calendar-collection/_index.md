---
title: Aspose.Tasks'ta Takvim Koleksiyonunu Yönetme
linktitle: Aspose.Tasks'ta Takvim Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'te takvim koleksiyonlarını verimli bir şekilde nasıl yöneteceğinizi öğrenin. Takvimleri kolaylıkla oluşturun, değiştirin ve yönetin.
type: docs
weight: 11
url: /tr/net/calendar-scheduling/calendar-collection/
---
## giriiş

Bu eğitimde Aspose.Tasks for .NET'te takvim koleksiyonlarının nasıl yönetileceğini inceleyeceğiz. Takvimler proje yönetiminde iş günlerini, tatilleri ve istisnaları tanımlayarak çok önemli bir rol oynar. Aspose.Tasks, projelerinizdeki takvimleri yönetmek için güçlü işlevsellik sağlar.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: Visual Studio'yu veya herhangi bir uyumlu .NET geliştirme için IDE'yi yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
3. Temel C# anlayışı: C# programlama diline aşinalık faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Tasks ile çalışmak için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Yeni Takvim Oluşturma

###  1. Adım: Yeni bir başlangıç yapın`Project` object.
```csharp
var project = new Project();
```

### Adım 2: Projenin takvim koleksiyonuna takvimler ekleyin.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Adım 3: Takvimleri yineleyin ve adlarını görüntüleyin.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Takvimi Yeni Takvimle Değiştirme

### Adım 1: Mevcut bir projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Mevcut takvimi (varsa) kaldırın.
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

## Takvimi Ada veya Kimliğe Göre Alma

### Adım 1: Projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Takvimleri ada veya UID'ye göre alın.
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

## Takvimler Üzerinde Yineleme

### Adım 1: Projeyi yükleyin.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Adım 2: Takvimlerin sayısını alın.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Adım 3: Takvim koleksiyonunu ve görünen adları yineleyin.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Standart Takvim Yapmak

### Adım 1: Yeni bir proje başlatın.
```csharp
var project = new Project();
```

### Adım 2: Yeni bir takvim tanımlayın ve onu standart hale getirin.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Adım 3: Projeyi kaydedin.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Çözüm

Aspose.Tasks for .NET'te takvim koleksiyonlarını yönetmek, etkili proje yönetimi için çok önemlidir. Sağlanan işlevlerle, proje gereksinimlerinize göre takvimleri verimli bir şekilde oluşturabilir, değiştirebilir ve yönetebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks'ta özel iş günleri oluşturabilir miyim?

C1: Evet, takvimlere istisnalar ekleyerek özel iş günleri oluşturabilirsiniz.

### S2: Takvimleri Microsoft Project dosyalarından içe aktarmak mümkün mü?

Cevap2: Kesinlikle Aspose.Tasks, Microsoft Project dosyalarından takvimlerin içe aktarılmasını destekler.

### S3: Belirli bir takvimi bir projeden nasıl kaldırabilirim?

Cevap3: Bir takvimi koleksiyondan alıp ardından çağrı yaparak kaldırabilirsiniz.`Remove` yöntem.

### S4: Aspose.Tasks takvimlerin farklı formatlara aktarılmasını destekliyor mu?

Cevap4: Evet, Aspose.Tasks, takvimlerin XML, MPP vb. gibi çeşitli formatlara aktarılmasına olanak tanır.

### S5: Bir takvimdeki belirli günler için çalışma saatlerini özelleştirebilir miyim?

Cevap5: Elbette, takvimdeki istisnaları kullanarak bireysel günler için çalışma saatlerini tanımlayabilirsiniz.