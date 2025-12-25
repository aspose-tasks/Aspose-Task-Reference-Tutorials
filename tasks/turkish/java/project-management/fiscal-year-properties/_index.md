---
date: 2025-12-25
description: Aspose.Tasks for Java kullanarak mali yıl özelliklerini nasıl yöneteceğinizi
  ve MPP dosyalarını verimli bir şekilde nasıl yükleyeceğinizi öğrenin. Örneklerle
  adım adım kılavuz.
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Mali Yıl Özelliklerini Yönet
url: /tr/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Mali Yıl Özelliklerini Yönetme

## Giriş
Aspose.Tasks, geliştiricilerin **mali yıl** ayarlarını yönetmelerine, MPP dosyalarını yüklemelerine ve proje verilerini sadece birkaç satır kodla XML'e dönüştürmelerine olanak tanıyan güçlü bir Java kütüphanesidir. Bu öğreticide, mali yıl özelliklerini nasıl ayarlayacağınızı, mali yıl bilgilerini nasıl görüntüleyeceğinizi ve sonucu nasıl kaydedeceğinizi tam olarak göreceksiniz — kodunuzu temiz ve sürdürülebilir tutarken.

## Hızlı Yanıtlar
- **Aspose.Tasks'te “mali yılı yönetmek” ne anlama geliyor?** Proje için mali yıl başlangıç ayını tanımlamanıza ve mali yıl numaralandırmasını etkinleştirmenize olanak tanır.  
- **Mali yıl başlangıç ayını nasıl ayarlarsınız?** `Prj.FY_START_DATE` özelliğini bir `Month` enum değeriyle (ör. `Month.JULY`) kullanın.  
- **Bir MPP dosyasını yükleyebilir miyim?** Evet, *.mpp* dosyasının yolunu belirterek bir `Project` örneği oluşturmanız yeterlidir.  
- **MPP'yi XML'e nasıl dönüştürürüm?** İstediğiniz özellikleri ayarladıktan sonra `project.save(..., SaveFileFormat.Xml)` metodunu çağırın.  
- **Bir lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü mevcuttur; üretim kullanımı için ticari bir lisans gereklidir.

## Proje dosyalarında “mali yılı yönetmek” ne anlama gelir?
Mali yılı yönetmek, projenizin finansal raporlama için kullandığı takvimi yapılandırmak anlamına gelir. Bu, mali yılın başlangıç ayını ayarlamayı ve isteğe bağlı olarak mali yıl numaralandırmasını etkinleştirmeyi içerir; bu da tarihlerin raporlarda nasıl hesaplandığını ve gösterildiğini etkiler.

## Mali yıl işleme için Aspose.Tasks'i neden kullanmalısınız?
- **Microsoft Project gerekmez** – proje dosyalarıyla doğrudan Java içinde çalışın.  
- **Tam kontrol** – mali yıl başlangıcını ayarlayın, numaralandırmayı etkinleştirin ve formatları programlı olarak dönüştürün.  
- **Sağlam API** – büyük MPP dosyalarını güvenilir bir şekilde işleyin ve sorunsuz XML dışa aktarımı yapın.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde yüklü Java Development Kit (JDK).  
2. Aspose.Tasks for Java JAR – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin ve projenizin sınıf yoluna ekleyin.

## Paketleri İçe Aktarma
Başlamak için Java kaynak dosyanıza gerekli sınıfları içe aktarın:
```java
import com.aspose.tasks.*;
```

## Bir MPP dosyasını nasıl yükler ve mali yıl bilgilerini görüntüleriz
Aşağıda süreci net, numaralı adımlara ayırıyoruz.

### Adım 1: Proje Dosyasını Yükle
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Burada belirtilen dizinden bir **MPP dosyası** (`project.mpp`) **yüklenir**. Bu, mali yıl ile ilgili herhangi bir işlemde ilk adımdır.

### Adım 2: Mali Yıl Özelliklerini Görüntüle
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` ve `Prj.FISCAL_YEAR_START` özellikleri, **mali yıl** ayrıntılarını **görüntülemenizi** sağlar ve “mevcut mali yapılandırma nedir?” sorusuna yanıt verir.

### Adım 3: Mali Yıl Başlangıcını Ayarla ve Numaralandırmayı Etkinleştir
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Bu adımda **mali** ayarları nasıl belirleyeceğinizi gösteriyoruz:
- `Month.JULY`, mali yılın başlangıç ayını tanımlar.  
- `NullableBool(true)`, mali yıl numaralandırmasını etkinleştirir.  
- Son olarak, proje `SaveFileFormat.Xml` kullanılarak **MPP'den XML'e dönüştürülür**.

### Adım 4: İşlemi Onayla
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Basit bir konsol mesajı, mali yılın yapılandırıldığını ve dosyanın kaydedildiğini onaylar.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Yanlış ay değeri** | `Month` enum'ını kullandığınızdan emin olun (ör. `Month.JANUARY`). |
| **Dosya bulunamadı** | `dataDir`'in doğru klasöre işaret ettiğini ve dosya adının eşleştiğini doğrulayın. |
| **Kaydetme başarısız** | Hedef klasörde yazma izinlerini ve `SaveFileFormat`'ın desteklendiğini kontrol edin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java'ı diğer proje özelliklerini değiştirmek için kullanabilir miyim?**  
C: Evet, Aspose.Tasks, mali yıl ayarlarının ötesinde çeşitli proje özelliklerini yönetmek için kapsamlı işlevsellik sağlar.

**S: Aspose.Tasks for Java farklı proje dosya formatlarıyla uyumlu mu?**  
C: Evet, MPP, XML ve diğer birçok formatı destekler.

**S: Aspose.Tasks for Java kullanırken bir sorunla karşılaşırsam nasıl destek alabilirim?**  
C: Aspose.Tasks topluluğundan [forum](https://forum.aspose.com/c/tasks/15) üzerinden yardım isteyebilir veya doğrudan destek ekibiyle iletişime geçebilirsiniz.

**S: Aspose.Tasks ücretsiz deneme sürümü sunuyor mu?**  
C: Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.Tasks for Java için lisans nereden satın alınır?**  
C: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Aspose.Tasks for Java'da mali yıl özelliklerini yönetmek oldukça basittir. Yukarıdaki adımları izleyerek **mali yılı yönetebilir**, **MPP dosyalarını yükleyebilir**, **mali yıl** detaylarını **görüntüleyebilir** ve **MPP'yi XML'e dönüştürebilirsiniz**. Bu teknikleri kullanarak proje takvimlerinizi organizasyonunuzun finansal takvimine uyumlu tutun.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}