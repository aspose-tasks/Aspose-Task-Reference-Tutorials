---
title: Aspose.Tasks ile Farklı Birimlerdeki Görev Süresi
linktitle: Aspose.Tasks ile Farklı Birimlerdeki Görev Süresi
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks ile Java projelerinde görev süresi yönetimini keşfedin. Süreleri dakika, gün, saat, hafta ve ay cinsinden doğru bir şekilde hesaplayın ve dönüştürün.
weight: 32
url: /tr/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Farklı Birimlerdeki Görev Süresi

## giriiş
Proje yönetimi alanında görev süresini anlamak ve yönetmek kritik bir husustur. Aspose.Tasks for Java, bunun verimli bir şekilde üstesinden gelmek için güçlü bir araç seti sağlar. Bu eğitimde Aspose.Tasks'ı kullanarak çeşitli birimlerdeki görev sürelerini alma konusunda size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java Geliştirme Kiti (JDK) yüklü
-  Aspose.Tasks Java kütüphanesi için. İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/)
- Java programlamanın temel anlayışı
## Paketleri İçe Aktar
Java projenize Aspose.Tasks kütüphanesini ekleyin. Kodunuzun başına aşağıdaki import ifadesini ekleyin:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz Entegre Geliştirme Ortamında (IDE) yeni bir Java projesi oluşturarak başlayın. Aspose.Tasks kütüphanesini projenizin bağımlılıklarına eklediğinizden emin olun.
## Adım 2: Proje Şablonunu Okuyun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// MS Project şablon dosyasını okuyun
String fileName = dataDir + "project.xml";
// Giriş dosyasını Proje olarak okuyun
Project project = new Project(fileName);
```
 Değiştirildiğinden emin olun`"Your Document Directory"` proje dosyalarınızın gerçek yolu ile.
## 3. Adım: Bir Görevi Alın
```java
// Süresini farklı formatlarda hesaplamak için bir görev alın
Task task = project.getRootTask().getChildren().getById(1);
```
 Burada projeden bir görev alıyoruz. Ayarlamak`getById(1)` projenizin görev kimliğine göre.
## Adım 4: Dakika Olarak Süre
```java
// Dakika cinsinden süreyi alın
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Bu adım, görev süresini dakika cinsinden hesaplar.
## Adım 5: Gün Olarak Süre
```java
// Gün cinsinden süreyi alın
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Bu adım, görev süresini gün cinsinden hesaplar.
## Adım 6: Saat Olarak Süre
```java
// Süreyi Saat cinsinden alın
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Bu adım, görev süresini saat cinsinden hesaplar.
## Adım 7: Hafta Olarak Süre
```java
// Süreyi Hafta olarak alın
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Bu adım, görev süresini hafta cinsinden hesaplar.
## Adım 8: Ay Olarak Süre
```java
// Ay cinsinden süreyi alın
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Bu adım, görev süresini ay cinsinden hesaplar.
## Çözüm
Aspose.Tasks for Java ile görev sürelerini yönetmek artık çok kolay. Bu eğitim, farklı zaman birimleri hakkında netlik sağlayarak süreç boyunca size adım adım yol gösterdi.
## Sıkça Sorulan Sorular
### S: Aspose.Tasks for Java'yı herhangi bir Java IDE ile kullanabilir miyim?
Evet, Aspose.Tasks for Java, tüm Java Entegre Geliştirme Ortamı (IDE) ile uyumludur.
### S: Microsoft Project dosyasındaki bir görevin kimliğini nasıl edinebilirim?
Görev kimliklerini program aracılığıyla almak için proje dosyasını inceleyebilir veya Aspose.Tasks API'sini kullanabilirsiniz.
### S: Aspose.Tasks büyük ölçekli projelere uygun mudur?
Kesinlikle. Aspose.Tasks, çeşitli boyutlardaki projeleri verimli bir şekilde yönetmek için tasarlanmıştır.
### S: Daha fazla belgeyi nerede bulabilirim?
 Ziyaret edin[dokümantasyon](https://reference.aspose.com/tasks/java/)kapsamlı kaynaklar için.
### S: Satın almadan önce Aspose.Tasks for Java'yı deneyebilir miyim?
 Evet, keşfedebilirsiniz[ücretsiz deneme](https://releases.aspose.com/) yeteneklerini değerlendirmektir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
