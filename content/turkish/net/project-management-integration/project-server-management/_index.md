---
title: MS Project Server'ı Aspose.Tasks ile Yönetmek
linktitle: Aspose.Tasks ile Project Server'ı Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile kusursuz MS Project Server yönetiminin kilidini açın. Proje görevlerini zahmetsizce otomatikleştirin.
type: docs
weight: 23
url: /tr/net/project-management-integration/project-server-management/
---
## giriiş
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project Server'ı yönetmeyi derinlemesine inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan, proje verilerinin sorunsuz entegrasyonuna ve manipülasyonuna olanak tanıyan güçlü bir kütüphanedir.
## Önkoşullar
Aspose.Tasks ile MS Project Server'ı yönetmeye başlamadan önce aşağıdaki önkoşulların ayarlandığından emin olun:
1. Microsoft Project Server: Yönetici ayrıcalıklarına veya en azından proje oluşturma ve yönetme izinlerine sahip olduğunuz bir Microsoft Project Server örneğine erişmeniz gerekir.
2.  Aspose.Tasks for .NET Library: Aspose.Tasks for .NET kütüphanesini indirip yüklediğinizden emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/net/).
3. Kimlik Bilgileri: MS Project Server örneğinizle kimlik doğrulaması yapmak için gerekli kimlik bilgilerini edinin. Bu genellikle bir kullanıcı adı ve şifre içerir.
## Ad Alanlarını İçe Aktar
Başlamadan önce gerekli ad alanlarını C# kodunuza aktardığınızdan emin olun:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## 1. Adım: Kimlik Doğrulama Kimlik Bilgilerini Ayarlayın
Öncelikle MS Project Server örneğinize bağlanmak için kimlik doğrulama bilgilerini ayarlamanız gerekir. Buna alan adı adresi, kullanıcı adı ve şifre dahildir.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Adım 2: Projeyi Yükleyin
Daha sonra Aspose.Tasks'ı kullanarak yönetmek istediğiniz MS Project dosyasını yükleyin.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## 3. Adım: Proje Sunucusu Yöneticisini Oluşturun
 Bir örnek oluştur`ProjectServerManager` önceden tanımlanmış kimlik bilgilerini kullanarak nesne.
```csharp
var manager = new ProjectServerManager(credentials);
```
## 4. Adım: Kaydetme Seçeneklerini Tanımlayın
Projeniz için belirli kaydetme seçeneklerini tanımlayın. Örneğin, işlem için bir zaman aşımı süresi ayarlayabilirsiniz.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Adım 5: Proje Oluşturun veya Güncelleyin
Son olarak projeyi MS Project Server'da oluşturun veya güncelleyin.
```csharp
manager.CreateNewProject(project, options);
```
Tebrikler! Aspose.Tasks for .NET'i kullanarak MS Project Server'ı başarıyla yönettiniz.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET kullanarak MS Project Server'ın programlı olarak nasıl yönetileceğini araştırdık. Sağlanan adımlarla Aspose.Tasks'ı .NET uygulamalarınıza sorunsuz bir şekilde entegre ederek MS Project Server'da proje yönetimi görevlerini otomatikleştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks, Microsoft Project Server'ın tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks, Microsoft Project Server'ın çeşitli sürümleriyle entegrasyonu destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Aspose.Tasks'ı kullanarak projelerde toplu işlemler gerçekleştirebilir miyim?
C: Evet, Aspose.Tasks, MS Project Server'da proje oluşturma, güncelleme ve silme gibi toplu işlemleri gerçekleştirmenize olanak tanır.
### S: Aspose.Tasks proje planlama ve kaynak yönetimi için destek sağlıyor mu?
C: Aspose.Tasks kesinlikle proje planlama, kaynak tahsisi ve görev yönetimi işlevleri için kapsamlı destek sunuyor.
### S: Aspose.Tasks ile raporlama görevlerini otomatikleştirmek mümkün mü?
C: Evet, Aspose.Tasks, proje verilerine dayalı özel raporların oluşturulmasını otomatikleştirmenize olanak tanıyarak verimli proje izleme ve analizini kolaylaştırır.
### S: Aspose.Tasks'ı satın almadan önce deneyebilir miyim?
 C: Evet, Aspose.Tasks'ın yeteneklerini ücretsiz deneme sürümüne erişerek keşfedebilirsiniz.[İnternet sitesi](https://purchase.aspose.com/temporary-license/).