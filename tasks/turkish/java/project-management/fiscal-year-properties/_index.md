---
date: 2026-04-01
description: Aspose.Tasks for Java kullanarak XML kaydetmeyi, mali yılı ayarlamayı
  ve MPP'yi XML'ye dönüştürmeyi öğrenin. Kod örnekleriyle adım adım rehber.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Aspose.Tasks'te XML Kaydetme ve Mali Yılı Yönetme
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te XML Kaydetme ve Mali Yılı Yönetme
url: /tr/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XML Kaydetme ve Aspose.Tasks'te Mali Yılı Yönetme

## Giriş
Eğer Microsoft Project verilerinden oluşturulan **how to save xml** dosyalarına ihtiyacınız varsa, Aspose.Tasks for Java bunu temiz, lisans‑gerektirmeyen bir şekilde yapmanızı sağlar. Bu öğreticide bir MPP dosyasını yüklemeyi, mali yıl bilgilerini görüntülemeyi, mali yıl özelliklerini ayarlamayı ve sonunda **how to save xml** çıktısını almayı adım adım göstereceğiz. Ayrıca **how to set fiscal** ayrıntılarını ve **how to convert mpp** dosyalarını Microsoft Project'i hiç açmadan nasıl dönüştürebileceğinizi de göreceksiniz.

## Hızlı Yanıtlar
- **What does “manage fiscal year” mean in Aspose.Tasks?** Aspose.Tasks'te “manage fiscal year” ne anlama gelir? Bir projenin mali yıl başlangıç ayını tanımlamanıza ve mali yıl numaralandırmasını etkinleştirmenize olanak tanır.  
- **How to set fiscal year start month?** Mali yıl başlangıç ayını nasıl ayarlarsınız? Bir `Month` enum değeri (ör. `Month.JULY`) ile `Prj.FY_START_DATE` özelliğini kullanın.  
- **Can I load an MPP file?** Bir MPP dosyasını yükleyebilir miyim? Evet, *.mpp* dosyasının yolunu belirterek bir `Project` örneği oluşturmanız yeterlidir.  
- **How to convert MPP to XML?** MPP'yi XML'e nasıl dönüştürürüm? İstediğiniz özellikleri ayarladıktan sonra `project.save(..., SaveFileFormat.Xml)` çağırın.  
- **Do I need a license?** Lisans gerekir mi? Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için ticari bir lisans gereklidir.  

## Proje dosyalarında “manage fiscal year” nedir?
Mali yılı yönetmek, projenizin finansal raporlama için kullandığı takvimi yapılandırmak anlamına gelir. Bu, mali yılın başlangıç ayını ayarlamayı ve isteğe bağlı olarak mali yıl numaralandırmasını etkinleştirmeyi içerir; bu, tarihlerin raporlarda nasıl hesaplandığını ve gösterildiğini etkiler.

## Mali yıl yönetimi için neden Aspose.Tasks kullanmalı?
- **No Microsoft Project required** – proje dosyalarıyla doğrudan Java'da çalışın.  
- **Full control** – mali yıl başlangıcını ayarlayın, numaralandırmayı etkinleştirin ve formatları programlı olarak dönüştürün.  
- **Robust API** – büyük MPP dosyalarının güvenilir işlenmesi ve sorunsuz XML dışa aktarımı.  

## Önkoşullar
Başlamadan önce aşağıdakileri sağladığınızdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü olmalı.  
2. Aspose.Tasks for Java JAR – [buradan](https://releases.aspose.com/tasks/java/) indirin ve projenizin sınıf yoluna ekleyin.

## Paketleri İçe Aktarma
Başlamak için Java kaynak dosyanıza gerekli sınıfları içe aktarın:
```java
import com.aspose.tasks.*;
```

## MPP Dosyasını Yükleme ve Mali Yıl Bilgilerini Görüntüleme
Aşağıda süreci net, numaralı adımlara ayırıyoruz.

### Adım 1: Proje Dosyasını Yükle
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Burada belirtilen dizinden **load an MPP file** (`project.mpp`) yüklüyoruz. Bu, mali yıl ile ilgili herhangi bir işlemin ilk adımıdır.

### Adım 2: Mali Yıl Özelliklerini Görüntüle
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` ve `Prj.FISCAL_YEAR_START` özellikleri, **display fiscal year** ayrıntılarını göstermenizi sağlar ve “mevcut mali yapılandırma nedir?” sorusuna yanıt verir.

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
Bu adımda **how to set fiscal** ayarlarını yapıyoruz:
- `Month.JULY` mali yıl başlangıç ayını tanımlar.  
- `NullableBool(true)` mali yıl numaralandırmasını açar.  
- Son olarak, proje `SaveFileFormat.Xml` kullanılarak **converted MPP to XML** edilir.

### Adım 4: İşlemi Onayla
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Basit bir konsol mesajı, mali yılın yapılandırıldığını ve dosyanın kaydedildiğini onaylar.

## Neden Önemlidir
Projeyi XML olarak kaydetmek, kolayca ayrıştırılabilen, sürüm kontrolüne alınabilen veya diğer sistemlerle entegre edilebilen taşınabilir bir metin temelli temsil sağlar. Mali yıl ayarları doğru olduğunda, sonraki finansal raporlar ve panolar kuruluşunuzun muhasebe dönemleriyle uyumlu olur.

## Yaygın Kullanım Durumları
- **Financial reporting** – Proje takvimlerini bir mali takvimle hizalayın, ardından BI araçlarına dışa aktarın.  
- **Data migration** – Eski *.mpp* dosyalarını bulut tabanlı proje yönetim platformlarına aktarım için XML'e dönüştürün.  
- **Automated audits** – Programlı olarak her projenin doğru mali başlangıç ayını kullandığını doğrulayın.

## Sorun Giderme İpuçları ve Yaygın Tuzaklar
| Sorun | Çözüm |
|-------|----------|
| **Incorrect month value** | `Month` enum'ını (ör. `Month.JANUARY`) kullandığınızdan emin olun. |
| **File not found** | `dataDir`'in doğru klasöre işaret ettiğini ve dosya adının eşleştiğini doğrulayın. |
| **Saving fails** | Hedef dizinde yazma izinlerini ve `SaveFileFormat`'ın desteklendiğini kontrol edin. |
| **Fiscal year not reflected in XML** | Kaydetme sonrası XML'i açın ve `<FiscalYearStart>` ve `<FiscalYearNumbering>` düğümlerinin beklenen değerleri içerdiğini doğrulayın. |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java'ı diğer proje özelliklerini değiştirmek için kullanabilir miyim?**  
A: Evet, Aspose.Tasks mali yıl ayarlarının ötesinde çeşitli proje özelliklerini yönetmek için kapsamlı işlevsellik sunar.

**Q: Aspose.Tasks for Java farklı proje dosya formatlarıyla uyumlu mu?**  
A: Evet, MPP, XML ve diğerlerini içeren geniş bir format yelpazesini destekler.

**Q: Aspose.Tasks for Java kullanırken herhangi bir sorunla karşılaşırsam nasıl destek alabilirim?**  
A: [forum](https://forum.aspose.com/c/tasks/15) üzerinden Aspose.Tasks topluluğundan yardım isteyebilir veya doğrudan destek ekibiyle iletişime geçebilirsiniz.

**Q: Aspose.Tasks ücretsiz deneme sürümü sunuyor mu?**  
A: Evet, Aspose.Tasks'in ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**Q: Aspose.Tasks for Java için lisansı nereden satın alabilirim?**  
A: Aspose.Tasks for Java lisansını [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Aspose.Tasks for Java'da mali yıl özelliklerini yönetmek basittir. Yukarıdaki adımları izleyerek **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year**, ve **convert mpp to xml** işlemlerini güvenle yapabilirsiniz. Bu teknikleri, proje takvimlerinizi kuruluşunuzun finansal takvimine uyumlu tutmak ve sonraki işlemler için taşınabilir XML temsilleri oluşturmak için kullanın.

---

**Son Güncelleme:** 2026-04-01  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}