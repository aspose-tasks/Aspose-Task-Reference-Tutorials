---
title: Aspose.Tasks ile Zahmetsiz MS Project Çevrimiçi Veri Okuma
linktitle: Aspose.Tasks'ta Project Online Verilerini Okuma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak Microsoft Project Online verilerini zahmetsizce nasıl okuyacağınızı öğrenin. Proje yönetimi yeteneklerinizi geliştirin.
weight: 13
url: /tr/java/project-data-reading/read-project-online/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Zahmetsiz MS Project Çevrimiçi Veri Okuma

## giriiş
Proje yönetimi alanında, Microsoft Project Online verilerinin verimli bir şekilde kullanılması, operasyonların kolaylaştırılması için çok önemlidir. Aspose.Tasks for Java, bu tür verileri zahmetsizce okumak için güçlü bir çözüm sunar. Bu eğitim, MS Project Online verilerine sorunsuz bir şekilde erişmek ve bunları yönetmek için Aspose.Tasks'tan yararlanmayı ele alıyor.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Java programlarını derlemek ve çalıştırmak için JDK'yı yükleyin.
2.  Aspose.Tasks for Java Library: Aspose.Tasks kütüphanesini indirin ve Java projenize ekleyin. adresinden edinebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online Hesabı: MS Project Online verilerine erişmek için geçerli kimlik bilgileri edinin.
4. SharePoint Etki Alanı Adresi: MS Project Online verilerinizin bulunduğu SharePoint etki alanı adresi.
5. Kullanıcı Adı ve Parola: MS Project Online'a erişimin doğrulanması için kimlik bilgileri.
## Paketleri İçe Aktar
Sorunsuz entegrasyon için gerekli Aspose.Tasks paketlerini Java projenize aktarın:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 1. Adım: SharePoint Etki Alanı Adresini, Kullanıcı Adını ve Parolayı Ayarlayın
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Yer değiştirmek`"https://contoso.sharepoint.com"` SharePoint etki alanı adresinizle,`"admin@contoso.onmicrosoft.com"` kullanıcı adınızla ve`"MyPassword"` şifrenizle.
## Adım 2: Project Server Kimlik Bilgileriyle Kimlik Doğrulama
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Yaratmak`ProjectServerCredentials` SharePoint etki alanı adresi, kullanıcı adı ve parolayla nesne. Sonra başlat`ProjectServerManager` bu kimlik bilgileri ile.
## Adım 3: Proje Listesini Alın ve Bilgileri Görüntüleyin
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Buradan elde edilen proje listesini yineleyin`reader.getProjectList()` ve ad, oluşturulma tarihi ve son kaydedilme tarihi gibi proje ayrıntılarını görüntüleyin.
## Adım 4: Bireysel Projeleri Yükleyin ve Çıktı Kaynak Sayısını
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Her proje için şunu kullanarak yükleyin:`reader.getProject(p.getId())` ve ilişkili kaynakların sayısıyla birlikte proje adının çıktısını alın.

## Çözüm
Aspose.Tasks for Java, MS Project Online verilerini okuma sürecini basitleştirerek geliştiricilere proje yönetimi görevlerini kolaylaştırmak için güçlü bir araç seti sunar. Bu öğreticiyi takip ederek Aspose.Tasks'i Java uygulamalarınıza verimli bir şekilde entegre ederek proje verilerine kolaylıkla erişebilir ve bunları yönetebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java'yı MS Project Online verilerini değiştirmek için kullanabilir miyim?
C: Evet, Aspose.Tasks, MS Project Online verilerini programlı olarak okumak ve değiştirmek için kapsamlı yetenekler sağlar.
### S: Aspose.Tasks diğer proje yönetimi dosya formatlarını destekliyor mu?
C: Aspose.Tasks kesinlikle MPP, XML ve daha fazlasını içeren çeşitli dosya formatlarını destekleyerek çeşitli proje yönetim sistemleriyle uyumluluk sağlar.
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz.[Burada](https://releases.aspose.com/) Aspose.Tasks'ın özelliklerini ve işlevlerini keşfetmek için.
### S: Aspose.Tasks for Java'nın kapsamlı belgelerini nerede bulabilirim?
 C: Ayrıntılı belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/java/)Aspose.Tasks'ı Java projelerinizde kullanma konusunda kapsamlı rehberlik için.
### S: Aspose.Tasks for Java için hangi destek seçenekleri mevcut?
 C: Herhangi bir sorunla karşılaşırsanız veya sorularınız varsa Aspose.Tasks topluluk forumundan yardım isteyebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
