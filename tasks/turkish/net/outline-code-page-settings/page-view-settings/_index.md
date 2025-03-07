---
title: Aspose.Tasks'ta MS Project Sayfa Görünümü Ayarlarını Özelleştirin
linktitle: Aspose.Tasks'ta Sayfa Görünümü Ayarlarını Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Microsoft Project belgelerinizin yazdırma formatını uyarlamak için Aspose.Tasks for .NET'te sayfa görüntüleme ayarlarını nasıl yapılandıracağınızı öğrenin.
weight: 21
url: /tr/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MS Project Sayfa Görünümü Ayarlarını Özelleştirin

## giriiş
Microsoft Project, proje yönetimi için güçlü bir araçtır ancak bazen projenizin görüntülenme ve yazdırılma şeklini özelleştirmeniz gerekir. Aspose.Tasks for .NET ile sayfa görüntüleme ayarlarını özel gereksinimlerinizi karşılayacak şekilde kolayca yapılandırabilirsiniz. Bu eğitimde size süreç boyunca adım adım rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kitaplığını indirip yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Dosyası: Sayfa görüntüleme ayarlarını yapılandırmak istediğiniz bir Microsoft Project dosyasını hazır bulundurun.

## Ad Alanlarını İçe Aktar
Öncelikle .NET projenizde Aspose.Tasks ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Adım 1: Proje Dosyasını Yükleyin
 Microsoft Project dosyanızı bir örneğine yükleyerek başlayın.`Project` sınıf.
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Adım 2: İlk Sütun Sayısını Ayarlayın
Tüm sayfalara yazdırılacak ilk sütunların sayısını belirtin.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## 3. Adım: Notları Yazdırın
Notların projeyle birlikte yazdırılıp yazdırılmayacağını seçin.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Adım 4: Zaman Ölçeğini Sayfanın Sonuna Sığdır
Yazdırırken zaman ölçeğini sayfanın sonuna sığdırıp sığdırmayacağınıza karar verin.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Adım 5: Tüm Sayfa Sütunlarını Yazdırın
Bir görünümün tüm sayfa sütunlarının yazdırılıp yazdırılmayacağını belirtin.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Adım 6: Boş Sayfaları Yazdırın
Bir görünümün boş sayfalarının yazdırılıp yazdırılmayacağını seçin.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Adım 7: Tüm Sayfalara İlk Sütunları Yazdırın
Belirtilen sayıda ilk sütunun tüm sayfalara yazdırılıp yazdırılmayacağını ayarlayın.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Adım 8: Projeyi Yapılandırılmış Ayarlarla Kaydetme
Son olarak, PDF gibi çıktı biçimini belirterek projeyi yapılandırılmış sayfa görüntüleme ayarlarıyla kaydedin.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Çözüm
Aspose.Tasks for .NET'te Microsoft Project sayfa görüntüleme ayarlarını yapılandırmak basittir ve yazdırma formatını tam ihtiyaçlarınıza göre uyarlamanıza olanak tanır. Bu eğitimde özetlenen adımları izleyerek proje belgelerinizin tam olarak gerektiği gibi sunulmasını sağlayabilirsiniz.
## SSS'ler
### S: PDF'nin yanı sıra diğer dosya formatları için de sayfa görüntüleme ayarlarını yapılandırabilir miyim?
C: Evet, Aspose.Tasks, projeleri kaydetmek için XLSX, MPP ve HTML dahil olmak üzere çeşitli dosya formatlarını destekler.
### S: Yazdırabileceğim sütun sayısında herhangi bir sınırlama var mı?
C: Aspose.Tasks, gereksinimlerinize göre yazdırılacak sütun sayısını özelleştirmenize olanak tanır.
### S: Farklı projeler için farklı sayfa görüntüleme ayarları uygulayabilir miyim?
C: Evet, üzerinde çalıştığınız her proje dosyası için sayfa görüntüleme ayarlarını bağımsız olarak ayarlayabilirsiniz.
### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Aspose.Tasks, Microsoft Project 2003 ve sonraki sürümlerle uyumluluk sunar.
### S: Aspose.Tasks için nereden daha fazla yardım veya destek bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Kullanım sırasında karşılaştığınız her türlü soru veya sorun için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
