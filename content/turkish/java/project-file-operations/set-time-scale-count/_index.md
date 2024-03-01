---
title: Aspose.Tasks'ta MS Project Zaman Ölçeği Sayımında Uzmanlaşma
linktitle: Aspose.Tasks'ta Zaman Ölçeği Sayısını Ayarlama
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project'te zaman ölçeği sayımını etkili bir şekilde nasıl yöneteceğinizi öğrenin. Proje görselleştirmesini ve yönetimini zahmetsizce optimize edin.
type: docs
weight: 22
url: /tr/java/project-file-operations/set-time-scale-count/
---
## giriiş
MS Project'te zaman ölçeği sayımını yönetmek, proje görselleştirmesini ve yönetimini önemli ölçüde etkileyebilir. Proje yönetimi görevlerini programlı olarak yönetmeye yönelik güçlü bir API olan Aspose.Tasks for Java ile, proje görünümlerini özel ihtiyaçlarınıza göre uyarlamak için zaman ölçeği sayımını verimli bir şekilde değiştirebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdakilerin yerinde olduğundan emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kitinin (JDK) kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini indirip yükleyin. Şu adresten alabilirsiniz:[Burada](https://releases.aspose.com/tasks/java/).
3. Temel Java Programlama Bilgisi: Java programlama diline aşina olmak faydalı olacaktır.

## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 1. Adım: Veri Dizinini Ayarlayın
Proje dosyalarınızın saklanacağı veri dizininin yolunu tanımlayın:
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` veri dizininizin yolu ile.
## 2. Adım: Proje Örneği Oluşturun
 Yeni bir örnek oluştur`Project` nesne:
```java
Project project = new Project();
```
Bu, yeni bir proje nesnesi oluşturur.
## 3. Adım: Gantt Grafiği Görünümünü Yapılandırma
 Oluşturmak`GanttChartView` Gantt şeması görünümünü yapılandırmak için nesne:
```java
GanttChartView view = new GanttChartView();
```
## Adım 4: Alt Katman için Zaman Ölçeği Sayısını Ayarlayın
Alt zaman ölçeği katmanı için sayım ve işaret görünürlüğünü ayarlayın:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Bu, aralık sayısını ve alt katman için onay işaretlerinin görüntülenip görüntülenmeyeceğini belirtir.
## 5. Adım: Orta Katman için Zaman Ölçeği Sayısını Ayarlayın
Benzer şekilde orta zaman ölçeği katmanını yapılandırın:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Adım 6: Projeye Görünüm Ekleme
Yapılandırılmış görünümü projeye ekleyin:
```java
project.getViews().add(view);
```
Bu, projeye özelleştirilmiş görünümü ekler.
## Adım 7: Test Verilerini Projeye Ekleme
Gösterim için projeye bazı test verileri ekleyin:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Bu, belirtilen sürelere sahip iki görev oluşturur.
## Adım 8: Projeyi PDF olarak kaydedin
Projeyi PDF dosyası olarak kaydedin:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Bu, projeyi uygulanan konfigürasyonlarla birlikte bir PDF dosyasına kaydeder.

## Çözüm
Aspose.Tasks for Java'yı kullanarak MS Project'te zaman ölçeği sayımını etkili bir şekilde yönetmek, daha iyi görselleştirme ve yönetim için proje görünümlerini özelleştirmenizi sağlar.
## SSS'ler
### S: Aspose.Tasks for Java büyük ölçekli proje dosyalarını işleyebilir mi?
C: Evet, Aspose.Tasks for Java, büyük ölçekli proje dosyalarını verimli bir şekilde işleme kapasitesine sahiptir.
### S: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mudur?
C: Evet, Aspose.Tasks for Java, Eclipse ve IntelliJ IDEA gibi popüler Java Entegre Geliştirme Ortamları (IDE'ler) ile sorunsuz bir şekilde çalışır.
### S: Aspose.Tasks for Java'yı kullanarak Gantt grafiklerinin görünümünü özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks for Java, Gantt şemalarının görünümünü ihtiyaçlarınıza göre özelleştirmek için kapsamlı yetenekler sunuyor.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, adresinden ücretsiz deneme sürümünü alabilirsiniz.[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nereden destek alabilirim?
 C: Aspose.Tasks forumunda destek ve yardım bulabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).