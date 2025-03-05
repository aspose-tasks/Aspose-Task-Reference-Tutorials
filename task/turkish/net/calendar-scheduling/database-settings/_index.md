---
title: Aspose.Tasks'ta Veritabanı Ayarları
linktitle: Aspose.Tasks'ta Veritabanı Ayarları
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Primavera veritabanından projeleri nasıl içe aktaracağınızı öğrenin. Bu kapsamlı eğitimde adım adım rehberlik alın.
type: docs
weight: 29
url: /tr/net/calendar-scheduling/database-settings/
---
## giriiş

Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Tasks'ı kullanarak Primavera veritabanından projeleri içe aktarmaya odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Sisteminizde Visual Studio yüklü.
-  Aspose.Tasks for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
- Gerekli izinlerle birlikte Primavera veritabanına erişim.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu ad alanları Aspose.Tasks for .NET ile çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Şimdi sağlanan örnek kodu birden çok adıma ayıralım:

## 1. Adım: Bağlantı Dizesini Tanımlayın

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Bu adımda Primavera veritabanına bağlanacak bağlantı stringini tanımlıyoruz. Değiştirdiğinizden emin olun`DataDir` veritabanı dosyanızın bulunduğu dizinle.

## Adım 2: Veritabanı Ayarlarını Oluşturun

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Burada bir örneğini oluşturuyoruz`PrimaveraDbSettings` bağlantı dizesini ve proje kimliğini parametre olarak ileten sınıf. Proje kimliğini ihtiyacınıza göre ayarlayın.

## 3. Adım: Sağlayıcının Değişmez Adını Ayarlayın

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Sağlayıcının değişmez adını belirtin. Bu örnekte SQLite kullanıyoruz, ancak bunu veritabanı sağlayıcınıza göre değiştirebilirsiniz.

## Adım 4: Projeyi Yükle

```csharp
var project = new Project(settings);
```

 Yeni bir tane oluştur`Project` nesne, veritabanı ayarlarını parametre olarak iletir.

## Adım 5: Projeyi Kaydet

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Son olarak projeyi belirtilen dosya formatıyla istediğiniz konuma kaydedin.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'i kullanarak Primavera veritabanından projeleri nasıl içe aktaracağımızı öğrendik. Sağlanan adımları izleyerek proje içe aktarma işlevini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks for .NET'i kullanarak farklı veritabanı sağlayıcılarından projeleri içe aktarabilir miyim?

C1: Evet, bağlantı dizesini ve sağlayıcının değişmez adını buna göre ayarlayarak çeşitli veritabanı sağlayıcılarından projeleri içe aktarabilirsiniz.

### S2: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?

 C2: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).

### S3: Aspose.Tasks for .NET belgelerini nerede bulabilirim?

 A3: Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).

### S4: Aspose.Tasks for .NET için nasıl destek alabilirim?

 Cevap4: Aspose.Tasks topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).

### S5: Aspose.Tasks for .NET'i kullanmak için geçici bir lisansa ihtiyacım var mı?

 Cevap5: Kütüphanenin tam işlevselliğini değerlendirmek istiyorsanız, adresinden geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).