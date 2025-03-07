---
title: Aspose.Tasks ile Proje Verilerinde Uzmanlaşmak
linktitle: Aspose.Tasks'ta Proje Verileriyle Çalışmak
second_title: Aspose.Tasks .NET API'si
description: .NET'te Aspose.Tasks kullanarak Microsoft Project verilerini nasıl değiştireceğinizi öğrenin. Kolayca görevler oluşturun, kaynaklar ekleyin ve projeleri kaydedin.
weight: 16
url: /tr/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Proje Verilerinde Uzmanlaşmak

## giriiş
Bu eğitimde, .NET için Aspose.Tasks kütüphanesini kullanarak Microsoft Project verileriyle nasıl çalışılacağını keşfedeceğiz. Aspose.Tasks, görev oluşturma, kaynak ekleme, özellikleri ayarlama ve projeleri çeşitli formatlarda kaydetme dahil olmak üzere proje dosyalarını yönetmek için güçlü özellikler sağlar.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks Kütüphanesinin Kurulumu: Aspose.Tasks kütüphanesini şuradan indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: Bir .NET geliştirme ortamı kurduğunuzdan emin olun.
3. Temel C# Bilgisi: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar
Aspose.Tasks ile çalışmaya başlamadan önce gerekli ad alanlarını projenize aktarın:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Adım 1: Proje Nesnesini Başlatın
```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Bu satır yeni bir örneğini başlatır.`Project` Bir Microsoft Project dosyasını temsil eden sınıf.
## Adım 2: Proje Özelliklerini Ayarlayın
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Bu satırlar, projenin çalışma formatı ve görev oluşturma modu gibi özelliklerinin nasıl ayarlanacağını gösterir.
## 3. Adım: Görev Ekleme
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Burada projenin kök görevine "Görev 1" adında yeni bir görev ekleniyor.
## Adım 4: Görev Özelliklerini Ayarlama
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Bu satırlar "Görev 1" için başlangıç tarihini, süreyi ve bitiş tarihini ayarlar.
## Adım 5: Kaynak Ekleme
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Bu bölümde projeye bir çalışma kaynağının nasıl ekleneceği gösterilmektedir.
## Adım 6: Kaynakları Görevlere Atama
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Bu satırlar önceden eklenen çalışma kaynağının belirli başlangıç, çalışma ve bitiş tarihleriyle "Görev 1"e nasıl atanacağını gösterir.
## Adım 7: Projeyi Kaydetme
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Son olarak proje Microsoft Project XML dosya formatında kaydedilir.

## Çözüm
Bu eğitimde, .NET'teki Aspose.Tasks kütüphanesini kullanarak Microsoft Project verileriyle nasıl çalışacağımızı öğrendik. Adım adım kılavuzu takip ederek proje dosyalarını yönetebilir, görevler, kaynaklar ekleyebilir, görevlere kaynak atayabilir ve projeleri çeşitli formatlarda kaydedebilirsiniz.
## SSS'ler
### S: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks karmaşık proje yapıları için kapsamlı destek sağlayarak görevleri, kaynakları ve atamaları verimli bir şekilde yönetmenize olanak tanır.
### S: Aspose.Tasks, Microsoft Project'in farklı sürümleriyle uyumlu mudur?
C: Aspose.Tasks, çok çeşitli Microsoft Project sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Aspose.Tasks'ı diğer .NET kütüphaneleriyle entegre edebilir miyim?
C: Aspose.Tasks kesinlikle diğer .NET kütüphaneleriyle sorunsuz bir şekilde bütünleşerek geliştirme projelerinizde esneklik sağlar.
### S: Aspose.Tasks proje planlama algoritmaları için destek sunuyor mu?
C: Evet, Aspose.Tasks, proje zaman çizelgelerini ve kaynak kullanımını optimize etmenize yardımcı olacak gelişmiş planlama algoritmaları içerir.
### S: Aspose.Tasks kullanıcıları için bir topluluk forumu var mı?
 C: Evet, yararlı kaynaklar bulabilir ve diğer Aspose.Tasks kullanıcılarıyla iletişim kurabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
