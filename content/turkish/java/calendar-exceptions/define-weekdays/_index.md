---
title: Aspose.Tasks ile Takvim İstisnaları için Hafta İçi Günleri Tanımlayın
linktitle: Aspose.Tasks ile Takvim İstisnaları için Hafta İçi Günleri Tanımlayın
second_title: Aspose.Tasks Java API'si
description: Doğru proje planlaması için Aspose.Tasks'ı kullanarak Java projelerinde takvim istisnaları için haftanın günlerini nasıl tanımlayacağınızı öğrenin.
type: docs
weight: 11
url: /tr/java/calendar-exceptions/define-weekdays/
---
### giriiş
Proje yönetiminde, takvimler için istisnaların tanımlanması, proje zaman çizelgesinde standart olmayan çalışma günlerinin veya tatillerin doğru şekilde temsil edilmesi açısından çok önemlidir. Aspose.Tasks for Java, tatiller veya özel iş günleri gibi istisnaların tanımlanması da dahil olmak üzere, takvimleri verimli bir şekilde yönetmek için güçlü işlevler sağlar. Bu eğitimde Aspose.Tasks for Java'yı kullanarak takvim istisnaları için hafta içi günlerin nasıl tanımlanacağını inceleyeceğiz.
### Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için tercih ettiğiniz IDE'yi seçin.

## Paketleri İçe Aktar
Başlamak için Aspose.Tasks için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;

```

## Adım 1: Veri Dizinini Tanımlayın
Proje dosyalarının saklanacağı veri dizininizin yolunu ayarlayın.
```java
String dataDir = "Your Data Directory";
```
## 2. Adım: Proje Örneği Oluşturun
Proje verileriyle çalışmaya başlamak için Project sınıfının yeni bir örneğini başlatın.
```java
Project project = new Project();
```
## 3. Adım: Takvimi Tanımlayın
İstisnaların ekleneceği takvimi tanımlamak için bir takvim nesnesi oluşturun.
```java
Calendar cal = project.getCalendars().add("Calendar1");
```
## 4. Adım: Hafta İçi İstisnasını Tanımlayın
Takvimde tatiller gibi hafta içi günler için bir istisna tanımlayın.
```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```
## Adım 5: Projeyi Kaydet
Proje dosyasını tanımlanmış takvim istisnalarıyla birlikte kaydedin.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Çözüm
Bu adımları izleyerek Aspose.Tasks for Java'yı kullanarak projenizdeki takvim istisnaları için haftanın günlerini etkili bir şekilde tanımlayabilirsiniz. Tatiller veya özel iş günleri gibi istisnaların yönetilmesi, proje zaman çizelgelerinin doğru şekilde planlanmasını ve temsil edilmesini sağlar.
## SSS
### S: Aynı takvimde haftanın farklı günleri için birden fazla istisna tanımlayabilir miyim?
C: Evet, Aspose.Tasks for Java'yı kullanarak tek bir takvimde haftanın çeşitli günleri için birden fazla istisna tanımlayabilirsiniz.
### S: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mudur?
C: Aspose.Tasks for Java, IntelliJ IDEA, Eclipse ve NetBeans gibi popüler Java IDE'leriyle uyumludur.
### S: Günlük istisnalar dışındaki istisna türlerini özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks for Java, günlük istisnalarla sınırlı olmayıp, çeşitli kriterlere göre istisnaları tanımlama esnekliği sağlar.
### S: Proje gereksinimlerine göre istisnaları dinamik olarak nasıl ele alabilirim?
C: Aspose.Tasks for Java tarafından sağlanan kapsamlı API'yi kullanarak, dinamik proje gereksinimlerine dayalı istisnaları programlı bir şekilde ele alabilirsiniz.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümünden şu adresten yararlanabilirsiniz:[İnternet sitesi](https://releases.aspose.com/).
