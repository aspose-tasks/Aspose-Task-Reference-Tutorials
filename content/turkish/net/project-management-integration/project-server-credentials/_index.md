---
title: Aspose.Tasks'ta MS Project Server Kimlik Bilgilerini Yönetme
linktitle: Aspose.Tasks'ta Project Server Kimlik Bilgilerini Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile MS Project Server kimlik bilgilerini sorunsuz bir şekilde nasıl yöneteceğinizi öğrenin. Proje yönetimi verimliliğini artırın.
type: docs
weight: 22
url: /tr/net/project-management-integration/project-server-credentials/
---
## giriiş
Proje yönetimi alanında, etkili koordinasyon ve kesintisiz iletişim, projenin başarılı bir şekilde yürütülmesi için çok önemlidir. Aspose.Tasks for .NET, Microsoft Project Server kimlik bilgilerini yönetmek için kapsamlı bir çözüm sunarak kullanıcıların proje verilerine güvenli bir şekilde erişmesine ve bunları yönetmesine olanak tanır. Bu eğitim, Aspose.Tasks for .NET kullanarak MS Project Server kimlik bilgilerini yönetme sürecini ayrıntılı olarak ele alıyor ve sorunsuz bir deneyim sağlamak için kullanıcılara her adımda rehberlik ediyor.
## Önkoşullar
Aspose.Tasks for .NET ile MS Project Server kimlik bilgilerini yönetme yolculuğuna çıkmadan önce aşağıdaki ön koşulların karşılandığından emin olun:
### 1. Aspose.Tasks for .NET'i yükleme
 Başlamak için Aspose.Tasks for .NET'i sağlanan kaynaktan indirip yükleyin.[İndirme: {link](https://releases.aspose.com/tasks/net/), Kitaplığı .NET ortamınıza sorunsuz bir şekilde entegre etmek için kurulum talimatlarını izleyin.
### 2. Kimlik Bilgilerine Erişim
MS Project Server'a erişim için gereken gerekli kimlik bilgilerini toplayın. Buna Project Server ile ilişkili SharePoint etki alanı adresi, kullanıcı adı ve parola da dahildir.

## Ad Alanlarını İçe Aktar
Aspose.Tasks for .NET tarafından sağlanan işlevselliklerden verimli bir şekilde yararlanmak için .NET projenize gerekli ad alanlarını içe aktarın.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## 1. Adım: Belge Dizini Yolunu Tanımlayın
```csharp
String DataDir = "Your Document Directory";
```
## Adım 2: SharePoint Etki Alanı Adresini, Kullanıcı Adını ve Parolayı Ayarlayın
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## 3. Adım: Project Server Kimlik Bilgilerini Oluşturun
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Adım 4: Proje Dosyasını Yükleyin
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Adım 5: Proje Sunucusu Yöneticisini Başlatın
```csharp
var manager = new ProjectServerManager(credentials);
```
## Adım 6: Yeni Proje Oluşturun
```csharp
manager.CreateNewProject(newProject);
```
## Adım 7: Proje Listesini Alın
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Adım 8: Proje Listesini Yineleyin
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Çözüm
MS Project Server kimlik bilgilerinin etkili bir şekilde yönetilmesi, kolaylaştırılmış proje yönetimi için çok önemlidir. Aspose.Tasks for .NET, sağlam bir işlevsellik seti sağlayarak bu süreci basitleştirir. Kullanıcılar, bu eğitimde özetlenen adım adım kılavuzu takip ederek Aspose.Tasks for .NET'i projelerine sorunsuz bir şekilde entegre edebilir ve proje verilerine güvenli erişim ve manipülasyon sağlayabilirler.
## SSS'ler
### S: Aspose.Tasks for .NET, Microsoft Project Server'ın tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks for .NET, Microsoft Project Server'ın çeşitli sürümleriyle uyumlu olacak şekilde tasarlanmıştır ve kullanıcılara çok yönlülük ve esneklik sağlar.
### S: Aspose.Tasks for .NET'i mevcut .NET projeme entegre edebilir miyim?
C: Evet, Aspose.Tasks for .NET, mevcut .NET projelerine sorunsuz bir şekilde entegre edilebilir ve bu da verimli proje yönetimi yeteneklerini kolaylaştırır.
### S: Aspose.Tasks for .NET proje kaynaklarına erişim desteği sağlıyor mu?
C: Kesinlikle, Aspose.Tasks for .NET, proje kaynaklarına erişim ve bunları yönetme konusunda kapsamlı destek sunarak proje yönetimi verimliliğini artırır.
### S: Aspose.Tasks for .NET için herhangi bir lisanslama seçeneği mevcut mu?
C: Evet, Aspose.Tasks for .NET, deneme amaçlı geçici lisanslar ve ticari kullanım için tam lisanslar dahil olmak üzere esnek lisanslama seçenekleri sunar.
### S: Aspose.Tasks for .NET için nereden yardım veya destek alabilirim?
 C: Aspose.Tasks for .NET ile ilgili sorularınız veya yardım için şu adresteki destek forumunu ziyaret edebilirsiniz:[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15).## Kaynak Kodunu Tamamlayın