---
title: Aspose.Tasks için MS Project'te Yazı Tipi Düzenleme
linktitle: Aspose.Tasks'ta Yazı Tipi Kaydetme Argümanları
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki yazı tiplerini nasıl değiştireceğinizi öğrenin. Geliştiriciler için adım adım kılavuz.
weight: 19
url: /tr/net/tasks-project-management/font-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks için MS Project'te Yazı Tipi Düzenleme

## giriiş
MS Project belgelerindeki yazı tiplerini değiştirmek için Aspose.Tasks for .NET kullanımına ilişkin kapsamlı eğitimimize hoş geldiniz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan, proje verilerini okuma, yazma ve değiştirme gibi görevler için çok çeşitli işlevler sağlayan güçlü bir kitaplıktır.
Bu eğitimde, özellikle Aspose.Tasks for .NET kullanarak yazı tiplerini MS Project dosyalarına kaydetmeye odaklanacağız. Yazı tipi kaydetme özelliklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilmenizi sağlamak için süreci takip edilmesi kolay adımlara ayıracağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
1. Geliştirme Ortamı: Visual Studio ve .NET'in yüklü olduğu bir geliştirme ortamına sahip olduğunuzdan emin olun.
2.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/net/).
3.  Lisans: Aspose.Tasks for .NET için bir lisans edinin. Henüz bir lisansınız yoksa, adresinden geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
4. Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.

## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# projenize aktarın. Bu ad alanları Aspose.Tasks işlevleriyle çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.
## 1. Adım: C# Projenizi Açın
C# projenizi Visual Studio'da veya tercih edilen herhangi bir IDE'de açın.
## Adım 2: Aspose.Tasks Ad Alanını İçe Aktarın
 Aşağıdakileri ekleyin`using` Aspose.Tasks ad alanını içe aktarmak için C# dosyanızın başındaki yönerge:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

Artık projemizi oluşturduğumuza ve gerekli ad alanlarını içe aktardığımıza göre, Aspose.Tasks for .NET kullanarak yazı tiplerini MS Project dosyalarına kaydetme sürecine geçelim.
## 1. Adım: Belge Dizinini Tanımlayın
MS Project dosyasının bulunduğu belge dizininizin yolunu ayarlayın:
```csharp
String DataDir = "Your Document Directory";
```
## 2. Adım: FileStream'i oluşturun
Yazı tipi verilerini yazmak için bir FileStream oluşturun:
```csharp
var stream = new FileStream(DataDir + "fonts/" + args.FileName, FileMode.Create);
```
## 3. Adım: FileStream'i Args'a atayın
 Oluşturulan FileStream'i şuraya atayın:`Stream` yazı tipi kaydetme bağımsız değişkenlerinin özelliği:
```csharp
args.Stream = stream;
```
## 4. Adım: Dosya URI'sini belirtin
Proje dizini içindeki yazı tipi dosyasının URI'sini ayarlayın:
```csharp
args.Uri = DataDir + "fonts/" + args.FileName;
```
## Adım 5: Kullanımdan Sonra FileStream'i Kapatın
Sistem kaynaklarını serbest bırakmak için kullanımdan sonra FileStream'in kapalı olduğundan emin olun:
```csharp
args.KeepStreamOpen = false;
```

## Çözüm
Bu eğitimde, Aspose.Tasks for .NET kullanarak yazı tiplerini MS Project dosyalarına kaydetme sürecini ele aldık. Yukarıda özetlenen adımları izleyerek, yazı tipi kaydetme özelliklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre ederek proje yönetimi iş akışlarınızı geliştirebilirsiniz.
## SSS'ler
### Aspose.Tasks for .NET'i lisans olmadan kullanabilir miyim?
Hayır, uygulamalarınızda Aspose.Tasks for .NET'i kullanmak için geçerli bir lisansa ihtiyacınız var. Ancak değerlendirme amacıyla geçici bir lisans alabilirsiniz.
### Aspose.Tasks for .NET tüm sürümlerdeki Microsoft Project dosyalarıyla uyumlu mu?
Aspose.Tasks for .NET, MPP, XML ve MPX formatları dahil olmak üzere 2003'ten itibaren Microsoft Project dosya formatlarını destekler.
### Aspose.Tasks for .NET'i kullanarak MS Project dosyalarının diğer yönlerini değiştirebilir miyim?
Evet, Aspose.Tasks for .NET, MS Project dosyalarının görevler, kaynaklar ve takvimler gibi çeşitli yönlerini okumak, yazmak ve değiştirmek için geniş bir işlevsellik yelpazesi sunar.
### Aspose.Tasks for .NET hem masaüstü hem de web uygulamaları için uygun mu?
Evet, Aspose.Tasks for .NET, .NET çerçevesi kullanılarak geliştirilen hem masaüstü hem de web uygulamalarında kullanılabilir.
### Aspose.Tasks for .NET için ek destek ve kaynakları nerede bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) destek için aşağıdaki belgelere erişin:[dokümantasyon sayfası](https://reference.aspose.com/tasks/net/)Aspose.Tasks web sitesindeki eğitimleri ve örnekleri keşfedin.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
