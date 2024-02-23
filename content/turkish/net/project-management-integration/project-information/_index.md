---
title: Aspose.Tasks'ta MS Proje Bilgilerini Çıkarın
linktitle: Aspose.Tasks'ta Proje Bilgilerini Çıkarma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project bilgilerini zahmetsizce nasıl çıkaracağınızı öğrenin. Kapsamlı eğitimimize dalın.
type: docs
weight: 20
url: /tr/net/project-management-integration/project-information/
---
## giriiş
Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarından verimli bir şekilde bilgi ayıklamak mı istiyorsunuz? Bu eğitimde size süreç boyunca adım adım rehberlik edeceğiz. Ancak uygulama ayrıntılarına dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
### 1. .NET için Aspose.Tasks
 Aspose.Tasks for .NET kitaplığını yüklediğinizden emin olun. Henüz yapmadıysanız adresinden indirebilirsiniz.[.NET web sitesi için Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. SharePoint için Kimlik Bilgileri
MS Project dosyalarınızın depolandığı SharePoint'e erişmek için kimlik bilgilerine ihtiyacınız olacak. Aşağıdaki bilgilere sahip olduğunuzdan emin olun:
- SharePoint Etki Alanı Adresi
- Kullanıcı adı
- Şifre
## Ad Alanlarını İçe Aktarma
Önkoşullarınızı sıraladıktan sonra, gerekli ad alanlarını projenize aktarmanın zamanı geldi.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Şimdi MS Project bilgilerini çıkarma sürecini birden çok adıma ayıralım.
## 1. Adım: Kimlik Bilgilerini Sağlayın
Öncelikle Project Server'a erişmek için SharePoint kimlik bilgilerinizi sağlamanız gerekir.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Adım 2: Proje Sunucusu Yöneticisini Başlatın
 Daha sonra, bir başlatma işlemi gerçekleştirin`ProjectServerManager` sağlanan kimlik bilgileriyle örnek.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Adım 3: Proje Listesini Alın
Artık projelerin listesini Project Server'dan alabilirsiniz.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Adım 4: Proje Bilgilerini Yazdırın
Son olarak, proje listesini yineleyin ve bilgilerini yazdırın.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Çözüm
Tebrikler! Aspose.Tasks for .NET'i kullanarak MS Project bilgilerini nasıl çıkaracağınızı başarıyla öğrendiniz. Bu bilgi birikimiyle artık bu işlevselliği .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### S1: Aspose.Tasks for .NET'i Microsoft Project'in herhangi bir sürümüyle kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, 2003, 2007, 2010, 2013, 2016 ve 2019 dahil olmak üzere Microsoft Project'in çeşitli sürümlerini destekler.
### S2: Aspose.Tasks for .NET hem Windows hem de Linux platformlarıyla uyumlu mudur?
C: Evet, Aspose.Tasks for .NET hem Windows hem de Linux platformlarıyla uyumludur, bu da onu farklı geliştirme ortamları için çok yönlü kılar.
### S3: Aspose.Tasks for .NET'i kullanarak görev bağımlılıklarını çıkarabilir miyim?
C: Kesinlikle! Aspose.Tasks for .NET, yalnızca temel proje bilgilerini değil aynı zamanda görev bağımlılıklarını ve diğer karmaşık ayrıntıları da çıkarmak için güçlü işlevsellik sağlar.
### S4: Aspose.Tasks for .NET teknik destek sunuyor mu?
 C: Evet, Aspose.Tasks for .NET için teknik desteği şu adresten alabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)Soru sorabileceğiniz ve uzmanlardan yardım alabileceğiniz yer.
### S5: Aspose.Tasks for .NET'i satın almadan önce deneyebilir miyim?
 C: Kesinlikle! Aspose.Tasks for .NET'in ücretsiz deneme sürümünden yararlanabilirsiniz.[sürümler sayfası](https://releases.aspose.com/)satın alma kararı vermeden önce özelliklerini keşfetmenize olanak tanır.