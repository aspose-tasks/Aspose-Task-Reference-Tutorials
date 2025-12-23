---
date: 2025-12-23
description: Aspose.Tasks for Java kullanarak MS Project’te görev bağımlılıklarını
  oluşturmayı ve kritik yolu hesaplamayı öğrenin. Proje yönetimi için adım adım kılavuz.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görev Bağımlılıkları Oluşturun ve Kritik Yolu Hesaplayın
url: /tr/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görev Bağımlılıkları Oluşturma ve Aspose.Tasks'te Kritik Yolu Hesaplama

## Giriş
Bu öğreticide, **görev bağımlılıklarını nasıl oluşturacağınızı** ve Aspose.Tasks for Java kullanarak bir MS Project dosyasında kritik yolu nasıl hesaplayacağınızı öğreneceksiniz. Kritik yolu anlamak ve görselleştirmek, projenizi zaman çizelgesinde tutmanıza yardımcı olur; görevleri doğru şekilde bağlamak ise herhangi bir gecikmenin anında görülmesini sağlar. Ortamı kurmaktan son kritik yolu görüntülemeye kadar tüm süreci adım adım inceleyelim.

## Hızlı Yanıtlar
- **İlk adım nedir?** Java projenizi kurun ve Aspose.Tasks kütüphanesini ekleyin.  
- **Hangi mod etkinleştirilmeli?** `CalculationMode.Automatic` (otomatik hesaplamayı ayarlayın).  
- **Görevleri nasıl bağlarım?** `project.getTaskLinks().add(...)` kullanarak görev bağımlılıkları oluşturun.  
- **Kritik yolu nasıl görüntülerim?** `project.getCriticalPath()` üzerinde döngü kurarak her görev adını yazdırın.  
- **Lisans gerekir mi?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.

## “Görev bağımlılıkları oluşturma” nedir?
Görev bağımlılıkları oluşturmak, görevler arasında (ör. Bitiş‑Başlangıç) ilişkiler tanımlamak anlamına gelir; böylece takvim gerçek dünya kısıtlamalarını yansıtır. Aspose.Tasks'te bu, `TaskLink` nesneleri aracılığıyla yapılır.

## MS Project'te kritik yolu neden hesaplamalıyız?
**MS Project kritik yolu**, projenin minimum süresini belirleyen bağımlı görevlerin en uzun dizisini gösterir. Bunu hesaplayarak, genel zaman çizelgesini etkilemeden kayması mümkün olmayan görevleri hızlıca tespit edebilirsiniz—etkili **project management Java** uygulamaları için hayati öneme sahiptir.

## Ön Koşullar
1. Sisteminizde Java Development Kit (JDK) yüklü olmalıdır.  
2. Aspose.Tasks for Java kütüphanesini indirip projenize ekleyin. Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

## Paketleri İçe Aktarma
Başlamak için, Java sınıfınızda gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.*;
```

## Otomatik Hesaplamayı Nasıl Ayarlarım?
Hesaplama modunu otomatik olarak ayarlamak, görevlerde veya bağlantılarda yapılan herhangi bir değişikliğin takvimi, kritik yolu da dahil olmak üzere anında güncellemesini sağlar.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Adım‑Adım Kılavuz

### Adım 1: Veri Dizini Ayarlama
MS Project dosyanızın bulunduğu klasörün yolunu tanımlayın.
```java
String dataDir = "Your Data Directory";
```

### Adım 2: MS Project Dosyasını Yükleme
Mevcut proje dosyasını (ör. *New project 2013.mpp*) Aspose.Tasks kullanarak yükleyin.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Adım 3: Görev Ekleme
Daha sonra birbirine bağlayacağımız üç basit alt görev oluşturun.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Adım 4: Görev Bağlantıları Oluşturma (görev bağımlılıkları oluşturma)
Görevler arasındaki bağımlılıkları tanımlayın. Burada en yaygın tip olan Bitiş‑Başlangıç bağlantısını kullanıyoruz.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Adım 5: Kritik Yolu Görüntüleme (kritik yolu gösterme)
Kritik yolu alın ve yazdırın. `getCriticalPath()` metodu, kritik zinciri oluşturan görevlerin listesini döndürür.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Adım 6: Tamamlanmayı Onaylama
İşlem tamamlandığında dostça bir mesaj gösterin.
```java
System.out.println("Process completed Successfully");
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Çözüm |
|-------|----------|
| **Kritik yol boş** | Bağlantıları eklemeden önce `CalculationMode.Automatic` ayarlandığından emin olun. |
| **Görevler bağlanmadı** | `TaskLink` nesnelerini her bağımlılık için eklediğinizi doğrulayın. |
| **Lisans istisnası** | `Project` örneğini oluşturmadan önce geçerli bir Aspose.Tasks lisansı yükleyin. |

## SSS

### S: Aspose.Tasks for Java'ı herhangi bir MS Project dosya sürümüyle kullanabilir miyim?
C: Evet, Aspose.Tasks for Java .mpp dosyaları dahil olmak üzere MS Project 2003'ten MS Project 2019'a kadar çeşitli sürümleri destekler.  

### S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?
C: Evet, [buradan](https://releases.aspose.com/) ücretsiz bir deneme indirebilirsiniz.  

### S: Aspose.Tasks for Java için destek nereden bulunur?
C: Destek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.  

### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
C: Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.  

### S: Aspose.Tasks for Java'ı nasıl satın alabilirim?
C: Aspose.Tasks for Java'ı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Bu adımları izleyerek **görev bağımlılıklarını oluşturmuş**, **otomatik hesaplamayı ayarlamış** ve MS Project dosyanız için **kritik yolu başarıyla görüntülemiş** oldunuz. Bu iş akışı, takvim mantığı üzerinde tam kontrol sağlar ve Java‑tabanlı **project management** kodu kullanarak projelerinizi zamanında tutmanıza yardımcı olur.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}