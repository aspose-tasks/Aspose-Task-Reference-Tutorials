---
title: Aspose.Tasks'ta MS Project Grup Kriterlerinin Değiştirilmesi
linktitle: Aspose.Tasks'ta Grup Kriterleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks'ı kullanarak MS Project dosyalarını .NET'te programlı olarak nasıl değiştireceğinizi keşfedin. Görev grubu ve kriter bilgilerini adım adım örneklerle alın.
type: docs
weight: 27
url: /tr/net/tasks-project-management/group-criteria/
---
## giriiş
Aspose.Tasks for .NET, .NET uygulamalarınızda Microsoft Project dosyalarıyla çalışmayı kolaylaştıran güçlü bir API'dir. İster proje yönetimi yazılımı geliştiriyor olun ister proje verilerini programlı olarak manipüle etmek istiyor olun, Aspose.Tasks ihtiyaçlarınızı karşılayacak kapsamlı bir dizi özellik sunar.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. C# ve .NET Framework bilgisi
Bu eğitimde sağlanan örnekleri anlamak ve uygulamak için C# programlama dili ve .NET Framework'e aşina olmak çok önemlidir.
### 2. Aspose.Tasks for .NET'in Kurulumu
 Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/) ve verilen kurulum talimatlarını izleyin.
### 3. Entegre Geliştirme Ortamı (IDE)
C# kodunu yazmak ve yürütmek için sisteminizde Visual Studio gibi bir IDE yüklü olmalıdır.

## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# kodunuza aktarın:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Adım 1: Microsoft Proje Dosyasını Yükleyin
Öncelikle Microsoft Project dosyanızın yolunu belirtin:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Yer değiştirmek`"Your Document Directory"` proje dosyanızın yolu ile birlikte.
## Adım 2: Görev Grupları Bilgilerini Alın
Daha sonra projedeki görev grupları hakkındaki bilgileri alın:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Bu kod parçacığı, görev gruplarının toplam sayısını yazdırır, ikinci görev grubunu, adını ve içerdiği kriterlerin sayısını alır.
## 3. Adım: Görev Grubunun Kriter Bilgilerini Alın
Şimdi görev grubu içindeki belirli bir kriterin ayrıntılarına bakalım:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Bu segment, kriterin indeksi, alanı, gruplama bilgisi, hücre rengi, yazı tipi rengi, grup aralığı ve başlangıç noktası gibi çeşitli özelliklerini görüntüler.
## Adım 4: Ölçütün Yazı Tipi Bilgisini Alın
Son olarak kriterin yazı tipiyle ilgili ayrıntılarını edinin:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Bu adım, yazı tipi adını, boyutunu, stilini ve kriterin artan veya azalan düzende sıralanıp sıralanmadığını yazdırır.

## Çözüm
Bu eğitimde, bir Microsoft Project dosyasından görev grupları ve kriterler hakkındaki bilgileri almak için Aspose.Tasks for .NET'in nasıl kullanılacağını araştırdık. Adım adım kılavuzu takip ederek .NET uygulamalarınızda proje verileriyle programlı olarak verimli bir şekilde çalışabilirsiniz.
## SSS'ler
### Aspose.Tasks büyük Microsoft Project dosyalarını işleyebilir mi?
Aspose.Tasks, büyük proje dosyalarını verimli bir şekilde yönetecek şekilde optimize edilerek yüksek performans ve güvenilirlik sağlanır.
### Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
Evet, Aspose.Tasks, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı dosya formatları arasında uyumluluk sağlar.
### Aspose.Tasks'ı kullanarak proje verilerini değiştirebilir miyim?
Kesinlikle Aspose.Tasks, görevler, kaynaklar, takvimler ve daha fazlası dahil olmak üzere proje verilerini yönetmek için kapsamlı işlevler sağlar.
### Aspose.Tasks farklı .NET platformları için destek sunuyor mu?
Evet, Aspose.Tasks; .NET Framework, .NET Core ve .NET Standard dahil olmak üzere birden fazla .NET platformunu destekler.
### Aspose.Tasks için yardım isteyebileceğim bir topluluk forumu var mı?
 Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Soru sormak, bilgi paylaşmak ve diğer kullanıcılarla işbirliği yapmak için.