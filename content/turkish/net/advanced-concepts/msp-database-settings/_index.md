---
title: Aspose.Tasks'ta Microsoft Project Veritabanı Ayarları
linktitle: Aspose.Tasks'ta Microsoft Project Veritabanı Ayarları
second_title: Aspose.Tasks .NET API'si
description: .NET uygulamalarına sorunsuz entegrasyon için Aspose.Tasks'ı kullanarak Microsoft Project veritabanı ayarlarını nasıl yapılandıracağınızı öğrenin.
type: docs
weight: 19
url: /tr/net/advanced-concepts/msp-database-settings/
---
## giriiş

Aspose.Tasks'ı kullanarak .NET uygulamalarınızda Microsoft Project veritabanlarıyla çalışıyorsanız, proje verilerini sorunsuz bir şekilde içe aktarmak için gerekli ayarları yapılandırmanız gerekir. Bu eğitim size süreç boyunca adım adım rehberlik edecektir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Tasks for .NET: Aspose.Tasks kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Veritabanına Erişim: Verileri içe aktarmak için bir Microsoft Project veritabanına erişiminizin olması gerekir.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projenize aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 1. Adım: Bağlantı Dizesi Oluşturun

Bağlantı dizesini Microsoft Project veritabanınıza oluşturun. İşte bir örnek:

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

Yer tutucu değerlerini gerçek veritabanı kimlik bilgilerinizle değiştirdiğinizden emin olun.

## Adım 2: MspDbSettings'i yapılandırın

 Bir örneğini oluşturun`MspDbSettings` ve proje GUID'i ile birlikte bağlantı dizesini belirtin:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## 3. Adım: Proje Verilerini Yükleyin

 Bir örnek oluştur`Project` yapılandırılmış ayarları kullanan nesne:

```csharp
var project = new Project(settings);
```

## Adım 4: Proje Verilerini Kaydedin

Yüklenen proje verilerini bir dosyaya kaydedin:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET kullanarak Microsoft Project veritabanlarına erişim ayarlarını nasıl yapılandıracağınızı öğrendiniz. Bu adımları izleyerek proje verilerini sorunsuz bir şekilde uygulamalarınıza aktarabilir ve verimli proje yönetimini kolaylaştırabilirsiniz.

## SSS'ler

### S1: Aspose.Tasks'i Microsoft Project veritabanlarının farklı sürümleriyle kullanabilir miyim?

Cevap1: Evet, Aspose.Tasks, Microsoft Project veritabanlarının çeşitli sürümlerini destekleyerek entegrasyonda esneklik sağlar.

### S2: Veritabanıyla bağlantı sorunlarını nasıl giderebilirim?

Y2: Bağlantı dizenizin uygun kimlik bilgileri ve veritabanı ayrıntılarıyla doğru şekilde yapılandırıldığından emin olun. Ayrıca belgelere başvurabilir veya destek talebinde bulunabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

### S3: Aspose.Tasks'ın deneme sürümü mevcut mu?

 C3: Evet, ücretsiz deneme sürümüne şuradan erişebilirsiniz:[Burada](https://releases.aspose.com/).

### S4: Veritabanı etkileşimi için şemayı özelleştirebilir miyim?

 A4: Evet, şemayı belirtebilirsiniz.`MspDbSettings` veritabanı yapınıza göre nesne.

### S5: Aspose.Tasks kullanımına ilişkin daha ayrıntılı belgeleri nerede bulabilirim?

 A5: Kapsamlı belgeleri inceleyebilirsiniz[Burada](https://reference.aspose.com/tasks/net/) Aspose.Tasks işlevlerine ilişkin ayrıntılı bilgiler için.