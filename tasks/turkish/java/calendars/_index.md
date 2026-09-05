---
date: 2026-08-08
description: Aspose.Tasks for Java kullanarak MS Project takvimlerinde hafta içi günlerini
  nasıl tanımlayacağınızı öğrenin. Bu rehber, MS Project takvimini nasıl değiştireceğinizi,
  Java’da custom calendar oluşturmayı ve çalışma günlerini verimli bir şekilde planlamayı
  gösterir.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Takvimler
og_description: Aspose.Tasks for Java kullanarak MS Project takvimlerinde hafta içi
  günlerini nasıl tanımlayacağınızı öğrenin. Java’da custom calendar konusunda uzmanlaşın,
  MS Project takvimini değiştirin ve çalışma günlerini verimli bir şekilde planlayın.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: MS Project takvimlerinde hafta içi günlerini nasıl tanımlarsınız – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: MS Project takvimlerinde hafta içi günlerini nasıl tanımlarsınız – Aspose.Tasks
  Java
url: /tr/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvimler

## Giriş

Java geliştiricisi olarak projenizin takviminde **hafta içi günlerini tanımlamak** istiyorsanız, doğru yerdesiniz. Bu merkezde, Aspose.Tasks for Java için tüm öğreticileri topluyoruz; bu öğreticiler **MS Project takvimleri içinde hafta içi günlerini nasıl tanımlanır**, çalışma saatlerini ayarlamayı ve zaman çizelgelerinizi kristal netliğinde tutmayı gösterir. Yeni bir zamanlama motoru oluşturuyor ya da mevcut bir planı ayarlıyorsanız, hafta içi günlerini tanımlamayı ustalaşmak, çalışma günü desenleri, tatiller ve özel vardiyalar üzerinde kesin kontrol sağlar. Bu kılavuz ayrıca **MS Project takvimini programlı olarak nasıl değiştireceğinizi** açıklar, böylece onlarca proje için takvim oluşturmayı otomatikleştirebilirsiniz.

## Hızlı cevaplar
- **Hafta içi günlerini tanımlamanın temel amacı nedir?**  
  MS Project'e hangi günlerin çalışma günü olduğunu ve çalışma saatlerinin ne olduğunu söylemek.
- **Java'da hafta içi günlerini tanımlamayı hangi kütüphane yönetir?**  
  Aspose.Tasks for Java, takvim manipülasyonu için akıcı bir API sağlar.
- **Lisans gerekli mi?**  
  Ücretsiz değerlendirme lisansı test için çalışır; üretim için ticari lisans gereklidir.
- **Farklı ekipler için birden fazla takvim tanımlayabilir miyim?**  
  Evet – her proje, kendi hafta içi ayarlarına sahip birkaç takvim içerebilir.
- **Başlamak için bir örnek proje var mı?**  
  Aşağıdaki “Define Weekdays in Calendar” öğreticisi, çalıştırmaya hazır bir örnek içerir.

## MS Project takvimlerinde hafta içi günlerini nasıl tanımlarım?

`Project` sınıfı bir MS Project dosyasını temsil eder ve veri yapılarına erişim sağlar. `Calendar` nesnesi bir projenin çalışma zamanı tanımlarını ve istisnalarını depolar. Projenizi `new Project("myproject.mpp")` ile yükleyin, bir `Calendar` nesnesi alın (veya oluşturun) ve ardından `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` çağrısını yapın. Bu tek satır, 8‑saatlik bir vardiya ile Pazartesi çalışma günü girdisi oluşturur. Diğer günler için tekrarlayın ve sonunda projeyi `project.save("updated.mpp")` ile kaydedin. Bu özlü desen, hafta içi günlerini sadece birkaç API çağrısıyla tanımlamanıza, değiştirmenize veya silmenize olanak tanır ve manuel UI etkileşimine gerek kalmaz.

## WeekDay nesnesi nedir?

`WeekDay` nesnesi, Aspose.Tasks takviminde tek bir hafta günü girdisini temsil eder; çalışma durumu ve çalışma‑zamanı aralıklarını saklar. Başlangıç/bitiş saatlerini yapılandırabilir, çalışma günü olmayan olarak ayarlayabilir veya fazla mesai periyotları ekleyebilirsiniz. Birden fazla `WorkingTime` aralığını tutarak bölünmüş vardiyalar modelleyebilir ve varsayılan çalışma günleri için bayrakları destekler. `WeekDay` API'sini kullanarak bir günü etkinleştirebilir veya devre dışı bırakabilir, normal saatleri atayabilir veya gelişmiş zamanlama senaryoları için fazla mesai kurallarını belirtebilirsiniz.

## Neden Aspose.Tasks for Java'ı hafta içi günlerini tanımlamak için kullanmalısınız?

- **Tam API kontrolü** – UI kısıtlamaları yok; programlı olarak hafta içi girdilerini oluşturabilir, değiştirebilir veya silebilirsiniz.  
- **Çapraz‑platform** – Masaüstü uygulamalardan bulut hizmetlerine, herhangi bir JVM‑uyumlu ortamda çalışır.  
- **Kesinlik** – Her hafta içi günü için farklı çalışma zamanları ayarlayın, tatiller için istisnalar ekleyin ve takvimleri birden çok proje arasında senkronize edin.  
- **Performans** – 500 + görev ve 100 + hafta içeren takvimleri, tüm UI’yı yüklemeden işleyin; standart 2.5 GHz sunucuda dönüşüm süresi 2 saniyenin altında (Aspose benchmarkına dayalı ölçülmüş iddia).  

## Önkoşullar
- Java 8 veya daha yeni bir sürüm yüklü olmalı.  
- Aspose.Tasks for Java kütüphanesi (Aspose web sitesinden indirilebilir veya Maven/Gradle üzerinden eklenebilir).  
- Geçerli bir Aspose.Tasks lisansı (öğrenme için değerlendirme lisansı yeterli).  

## Aspose.Tasks ile MS Project takvim özelliklerini yönetin

Java’da Aspose.Tasks ile MS Project takvim özelliklerini yönetmenin tam potansiyelini ortaya çıkarın. Öğreticimiz, takvim yönetiminin inceliklerini adım adım anlatır, özelleştirme ve optimizasyon konularında değerli içgörüler sunar. Çalışma saatlerini ayarlamaktan özel tarihleri tanımlamaya kadar her şeyi öğreneceksiniz.

Proje zaman çizelgelerinizin kontrolünü elinize almaya hazır mısınız? [Buradaki öğreticiyi keşfedin](./properties/).

## Aspose.Tasks kullanarak MS Project takvimleri oluşturun

Aspose.Tasks for Java ile MS Project takvimleri oluşturmayı zahmetsizce kolaylaştırın. Öğreticimiz süreci basitleştirir, projenizin benzersiz ihtiyaçlarına uygun takvimler kurmanızı sağlar. Verimli proje planlaması ve organizasyonu için ilk adımı atın.

Takvimleri kolayca oluşturmak ister misiniz? [Öğreticiyi inceleyin](./create/).

## Aspose.Tasks ile takvimde hafta içi günlerini tanımlayın

Aspose.Tasks for Java kullanarak MS Project takvimlerinizi hafta içi günlerini tanımlayarak özelleştirin. Bu öğretici, çalışma günlerini ve zaman dilimlerini şekillendirmenize rehberlik eder, başarılı proje yönetimi için gereken esnekliği sunar. Takvimlerinizi sizin için çalışır hâle getirin.

Hafta içi günlerini zahmetsizce tanımlamaya hazır mısınız? [Buradan başlayın](./define-weekdays/).

Bu öğreticiler arasında gezinirken, çalışma saatleri çıkarma, standart takvim oluşturma, çalışma haftalarını okuma ve takvimleri MPP formatına güncelleme gibi ek konuları da keşfedeceksiniz. Her öğretici, pratik bilgi sağlamak üzere hazırlanmıştır; böylece öğrendiklerinizi doğrudan Java projelerinize uygulayabilirsiniz.

## Aspose.Tasks kullanarak takvimden çalışma saatlerini alın

Aspose.Tasks for Java ile MS Project takvimlerinden çalışma saatlerini çıkarmayı öğrenerek proje yönetimi görevlerinizi basitleştirin. Bu öğretici, zaman çizelgelerinizi verimli bir şekilde optimize etmeniz için gereken becerileri kazandırır.

Çalışma saatlerini zahmetsizce çıkarmaya hazır mısınız? [Öğreticiyi keşfedin](./working-hours/).

## Aspose.Tasks ile standart takvim oluşturun

Aspose.Tasks ile Java’da standart bir MS Project takvimi oluşturmayı öğrenerek proje yönetimi yeteneklerinizi artırın. Bu adım‑adım öğretici, proje zaman çizelgelerinizde standart bir yaklaşım uygulamanızı sağlar.

Standart bir takvim oluşturmaya hazır mısınız? [Öğreticiyi inceleyin](./make-standard/).

## Aspose.Tasks ile MS Project takviminden çalışma haftalarını okuyun

Aspose.Tasks for Java kullanarak MS Project takvimlerinden çalışma haftalarını okuma konusunda kapsamlı bilgi edinin. Bu öğretici, proje takvimlerinizi etkili bir şekilde yönetmeniz için ayrıntılı talimatlar sunar.

Çalışma haftalarını zahmetsizce okumaya hazır mısınız? [Buradan başlayın](./read-work-weeks/).

## Aspose.Tasks ile MS Project takvimlerini MPP formatına güncelleyin

Aspose.Tasks for Java ile MS Project takvimlerini MPP formatına zahmetsizce güncelleyin. Bu öğretici, proje verilerinizin optimal uyumluluk için doğru formatta olmasını sağlayan sorunsuz bir yaklaşım sunar.

Takvimleri MPP formatına güncellemeye hazır mısınız? [Öğreticiyi keşfedin](./update-to-mpp/).

Aspose.Tasks for Java’un tam potansiyelini ortaya çıkarın ve proje yönetimi becerilerinizi yükseltin. Her öğretici, tüm seviyelerdeki geliştiricilere sorunsuz bir öğrenme deneyimi sunacak şekilde tasarlanmıştır. Java proje yönetimi yolculuğunuzu bugün dönüştürün!

## Takvim öğreticileri
### [Aspose.Tasks ile MS Project Takvim Özelliklerini Yönetin](./properties/)
Java’da Aspose.Tasks kullanarak MS Project takvim özelliklerini nasıl yöneteceğinizi öğrenin. Bu, Java uygulamalarınızdaki takvimler için adım‑adım rehber sunar.
### [Aspose.Tasks kullanarak MS Project takvimleri oluşturun](./create/)
Aspose.Tasks for Java ile MS Project takvimleri oluşturmayı öğrenin. Proje yönetimini zahmetsizce akıcı hâle getirin.
### [Aspose.Tasks ile takvimde hafta içi günlerini tanımlayın](./define-weekdays/)
Aspose.Tasks for Java ile MS Project takviminde hafta içi günlerini tanımlamayı öğrenin. Çalışma günlerini ve zaman dilimlerini zahmetsizce özelleştirin.
### [Aspose.Tasks kullanarak takvimden çalışma saatlerini alın](./working-hours/)
Aspose.Tasks for Java ile MS Project takvimlerinden çalışma saatlerini kolayca çıkarın. Proje yönetimi görevlerini basitleştirin.
### [Aspose.Tasks ile standart takvim oluşturun](./make-standard/)
Aspose.Tasks kullanarak Java’da standart bir MS Project takvimi oluşturmayı öğrenin. Bu adım‑adım öğreticiyle proje yönetimi yeteneklerinizi geliştirin.
### [Aspose.Tasks ile MS Project takviminden çalışma haftalarını okuyun](./read-work-weeks/)
Aspose.Tasks for Java ile MS Project takviminden çalışma haftalarını nasıl okuyacağınızı öğrenin. Bu kapsamlı öğreticide adım‑adım talimatlar bulacaksınız.
### [Aspose.Tasks ile MS Project takvimlerini MPP formatına güncelleyin](./update-to-mpp/)
Aspose.Tasks for Java kullanarak MS Project takvimlerini MPP formatına zahmetsizce güncellemeyi öğrenin.

## Sıkça Sorulan Sorular

**Q: Her hafta içi günü için farklı çalışma saatleri belirleyebilir miyim?**  
A: Evet. Aspose.Tasks, Pazartesi’den Pazar’a kadar her gün için başlangıç ve bitiş saatlerini ayrı ayrı ayarlamanıza izin verir.

**Q: Tatilleri veya çalışma dışı günleri nasıl yönetirim?**  
A: Hafta içi günlerini tanımladıktan sonra, tatilleri veya özel çalışma dışı periyotları işaretlemek için istisna (tarih) ekleyebilirsiniz.

**Q: Bir takvimden başka bir takvime hafta içi tanımını kopyalamak mümkün mü?**  
A: Kesinlikle. Mevcut bir takvimden bir `WeekDay` nesnesi alıp başka bir takvim örneğine ekleyebilirsiniz.

**Q: Hafta içi günlerini güncelledikten sonra projeyi yeniden yüklemem gerekir mi?**  
A: Hayır. Değişiklikler doğrudan bellek içindeki `Project` nesnesine uygulanır; işiniz bittiğinde sadece projeyi kaydedin.

**Q: Hafta içi manipülasyonu için hangi Aspose.Tasks sürümü gerekir?**  
A: 20.10 ve sonrası tüm yeni sürümler tam hafta içi API'lerini destekler. En iyi performans için en son kararlı sürümü kullanmanızı öneririz.

---

**Son güncelleme:** 2026-08-08  
**Test edildiği sürüm:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}