---
title: Aspose.Tasks Projelerinde Gantt Grafiği Görünümünü Yapılandırma
linktitle: Aspose.Tasks Projelerinde Gantt Grafiği Görünümünü Yapılandırma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ta Gantt MS Proje Tablosu Görünümünü Java kullanarak nasıl yapılandıracağınızı öğrenin. Projeyi özelleştirin ve adım adım Gantt grafiğinde görselleştirin.
type: docs
weight: 10
url: /tr/java/project-configuration/configure-gantt-chart/
---
## giriiş
Bu eğitimde, Java kullanarak Aspose.Tasks projelerinde Gantt MS Proje Tablosu Görünümünü nasıl yapılandıracağınızı öğreneceksiniz. Aspose.Tasks, Microsoft Project dosyalarıyla programlı olarak çalışmanıza olanak tanıyan güçlü bir Java API'sidir. Bu adımları izleyerek Gantt şeması görünümünü projenizin gereksinimlerine göre özelleştirebileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks Kitaplığı: Aspose.Tasks kitaplığını indirip yükleyin. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): İstediğiniz bir IDE'yi seçin. Bu eğitimde IntelliJ IDEA kullanılmaktadır, ancak rahat olduğunuz herhangi bir IDE'yi kullanabilirsiniz.
## Paketleri İçe Aktar
Öncelikle Java projenizde Aspose.Tasks ile çalışmak için gerekli paketleri içe aktarmanız gerekiyor. Aşağıdaki içe aktarma ifadelerini Java dosyanıza ekleyin:
```java
import com.aspose.tasks.*;
```
Şimdi Gantt MS Proje Tablosu Görünümünü yapılandırma sürecini adım adım talimatlara ayıralım:
## 1. Adım: Veri Dizinini Ayarlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` proje veri dizininizin yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "project.mpp");
```
Proje dosyanızı yükleyin (`project.mpp` bu örnekte) kullanarak`Project` Aspose.Tasks'tan sınıf.
## 3. Adım: Yeni Etkinlik Ekle
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 kullanarak projenizde yeni bir görev oluşturun.`Task` sınıfa gidin ve onu kök görevin çocuklarına ekleyin.
## 4. Adım: Özel Niteliği Tanımlayın
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 kullanarak yeni bir özel özellik tanımlayın.`ExtendedAttributeDefinition`class'ı seçin ve bunu projenin genişletilmiş özniteliklerine ekleyin.
## 5. Adım: Göreve Özel Nitelik Ekleme
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Özel niteliği, oluşturulan göreve şunu kullanarak ekleyin:`createExtendedAttribute` yöntem.
## Adım 6: Tabloyu Özelleştirin
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Metin özelliği alanını belirtilen genişlik, başlık ve hizalamayla ekleyerek tabloyu özelleştirin.
## Adım 7: Projeyi Kaydet
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Projeyi yapılandırılmış Gantt MS Proje Tablosu Görünümü ile kaydedin. Ortaya çıkan dosya Microsoft Project 2010'da açılabilir.
## Çözüm
Tebrikler! Aspose.Tasks projelerinde Gantt MS Proje Tablosu Görünümü'nü Java kullanarak başarıyla yapılandırdınız. Artık proje niteliklerini özelleştirebilir ve projenizin ihtiyaçlarına göre bunları Gantt şemasında görselleştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks; .NET, Java ve C dahil olmak üzere birçok programlama dilinde mevcuttur.++.
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için desteği nerede bulabilirim?
C: Bu konuda destek bulabilir ve sorular sorabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için nasıl lisans satın alabilirim?
 C: Lisansı şuradan satın alabilirsiniz:[Burada](https://purchase.aspose.com/buy).
### S: Test amaçlı olarak geçici bir lisansa ihtiyacım var mı?
 C: Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).