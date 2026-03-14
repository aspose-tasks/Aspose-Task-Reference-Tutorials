---
date: 2026-03-14
description: Aspose.Tasks kullanarak bir Microsoft Project veritabanı için veritabanı
  şemasını nasıl belirleyeceğinizi ve proje verilerini .NET uygulamalarına nasıl aktaracağınızı
  öğrenin.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks kullanarak Proje DB için veritabanı şemasını belirtin
url: /tr/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks içinde Microsoft Project Veritabanı Ayarları

## Giriş

Aspose.Tasks kullanarak .NET uygulamalarınızda Microsoft Project veritabanlarıyla çalışıyorsanız, **veritabanı şemasını belirtmeniz** ve **proje** verilerini sorunsuz bir şekilde içe aktarmak için gerekli ayarları yapılandırmanız gerekir. Bu öğretici, süreci adım adım size rehberlik edecek, **bağlantı** ayrıntılarını **nasıl yapılandıracağınızı**, **.NET bağlantı dizesi oluşturmayı** ve sonunda **projeyi MPP olarak kaydetmeyi** gösterecek.

## Hızlı Yanıtlar
- **Ana hedef nedir?** Veritabanı şemasını belirtmek ve bir Project veritabanını .NET uygulamasına içe aktarmak.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for .NET.  
- **Project Server'a nasıl bağlanırım?** Uygun bir SQL bağlantı dizesi oluşturarak ve `MspDbSettings` kullanarak.  
- **Hangi dosya formatı üretilir?** `SaveFileFormat.Mpp` ile kaydedilen bir MPP dosyası.  
- **Şema adını değiştirebilir miyim?** Evet, `MspDbSettings` üzerindeki `Schema` özelliğini ayarlayarak.

## Project DB için veritabanı şemasını nasıl belirtirsiniz

Neden **veritabanı şemasını belirtmeniz** gerekebileceğini anlamak önemlidir. Birçok kurumsal ortamda Project Server veritabanı özel bir şema altında bulunur (ör. `dbo`, `psdata`). Şemayı açıkça ayarlayarak, Aspose.Tasks'in doğru tabloları sorgulamasını sağlarsınız, çalışma zamanı hatalarını önler ve doğru veri içe aktarımını garantilersiniz.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Tasks for .NET: Aspose.Tasks kütüphanesini [buradan](https://releases.aspose.com/tasks/net/) indirip kurun.  
2. Microsoft Project Veritabanına Erişim: Verileri içe aktarmak için bir Microsoft Project veritabanına erişiminiz olmalıdır.  

## Ad Alanlarını İçe Aktarın

İlk olarak, projenize gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Adım 1: Bağlantı Dizesi Oluşturma

Microsoft Project veritabanınıza bağlantı dizesi oluşturun. Burada **.NET bağlantı dizesi oluşturursunuz** ve ayrıca **Project Server'a nasıl bağlanılacağını** tanımlarsınız.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro ipucu:** `DataSource` ve `InitialCatalog` değerlerini iki kez kontrol edin; bunlar sunucunuzun adresi ve yayınlanan veritabanı adıyla eşleşmelidir.

## Adım 2: MspDbSettings'i Yapılandırma

`MspDbSettings` bir örnek oluşturun, bağlantı dizesini geçirin ve `Schema` özelliğini ayarlayarak **veritabanı şemasını belirtin**. Bu, Aspose.Tasks'e hangi şemanın sorgulanacağını söyler.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Burada ayrıca yüklemek istediğiniz belirli projeyi tanımlayan proje GUID'sini sağlıyoruz.

## Adım 3: Proje Verilerini Yükleme

Yapılandırılmış ayarları kullanarak bir `Project` nesnesi örnekleyin. Bu adım, veritabanından .NET nesnesine **projeyi nasıl içe aktaracağınızı** etkili bir şekilde gerçekleştirir.

```csharp
var project = new Project(settings);
```

## Adım 4: Proje Verilerini Kaydetme

Son olarak, yüklenen projeyi diskte bir MPP dosyasına kaydedin. Bu, Aspose.Tasks API'si kullanarak **projeyi MPP olarak kaydetmeyi** gösterir.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Kodu çalıştırdıktan sonra, `ImportProjectDataFromDatabase_out.mpp` dosyasını çıktı dizininde bulacaksınız; Microsoft Project'te açılmaya hazır.

## Sonuç

Bu öğreticide, bir Microsoft Project veritabanı için **veritabanı şemasını nasıl belirlersiniz**, **bağlantıyı nasıl yapılandırırsınız**, **projeyi nasıl içe aktarırsınız** ve Aspose.Tasks for .NET kullanarak **projeyi MPP olarak nasıl kaydedersiniz** öğrendiniz. Bu adımlar, Project Server verilerinin özel uygulamalarınıza sorunsuz entegrasyonunu sağlar ve sağlam proje‑yönetim çözümleri oluşturmanıza yardımcı olur.

## Sıkça Sorulan Sorular

### Q1: Aspose.Tasks'i Microsoft Project veritabanlarının farklı sürümleriyle kullanabilir miyim?
A1: Evet, Aspose.Tasks, Microsoft Project veritabanlarının çeşitli sürümlerini destekler ve entegrasyonda esneklik sağlar.

### Q2: Veritabanı bağlantı sorunlarını nasıl gideririm?
A2: Bağlantı dizesinin uygun kimlik bilgileri ve veritabanı detaylarıyla doğru şekilde yapılandırıldığından emin olun. Ayrıca belgelere başvurabilir veya [Aspose.Tasks forumundan](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

### Q3: Aspose.Tasks için deneme sürümü mevcut mu?
A3: Evet, ücretsiz bir deneme sürümüne [buradan](https://releases.aspose.com/) erişebilirsiniz.

### Q4: Veritabanı etkileşimi için şemayı özelleştirebilir miyim?
A4: Evet, veritabanı yapınıza göre `MspDbSettings` nesnesi için şemayı belirtebilirsiniz.

### Q5: Aspose.Tasks kullanımına ilişkin daha ayrıntılı belgeleri nereden bulabilirim?
A5: Aspose.Tasks işlevselliği hakkında ayrıntılı bilgiler için kapsamlı belgeleri [burada](https://reference.aspose.com/tasks/net/) inceleyebilirsiniz.

**S: Bu yaklaşım Azure SQL veritabanlarıyla çalışır mı?**  
C: Kesinlikle. `DataSource` değerini Azure sunucu adınıza göre ayarlayın ve TLS/SSL ayarlarının etkin olduğundan emin olun.

**S: Büyük Project veritabanlarını zaman aşımına uğramadan nasıl yönetirim?**  
C: Bağlantı dizesindeki `ConnectTimeout` değerini artırın ve gerekirse projeleri partiler halinde yüklemeyi düşünün.

---

**Son Güncelleme:** 2026-03-14  
**Test Edilen:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}