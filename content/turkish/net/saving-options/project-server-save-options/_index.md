---
title: Aspose.Tasks için Sunucu Kaydetme MS Proje Seçenekleri
linktitle: Aspose.Tasks için Project Server Kaydetme Seçenekleri
second_title: Aspose.Tasks .NET API'si
description: Project Server entegrasyonunu kullanarak Aspose.Tasks için Microsoft Project seçeneklerini nasıl kaydedeceğinizi öğrenin. Proje yönetimi iş akışlarınızı geliştirin.
type: docs
weight: 16
url: /tr/net/saving-options/project-server-save-options/
---
## giriiş
Bu eğitimde, Project Server kullanarak Aspose.Tasks için Microsoft Project seçeneklerini kaydetmeyi ele alacağız. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir .NET API'sidir. Project Server yeteneklerinden yararlanarak Aspose.Tasks'i proje yönetimi iş akışlarımıza sorunsuz bir şekilde entegre edebiliyoruz. Bu eğitim size süreç boyunca adım adım rehberlik edecektir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
   
2. Project Server'a Erişim: Erişim kimlik bilgilerine ve Project Server örneğinizin URL'sine ihtiyacınız olacaktır. Eğer bir hesabınız yoksa, şu adresten ücretsiz deneme sürümü edinebilirsiniz:[Burada](https://releases.aspose.com/).
3. Microsoft Project Dosyası: Aspose.Tasks'ı kullanarak kaydetmek istediğiniz Microsoft Project dosyasını (.mpp) hazırlayın.

## Ad Alanlarını İçe Aktar
Öncelikle projenize gerekli ad alanlarını içe aktarmanız gerekir:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## 1. Adım: Projeyi ve Kimlik Bilgilerini Başlatın
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Değiştirdiğinizden emin olun`"Your Document Directory"`, `URL`, `Domain`, `UserName` , Ve`Password` gerçek değerlerinizle.
## Adım 2: Proje Sunucu Yöneticisi Oluşturun
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## 3. Adım: Kaydetme Seçeneklerini Tanımlayın
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Ayarlayın`ProjectGuid`, `ProjectName`, `Timeout` , Ve`PollingInterval` gereksinimlerinize göre.
## Adım 4: Projeyi Sunucuya Kaydetme
```csharp
manager.CreateNewProject(project, options);
```
Bu, projeyi belirtilen seçeneklerle Proje Sunucusuna kaydedecektir.

## Çözüm
Bu eğitimde, Project Server entegrasyonunu kullanarak Aspose.Tasks için Microsoft Project seçeneklerini nasıl kaydedeceğimizi öğrendik. Bu adımları izleyerek Aspose.Tasks'i proje yönetimi iş akışlarınıza sorunsuz bir şekilde dahil edebilir, verimliliği ve üretkenliği artırabilirsiniz.
## SSS'ler
### S: Aspose.Tasks'i Microsoft Project'in farklı sürümleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks, Microsoft Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Aspose.Tasks'ın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks çoklu iş parçacığını destekliyor mu?
C: Evet, Aspose.Tasks iş parçacığı açısından güvenli olacak şekilde tasarlanmıştır ve proje verilerine eş zamanlı erişime olanak sağlar.
### S: Project Server entegrasyonunu kullanırken kaydetme seçeneklerini özelleştirebilir miyim?
C: Evet, proje adı, zaman aşımı ve yoklama aralığı gibi kaydetme seçeneklerini ihtiyaçlarınıza göre uyarlayabilirsiniz.
### S: Aspose.Tasks için desteği nerede bulabilirim?
 C: Destek ve yardımı şu adreste bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).