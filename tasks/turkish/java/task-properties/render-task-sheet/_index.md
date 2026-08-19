---
date: 2026-02-26
description: Aspose.Tasks for Java kullanarak projeyi PDF olarak kaydetmeyi ve bir
  görev sayfası oluşturmayı öğrenin. Bu adım adım kılavuzla MPP'yi hızlıca PDF'ye
  dışa aktarın.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projeyi PDF Olarak Kaydet – Aspose.Tasks for Java ile Görev Sayfasını Render
  Et
url: /tr/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi PDF Olarak Kaydet – Aspose.Tasks ile Görev Sayfası Oluşturma

## Giriş
Bu kapsamlı rehberde **projeyi PDF olarak kaydet** ve Aspose.Tasks for Java ile bir görev sayfası oluşturmayı öğreneceksiniz. Bir MPP dosyasını PDF’ye dışa aktarıp paydaş incelemeleri için sunmanız ya da raporlama amacıyla temiz bir görev sayfası oluşturmanız gerektiğinde, bu öğretici her adımı gösterir, her ayarın neden önemli olduğunu açıklar ve çalıştırmanız gereken tam kodu sunar.

## Hızlı Yanıtlar
- **“projeyi pdf olarak kaydet” ne yapar?** Bir Microsoft Project dosyasını (MPP) PDF belgesine dönüştürür, isteğe bağlı olarak bir görev sayfası biçiminde formatlar.  
- **Görev‑sayfası PDF’si için hangi format kullanılır?** `PdfSaveOptions` içinde `PresentationFormat.TaskSheet` seçeneği.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Üretim ortamı için geçici ya da tam lisans gerekir; değerlendirme için ücretsiz deneme sürümü yeterlidir.  
- **Ana önkoşullar nelerdir?** Java JDK, Aspose.Tasks for Java kütüphanesi ve geçerli bir proje dosyası (örn. *.mpp).  
- **PDF düzenini özelleştirebilir miyim?** Evet, Aspose.Tasks birçok `PdfSaveOptions` özelliğiyle stil ve sayfa ayarları sunar.

## “projeyi pdf olarak kaydet” nedir?
Projeyi PDF olarak kaydetmek, iç proje verilerini taşınabilir, yalnızca okunabilir bir belgeye dönüştürür. Bu, Microsoft Project yüklü olmayan paydaşlarla takvim, görev sayfası veya durum raporlarını paylaşmak için idealdir.

## Neden bir görev sayfası oluşturulur?
Bir görev sayfası, her görevi tablo şeklinde gösterir; ID, ad, başlangıç/bitiş tarihleri ve diğer alanları içerir. PDF’ye render edilmesi, platformlar arasında tutarlı formatlama sağlar ve yazdırmayı ya da diğer belgelere eklemeyi kolaylaştırır.

## Önkoşullar
Başlamadan önce şunların yüklü olduğundan emin olun:

1. **Java Development Kit (JDK)** – en son sürüm yüklü ve `java`/`javac` PATH’te erişilebilir olmalı.  
2. **Aspose.Tasks for Java** – kütüphaneyi resmi siteden [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. Dönüştürmek istediğiniz geçerli **proje dosyası** (`*.mpp`), örneğin `NewProductDev.mpp`.  

## Paketleri İçe Aktarma
İlk olarak gerekli Aspose.Tasks sınıflarını içe aktarın. Bu importlar PDF kaydetme seçeneklerine, sunum formatlarına ve temel `Project` nesnesine erişim sağlar.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Ayarlayın
Kaynak MPP dosyasının bulunduğu ve oluşturulacak PDF’nin yazılacağı klasörü tanımlayın. Mutlak ya da göreli bir yol kullanabilirsiniz; sadece klasörün var olduğundan emin olun.

```java
String dataDir = "Your Document Directory";
```

### Adım 2: Proje Dosyasını Yükleyin
Mevcut MPP dosyasını yükleyerek bir `Project` örneği oluşturun. Bu nesne, proje yapısının bellekteki tam temsilini sağlar.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Adım 3: Kaydetme Seçeneklerini Yapılandırın – MPP’yi PDF’ye Dışa Aktarın
`PdfSaveOptions` nesnesini oluşturun ve Aspose.Tasks’e PDF’nin **görev sayfası** olarak render edilmesini söyleyin. Bu, *export project pdf* senaryosu için ana adımdır.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Adım 4: Projeyi Görev Sayfası Olarak Kaydedin – Projeyi PDF Olarak Kaydet
`Project` nesnesinin `save` metodunu çağırarak hedef dosya adını ve yapılandırılmış seçenekleri geçin. Bu işlem **MPP dosyasını görev sayfası biçiminde bir PDF’ye dönüştürür**.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Adım 5: Sonucu İnceleyin
Belirttiğiniz dizine (`dataDir`) gidin. `taskSheet.pdf` adında, tüm görevlerin düzenli bir şekilde listelendiği PDF dosyasını görmelisiniz. Dönüşümün başarılı olduğunu doğrulamak için herhangi bir PDF görüntüleyiciyle açın.

## Yaygın Sorunlar ve Çözümler
- **FileNotFoundException** – `dataDir` sonunun bir yol ayırıcı (`/` veya `\\`) ile bittiğinden ve MPP dosya adının doğru olduğundan emin olun.  
- **LicenseException** – Lisans hatası alıyorsanız, herhangi bir Aspose.Tasks API çağrısından önce geçici ya da satın alınmış bir lisans uygulayın.  
- **Boş PDF** – Projenin gerçekten görev içerdiğini kontrol edin; boş bir proje boş PDF üretir.

## Sık Sorulan Sorular

**S: Aspose.Tasks tüm Java sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks geniş bir Java sürüm yelpazesiyle çalışır. Ayrıntılar için [belgelere](https://reference.aspose.com/tasks/java/) bakın.

**S: Aspose.Tasks’i satın almadan deneyebilir miyim?**  
C: Kesinlikle! Ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) keşfedin.

**S: Aspose.Tasks için destek nereden bulabilirim?**  
C: Destek ve tartışmalar için Aspose.Tasks topluluğuna [forumda](https://forum.aspose.com/c/tasks/15) katılın.

**S: Aspose.Tasks için geçici bir lisans nasıl alınır?**  
C: Geçici lisansınızı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Aspose.Tasks for Java’ı nereden satın alabilirim?**  
C: Aspose.Tasks for Java’ı [buradan](https://purchase.aspose.com/buy) satın alın.

## Sonuç
Bu adımları izleyerek **projeyi PDF olarak kaydet** ve özellikle bir görev sayfası render etme işlemini Aspose.Tasks for Java kullanarak öğrendiniz. Bu özellik, *MPP’yi PDF’ye dışa aktarma* sürecini hızlıca gerçekleştirmenizi, okunabilir proje özetlerini paylaşmanızı ve proje verilerini daha geniş raporlama iş akışlarına entegre etmenizi sağlar.

---

**Son Güncelleme:** 2026-02-26  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}