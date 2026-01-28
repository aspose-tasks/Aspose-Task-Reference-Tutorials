---
date: 2026-01-28
description: Aspose.Tasks for Java kullanarak genişletilmiş görev niteliklerini nasıl
  okuyacağınızı öğrenin ve özel alan türünü verimli bir şekilde değiştirin.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Genişletilmiş Görev Niteliklerini Okuma
url: /tr/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Microsoft Project dosyalarından Aspose.Tasks for Java ile Genişletilmiş Görev Niteliklerini Okuma

## Giriş
Bu kapsamlı öğreticide, Microsoft Project dosyalarından **genişletilmiş görev niteliklerini** Aspose.Tasks Java kütüphanesini kullanarak nasıl okuyacağınızı keşfedeceksiniz. Raporlama aracı oluşturuyor, verileri senkronize ediyor ya da yalnızca özel alanlara daha derin bir bakışa ihtiyaç duyuyorsanız, bu özelliği ustalaşmak, bir projede depolanan her bilgiyi çıkarmanızı sağlayacaktır. Gerekli kurulum adımlarını gösterecek, nitelikleri işlerken özel alan tipini nasıl değiştireceğinizi anlatacak ve yaygın hatalardan kaçınmanız için pratik ipuçları sunacağız.

## Hızlı Yanıtlar
- **“Genişletilmiş görev niteliklerini okuma” ne anlama geliyor?** Bir Project dosyasındaki varsayılan görev özelliklerinin ötesinde tanımlanmış özel alan değerlerini çıkarmak demektir.  
- **Bu niteliklere erişimi sağlayan sınıf hangisidir?** Aspose.Tasks içinde `ExtendedAttribute` sınıfı.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Çalışma zamanında nitelik tipini değiştirebilir miyim?** Evet – `CustomFieldType` temelinde **özel alan tipini değiştirmek** için `switch` ifadesini kullanın.  
- **Java 8 ve üzeriyle uyumlu mu?** Kesinlikle, API JDK 8+’ı destekler.

## Genişletilmiş görev nitelikleri nedir?
Genişletilmiş görev nitelikleri, Microsoft Project’teki standart görev özelliklerine ek olarak kullanıcı tarafından tanımlanmış alanlardır (metin, tarih, sayı, işaret vb.). Aspose.Tasks, her `Task` nesnesine eklenmiş `ExtendedAttribute` koleksiyonu aracılığıyla bu niteliklere programatik olarak erişim ve değiştirme imkanı sunar.

## Neden genişletilmiş görev niteliklerini okumalıyız?
- **Tam görünürlük:** Paydaşların takvime eklediği özel verilere ulaşın.  
- **Otomasyon:** Panolar doldurun, özel raporlar oluşturun veya verileri manuel dışa aktarım olmadan başka sistemlere taşıyın.  
- **Esneklik:** Metin, tarih, süre, maliyet, işaret gibi herhangi bir özel alan tipini, her durumu uygun şekilde ele alarak çalışın.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:
- Java programlamaya temel düzeyde hâkimiyet.  
- Makinenizde Java Development Kit (JDK) yüklü.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.

## Paketleri İçe Aktarma
Aspose.Tasks projesi için gerekli sınıfları içe aktararak başlayın:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Adım 1: Görev ve Genişletilmiş Niteliklere Erişim
Bir Project dosyasını yükleyin ve her görevin genişletilmiş niteliklerine ulaşmak için döngüye alın:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Adım 2: Alan Kimliği ve Değer GUID’sini Alma
Hangi özel alanla çalıştığınızı anlamanıza yardımcı olacak iç tanımlayıcıları yazdırın:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Adım 3: Genişletilmiş görev niteliklerini okurken özel alan tipini nasıl değiştirebilirim
Her olası veri tipini doğru şekilde işlemek için `CustomFieldType` üzerine bir `switch` ifadesi kullanın:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Bu adımları projenizdeki her görev için tekrarlayarak tüm genişletilmiş görev niteliklerini keşfedebilir ve manipüle edebilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Null değerler döndürülüyor** | Özel alanın kaynak .mpp dosyasında gerçekten doldurulduğunu doğrulayın. |
| **Yanlış tip gösteriliyor** | `switch` ifadesinde doğru `CustomFieldType` kullandığınızdan emin olun; tip eşleşmezse varsayılan değerler gösterilir. |
| **Büyük projelerde performans yavaşlıyor** | Görevleri partiler halinde işleyin veya `project.getRootTask().getChildren().stream()` ile uygun koşulları ekleyerek yalnızca ihtiyaç duyduğunuz görevleri filtreleyin. |

## Sıkça Sorulan Sorular
### Genişletilmiş görev niteliklerini programatik olarak değiştirebilir miyim?
Evet, Aspose.Tasks for Java ile genişletilmiş görev niteliklerini değiştirebilirsiniz. Ayrıntılı talimatlar için dokümantasyona bakın.

### Deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümüne **[buradan](https://releases.aspose.com/)** ulaşabilirsiniz.

### Aspose.Tasks for Java için destek nereden alınır?
Destek için **[Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

### Geçici bir lisans nasıl alınır?
Geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** temin edebilirsiniz.

### Aspose.Tasks for Java tam sürümü nereden satın alınır?
Tam sürümü **[buradan](https://purchase.aspose.com/buy)** satın alabilirsiniz.

---

**Son Güncelleme:** 2026-01-28  
**Test Edilen Versiyon:** Aspose.Tasks Java API (en son kararlı sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}