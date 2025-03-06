---
title: Aspose.Tasks ile Kaynak Atama Yüzdelerini Hesaplayın
linktitle: Aspose.Tasks'ta Kaynak Atamaları için Yüzdeleri Hesaplayın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ı kullanarak Java projelerinde kaynak atamaları için yüzdeleri verimli bir şekilde nasıl hesaplayacağınızı öğrenin ve proje yönetimi görevlerini basitleştirin.
weight: 13
url: /tr/java/resource-assignments/calculate-percentages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Kaynak Atama Yüzdelerini Hesaplayın

## giriiş
Proje yönetiminde kaynak atamalarının doğru bir şekilde hesaplanması, görevlerin zamanında tamamlanması ve kaynakların verimli bir şekilde tahsis edilmesi açısından çok önemlidir. Aspose.Tasks for Java, bu süreci kolaylaştırmak için güçlü araçlar sağlayarak geliştiricilerin kaynak atamalarının yüzdelerini kolaylıkla hesaplamasına olanak tanır.
## Önkoşullar
Aspose.Tasks for Java kullanarak kaynak atamalarının yüzdelerini hesaplamaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
### Java Geliştirme Ortamı
 Sisteminizde Java Development Kit'in (JDK) kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks for Java Library
 Aspose.Tasks for Java kütüphanesini indirip yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
### Entegre Geliştirme Ortamı (IDE)
Kodlama için IntelliJ IDEA, Eclipse veya NetBeans gibi tercih ettiğiniz bir IDE'yi seçin. 

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java kodunuza aktarın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 1. Adım: Veri dizininizi ayarlayın
Proje verilerinizin bulunduğu belirlenmiş bir dizininiz olduğundan emin olun. Proje dosyalarınıza erişmek için bu dizini kullanacaksınız.
```java
String dataDir = "Your Data Directory";
```
## Adım 2: Proje dosyasını yükleyin
 Bir örnek oluştur`Project` nesnesini oluşturun ve belirtilen veri dizinini kullanarak proje dosyanızı yükleyin.
```java
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
## 3. Adım: Kaynak atamalarını yineleyin
Her atamanın ayrıntılarına erişmek için projedeki tüm kaynak atamaları arasında geçiş yapın.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Her kaynak atamasında işlemleri gerçekleştirin
}
```
## Adım 4: Tamamlanan işin yüzdesini hesaplayın
Aspose.Tasks'ı kullanarak her kaynak ataması için tamamlanan iş yüzdesini alın.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    System.out.println(ra.get(Asn.PERCENT_WORK_COMPLETE).toString());
}
```

## Çözüm
Bu basit adımları izleyerek Aspose.Tasks for Java'da kaynak atamalarının yüzdelerini zahmetsizce hesaplayabilir, proje yönetimi iş akışınızı düzenleyebilir ve optimum kaynak kullanımını sağlayabilirsiniz.
## SSS'ler
### S: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks karmaşık proje yapılarının kolaylıkla yönetilmesini destekleyerek her ölçekteki projeyi yönetmenize olanak tanır.
### S: Aspose.Tasks kurumsal düzeyde proje yönetimine uygun mu?
C: Kesinlikle Aspose.Tasks, kaynak tahsisi, planlama ve raporlama dahil olmak üzere kurumsal düzeyde proje yönetimi için özel olarak tasarlanmış güçlü özellikler sunar.
### S: Aspose.Tasks'ı diğer Java kütüphaneleriyle entegre edebilir miyim?
C: Kesinlikle Aspose.Tasks, proje yönetimi yeteneklerinizi geliştirmek için diğer Java kitaplıklarıyla sorunsuz bir şekilde entegre edilebilir.
### S: Aspose.Tasks müşteri desteği sağlıyor mu?
 C: Evet, Aspose.Tasks, forumları aracılığıyla özel müşteri desteği sunuyor. Yardım bulabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ı ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
