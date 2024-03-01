---
title: Aspose.Tasks'ta Yükleme Seçenekleri
linktitle: Aspose.Tasks'ta Yükleme Seçenekleri
second_title: Aspose.Tasks .NET API'si
description: Adım adım rehberlikle Microsoft Project belgelerini verimli bir şekilde yönetmek için Aspose.Tasks for .NET'in gücünden nasıl yararlanacağınızı öğrenin.
type: docs
weight: 16
url: /tr/net/advanced-concepts/loading-options/
---
## giriiş

Aspose.Tasks for .NET, geliştiricilerin Microsoft Project belgelerini programlı olarak yönetmelerine olanak tanıyan güçlü bir kitaplıktır. Proje dosyalarını oluşturmanız, okumanız, yazmanız veya dönüştürmeniz gerekiyorsa Aspose.Tasks, görevlerinizi kolaylaştırmak için geniş bir işlevsellik yelpazesi sunar. Bu eğitimde, Aspose.Tasks for .NET kullanımının temellerini inceleyerek önemli süreçleri basit, uygulanabilir adımlara ayıracağız.

## Önkoşullar

Aspose.Tasks for .NET'e dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:

1. Visual Studio: Visual Studio'yu veya seçtiğiniz herhangi bir IDE'yi yükleyin.
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
3. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.

Artık önkoşullarımızı ele aldığımıza göre, temel ad alanlarını inceleyelim ve adım adım kılavuza dalalım.

## Ad Alanlarını İçe Aktarma

Aspose.Tasks işlevlerine erişmek için C# projenize gerekli ad alanlarını içe aktarın:

1. Aspose.Tasks: Bu ad alanı, Proje belgeleriyle çalışmak için temel sınıflar ve arayüzler sağlar.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Şimdi farklı görevleri adım adım kılavuzlara ayıralım.

## Adım 1: Parola Korumalı Projeleri Yükleme

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Proje dosyasını yüklemek için FileStream'i başlatın
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // LoadOptions örneği oluştur
        var options = new LoadOptions
        {
            Password = "password" // Şifreyi ayarla
        };

        // Projeyi belirtilen seçeneklerle yükleyin
        var project = new Project(stream, options);

        // Proje adını görüntüle
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Adım 2: Primavera Projelerini Özel Seçeneklerle Yükleme

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // LoadOptions örneği oluştur
    var loadOptions = new LoadOptions();

    // Primavera okuma seçeneklerini yapılandırma
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Proje UID'sini ayarlayın
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Primavera okuma seçeneklerini ayarlama
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Primavera projesini belirtilen seçeneklerle yükleyin
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Proje adını görüntüle
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Yüklenen projeyle daha fazla işlem gerçekleştirin
}
```

## 3. Adım: Dosya Kodlamasını Belirleme

```csharp
public void SpecifyFileEncoding()
{
    // LoadOptions örneği oluştur
    LoadOptions lo = new LoadOptions();

    // Primavera XER dosyasından bir proje açarken kodlamayı belirtin
    lo.Encoding = Encoding.GetEncoding(1251);

    // Projeyi belirtilen kodlamayla yükleyin
    var project = new Project("encoding1251.xer", lo);

    // Yüklenen projeyle daha fazla işlem gerçekleştirin
}
```

## Adım 4: Primavera Projelerini Hata İşlemeyle Yükleme

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // LoadOptions örneği oluştur
    var loadOptions = new LoadOptions();

    // Primavera okuma seçeneklerini yapılandırma
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Proje UID'sini ayarlayın
    };

    // Primavera okuma seçeneklerini ayarlama
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Özel hata işlemeyi ayarlayın
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Primavera projesini belirtilen seçeneklerle ve hata işlemeyle yükleyin
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Yüklenen projeyle daha fazla işlem gerçekleştirin
}

// Özel hata işleyici yöntemi
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Özel hata işleme mantığını uygulayın
}
```

Bu adımları izleyerek Aspose.Tasks for .NET'teki yükleme seçeneklerini etkili bir şekilde kullanarak Proje belgelerini ihtiyaçlarınıza göre yönetebilirsiniz.

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'te yükleme seçenekleriyle çalışmanın temellerini inceledik. Parola korumalı projelerin yüklenmesinden özel hata yönetiminin belirlenmesine kadar, bu tekniklerde uzmanlaşmak, .NET uygulamalarınızdaki Proje dosyalarını verimli bir şekilde yönetmenizi sağlayacaktır.

## SSS'ler

### S1: Aspose.Tasks for .NET, Microsoft Project'in tüm sürümleriyle uyumlu mudur?

C1: Evet, Aspose.Tasks for .NET, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S2: Aspose.Tasks for .NET'i diğer üçüncü taraf kütüphanelerle entegre edebilir miyim?

Cevap2: Aspose.Tasks for .NET kesinlikle diğer .NET kitaplıklarıyla sorunsuz bir şekilde bütünleşerek gelişmiş işlevsellik ve esneklik sunar.

### S3: Aspose.Tasks for .NET dokümantasyon ve destek kaynakları sağlıyor mu?

 A3: Evet, kapsamlıya başvurabilirsiniz[dokümantasyon](https://reference.aspose.com/tasks/net/) ve aracılığıyla desteğe erişin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

### S4: Aspose.Tasks for .NET için herhangi bir lisanslama seçeneği mevcut mu?

 C4: Evet, ücretsiz denemeler ve geçici lisanslar da dahil olmak üzere farklı lisanslama seçeneklerini[Aspose.Tasks web sitesi](https://purchase.aspose.com/buy).

### S5: Aspose.Tasks for .NET için güncellemeler ve yeni özellikler ne sıklıkla yayınlanıyor?

Cevap5: Aspose.Tasks for .NET, optimum performansı ve gelişen teknolojilerle uyumluluğu sağlamak için düzenli güncellemeler ve özellik geliştirmeleri alır.