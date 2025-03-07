---
title: Aspose.Tasks'ta Takvimle Çalışmak
linktitle: Aspose.Tasks'ta Takvimle Çalışmak
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak proje takvimlerini yönetin, süreleri hesaplayın, istisnaları kolaylıkla ele alın.
weight: 10
url: /tr/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Takvimle Çalışmak

## giriiş

Aspose.Tasks for .NET, takvimlerle çalışmak için güçlü özellikler sunarak geliştiricilerin proje programlarını ve kaynak tahsislerini verimli bir şekilde yönetmesine olanak tanır. Bu eğitimde, takvim bilgilerinin alınması, çalışma haftalarının tanımlanması, çalışma saatlerinin hesaplanması ve daha fazlası gibi temel işlemleri kapsayan, takvimlerle etkileşimde bulunmak için Aspose.Tasks'ın nasıl kullanılacağını keşfedeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:

- C# programlama dilinin temel anlayışı.
-  Aspose.Tasks for .NET'in kurulumu. Kurulu değilse adresinden indirin[Burada](https://releases.aspose.com/tasks/net/).
- Visual Studio veya tercih edilen herhangi bir .NET geliştirme ortamına aşinalık.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Şimdi, adım adım kılavuz formatında her örneği birden fazla adıma ayıralım:

## 1. Adım: Takvim Bilgilerini Alın

Bir projeden takvim bilgilerini almak için şu adımları izleyin:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Takvim Bilgilerini Al
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Projedeki her takvimi yineleyin.
- Her takvimin UID'sini ve adını yazdırın.

## 2. Adım: Çalışma Haftası Bilgilerini Okuyun

Bir takvimden çalışma haftası bilgilerini okumak için şu adımları izleyin:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Takvimdeki her çalışma haftasını yineleyin.
- Her çalışma haftasının adını, başlangıç tarihini ve bitiş tarihini yazdırın.
- Her hafta içindeki çalışma günleri ve çalışma süreleri arasında geçiş yapın.

## 3. Adım: Takvim Özelliklerini Okuyun

Proje takvimlerinin özelliklerini okumak için şu adımları izleyin:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Projedeki her takvimi yineleyin.
- UID'yi, adı ve bunun temel takvim olup olmadığını yazdırın.
- Her gün türü için çalışma saatlerini yazdırın.

## Adım 4: Çalışma Saatlerini Hesaplayın

Bir görevin çalışma saatlerini hesaplamak için şu adımları izleyin:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvim, başlangıç tarihi ve bitiş tarihi gibi görev ayrıntılarını alın.
- Her günü yineleyerek ve bunun bir çalışma günü olup olmadığını kontrol ederek çalışma saatlerini hesaplayın.
- Toplam süreyi dakika cinsinden özetleyin.

## 5. Adım: Takvim için Hafta İçi Günleri Tanımlayın

Bir takvim için haftanın günlerini tanımlamak için şu adımları izleyin:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Açıklama:
- Yeni bir proje ve takvim oluşturun.
- Cuma için varsayılan çalışma günlerini (Pazartesiden Perşembeye) ve özel çalışma saatlerini ekleyin.
- Cumartesi ve Pazar'ı çalışma dışı günler olarak ayarlayın.

## Adım 6: Güncellenmiş Takvim Verilerini MPP'ye Yazma

Güncellenmiş takvim verilerini bir MPP dosyasına yazmak için şu adımları izleyin:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://satın alma.aspose.com/temporary-license/).");
    }
}
```

Açıklama:
- Proje dosyasını yükleyin ve standart takvimi alın.
- İstisnalar ve çalışma saatleri gibi takvim verilerini değiştirin.
- Güncellenen projeyi değiştirilen takvim verileriyle kaydedin.

## Adım 7: Bölünmüş Görev Bitiş Tarihini Hesaplayın

Bölünmüş bir görevin bitiş tarihini hesaplamak için şu adımları izleyin:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Açıklama:
- Proje dosyasını yükleyin ve bölünmüş görevi alın.
- Proje takvimini alın.
- Bitiş tarihini özel bir süreye göre hesaplayın.

## 8. Adım: Takvim İstisnalarını Alın

Takvim istisnaları hakkında bilgi almak için şu adımları izleyin:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Her takvimi ve istisnalarını yineleyin.
- Her istisnanın başlangıç ve bitiş tarihlerini yazdırın.

## 9. Adım: Temel Kaynak Takvimini Alın

Bir kaynağın takviminin temel takvimiyle çalışmak için şu adımları izleyin:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Bir kaynak ve takvimini ekleyin.
- Tüm kaynaklar için temel takvim adını yazdırın.

## Adım 10: Takvimi Sil

Bir projeden takvimi silmek için şu adımları izleyin:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi ada göre alın.
- Takvimi silin.

## Adım 11: Başlangıç ve İşe Göre Bitiş Tarihini Alın

Başlangıç tarihine ve işe göre bitiş tarihini hesaplamak için şu adımları izleyin:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Standart takvimi edinin.
- Bir başlangıç tarihi ve çalışma süresi tanımlayın.
- Başlangıç tarihine ve işe göre bitiş tarihini hesaplayın.

## Adım 12: Bir Sonraki İş Günü Başlangıcını Alın

Bir sonraki iş gününün takvim kullanarak başlamasını sağlamak için şu adımları izleyin:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Bir sonraki iş gününün başlangıç saatini alın.

## Adım 13: Önceki Çalışma Günü Sonunu Alın

Bir takvim kullanarak önceki iş gününün sonunu almak için şu adımları izleyin:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Önceki iş gününün bitiş saatini alın.

## Adım 14: Bitiş ve Süreden Başlangıç Tarihini Alın

Bitiş tarihi ve süreye göre bir başlangıç tarihi almak için şu adımları izleyin:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Bitiş tarihi ve süresinden başlangıç tarihini hesaplayın.

## Adım 15: Çalışma Saatlerini Alın

Belirli bir tarihe ait çalışma saatlerini almak için şu adımları izleyin:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Belirtilen tarih için çalışma saatlerini alın.

## Adım 16: Çalışma Sürelerini Alın

Belirli bir tarihe ait çalışma sürelerini almak için şu adımları izleyin:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Açıklama:
- Proje dosyasını yükleyin.
- Takvimi UID'ye göre alın.
- Belirtilen tarih için çalışma sürelerini alın.

## Çözüm

Aspose.Tasks for .NET'te takvimlerle çalışmak, proje programlarını etkili bir şekilde yönetmek için çok önemlidir. Sağlanan örnekler ve adım adım kılavuzlarla takvim verilerini kolayca yönetebilir, görev sürelerini hesaplayabilir ve istisnaları verimli bir şekilde yönetebilirsiniz. Bu işlevleri uygulamalarınıza entegre ederek proje yönetimi süreçlerini kolaylaştırabilir ve doğru planlama sağlayabilirsiniz.

## SSS'ler

### S1: Aspose.Tasks for .NET'i kullanmak için lisansa ihtiyacım var mı?

 C1: Evet, uygulamalarınızda Aspose.Tasks for .NET'i kullanmak için geçerli bir lisansa ihtiyacınız var. Tam lisansı satın alabilir veya adresinden 30 günlük geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).

### S2: Takvim istisnalarını programlı olarak değiştirebilir miyim?

C2: Evet, Aspose.Tasks for .NET API'lerini kullanarak takvim istisnalarını programlı olarak ekleyebilir, güncelleyebilir veya silebilirsiniz.

### S3: Görev bitiş tarihlerini özel sürelerle nasıl hesaplayabilirim?

 Cevap3: Aspose.Tasks for .NET aşağıdaki gibi yöntemler sağlar:`GetTaskFinishDateFromDuration()` özel sürelere göre görev bitiş tarihlerini hesaplamak için.

### S4: Gece vardiyası takvimleri gibi özel takvimler oluşturmak mümkün mü?

Cevap4: Evet, Aspose.Tasks for .NET API'lerini kullanarak gece vardiyası takvimleri gibi özel takvimler oluşturabilirsiniz.

### S5: Proje dosyalarından takvim istisnaları hakkında bilgi alabilir miyim?

C5: Evet, Aspose.Tasks for .NET'i kullanarak proje dosyalarından takvim istisnaları hakkındaki bilgileri kolayca alabilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
