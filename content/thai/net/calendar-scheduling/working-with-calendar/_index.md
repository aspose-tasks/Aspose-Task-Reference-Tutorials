---
title: การทำงานกับปฏิทินใน Aspose.Tasks
linktitle: การทำงานกับปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: จัดการปฏิทินโครงการ คำนวณระยะเวลา จัดการข้อยกเว้นอย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ .NET
type: docs
weight: 10
url: /th/net/calendar-scheduling/working-with-calendar/
---
## การแนะนำ

Aspose.Tasks สำหรับ .NET มอบคุณสมบัติอันทรงพลังสำหรับการทำงานกับปฏิทิน ช่วยให้นักพัฒนาสามารถจัดการกำหนดการโครงการและการจัดสรรทรัพยากรได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ Aspose.Tasks เพื่อโต้ตอบกับปฏิทิน ครอบคลุมการดำเนินการที่จำเป็น เช่น การดึงข้อมูลปฏิทิน การกำหนดสัปดาห์ทำงาน การคำนวณชั่วโมงทำงาน และอื่นๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
-  การติดตั้ง Aspose.Tasks สำหรับ .NET หากไม่ได้ติดตั้ง ให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/tasks/net/).
- ความคุ้นเคยกับ Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ ที่ต้องการ

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มเขียนโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นแล้ว:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน:

## ขั้นตอนที่ 1: ดึงข้อมูลปฏิทิน

เมื่อต้องการดึงข้อมูลปฏิทินจากโครงการ ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // ดึงข้อมูลปฏิทิน
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

คำอธิบาย:
- โหลดไฟล์โครงการ
- วนซ้ำแต่ละปฏิทินในโครงการ
- พิมพ์ UID และชื่อของแต่ละปฏิทิน

## ขั้นตอนที่ 2: อ่านข้อมูลสัปดาห์ทำงาน

เมื่อต้องการอ่านข้อมูลสัปดาห์ทำงานจากปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- ทำซ้ำในแต่ละสัปดาห์การทำงานในปฏิทิน
- พิมพ์ชื่อ วันที่เริ่มต้น และวันที่สิ้นสุดของแต่ละสัปดาห์การทำงาน
- ข้ามวันทำงานและเวลาทำงานในแต่ละสัปดาห์

## ขั้นตอนที่ 3: อ่านคุณสมบัติปฏิทิน

เมื่อต้องการอ่านคุณสมบัติของปฏิทินโครงการ ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- วนซ้ำแต่ละปฏิทินในโครงการ
- พิมพ์ UID ชื่อ และไม่ว่าจะเป็นปฏิทินพื้นฐาน
- พิมพ์ชั่วโมงการทำงานในแต่ละวัน

## ขั้นตอนที่ 4: คำนวณชั่วโมงทำงาน

เมื่อต้องการคำนวณชั่วโมงทำงานสำหรับงาน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับรายละเอียดของงาน เช่น ปฏิทิน วันที่เริ่มต้น และวันที่สิ้นสุด
- คำนวณชั่วโมงทำงานโดยวนซ้ำในแต่ละวันและตรวจสอบว่าเป็นวันทำงานหรือไม่
- สรุประยะเวลาทั้งหมดเป็นนาที

## ขั้นตอนที่ 5: กำหนดวันธรรมดาสำหรับปฏิทิน

หากต้องการกำหนดวันธรรมดาสำหรับปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- สร้างโครงการและปฏิทินใหม่
- เพิ่มวันทำการเริ่มต้น (วันจันทร์ถึงพฤหัสบดี) และเวลาทำงานที่กำหนดเองสำหรับวันศุกร์
- กำหนดให้วันเสาร์และวันอาทิตย์เป็นวันที่ไม่ทำงาน

## ขั้นตอนที่ 6: เขียนข้อมูลปฏิทินที่อัปเดตไปยัง MPP

หากต้องการเขียนข้อมูลปฏิทินที่อัปเดตลงในไฟล์ MPP ให้ทำตามขั้นตอนเหล่านี้:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/");
    }
}
```

คำอธิบาย:
- โหลดไฟล์โครงการและดึงข้อมูลปฏิทินมาตรฐาน
- แก้ไขข้อมูลปฏิทิน เช่น ข้อยกเว้นและเวลาทำงาน
- บันทึกโครงการที่อัปเดตด้วยข้อมูลปฏิทินที่แก้ไข

## ขั้นตอนที่ 7: คำนวณวันที่เสร็จสิ้นการแยกงาน

เมื่อต้องการคำนวณวันที่เสร็จสิ้นของงานแยก ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการและเรียกข้อมูลงานแยก
- รับปฏิทินโครงการ
- คำนวณวันที่สิ้นสุดตามระยะเวลาที่กำหนดเอง

## ขั้นตอนที่ 8: ดึงข้อมูลข้อยกเว้นของปฏิทิน

เมื่อต้องการดึงข้อมูลเกี่ยวกับข้อยกเว้นของปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- วนซ้ำแต่ละปฏิทินและข้อยกเว้น
- พิมพ์วันที่เริ่มต้นและสิ้นสุดของข้อยกเว้นแต่ละรายการ

## ขั้นตอนที่ 9: รับปฏิทินทรัพยากรฐาน

เมื่อต้องการทำงานกับปฏิทินพื้นฐานของปฏิทินของทรัพยากร ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- เพิ่มทรัพยากรและปฏิทิน
- พิมพ์ชื่อปฏิทินพื้นฐานสำหรับทรัพยากรทั้งหมด

## ขั้นตอนที่ 10: ลบปฏิทิน

หากต้องการลบปฏิทินออกจากโครงการ ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินตามชื่อ
- ลบปฏิทิน

## ขั้นตอนที่ 11: รับวันที่เสร็จสิ้นโดยเริ่มต้นและทำงาน

เมื่อต้องการคำนวณวันที่เสร็จสิ้นตามวันที่เริ่มต้นและงาน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินมาตรฐาน
- กำหนดวันที่เริ่มต้นและระยะเวลาการทำงาน
- คำนวณวันที่เสร็จสิ้นตามวันที่เริ่มต้นและการทำงาน

## ขั้นตอนที่ 12: เริ่มต้นวันทำการถัดไป

เมื่อต้องการเริ่มต้นวันทำงานถัดไปโดยใช้ปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- รับเวลาเริ่มต้นของวันทำการถัดไป

## ขั้นตอนที่ 13: รับวันสิ้นสุดวันทำการก่อนหน้า

เมื่อต้องการสิ้นสุดวันทำงานก่อนหน้าโดยใช้ปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- รับเวลาสิ้นสุดของวันทำงานก่อนหน้า

## ขั้นตอนที่ 14: รับวันที่เริ่มต้นจากเสร็จสิ้นและระยะเวลา

หากต้องการรับวันที่เริ่มต้นตามวันที่สิ้นสุดและระยะเวลา ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- คำนวณวันที่เริ่มต้นจากวันที่สิ้นสุดและระยะเวลา

## ขั้นตอนที่ 15: รับชั่วโมงทำงาน

หากต้องการรับชั่วโมงทำงานสำหรับวันที่ระบุ ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- รับเวลาทำงานสำหรับวันที่ที่ระบุ

## ขั้นตอนที่ 16: รับเวลาทำงาน

หากต้องการรับเวลาทำงานสำหรับวันที่ระบุ ให้ทำตามขั้นตอนเหล่านี้:

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

คำอธิบาย:
- โหลดไฟล์โครงการ
- รับปฏิทินโดย UID
- รับเวลาทำงานสำหรับวันที่ที่ระบุ

## บทสรุป

การทำงานกับปฏิทินใน Aspose.Tasks สำหรับ .NET ถือเป็นสิ่งสำคัญสำหรับการจัดการกำหนดการของโครงการอย่างมีประสิทธิภาพ ด้วยตัวอย่างที่ให้ไว้และคำแนะนำทีละขั้นตอน คุณสามารถจัดการข้อมูลปฏิทิน คำนวณระยะเวลาของงาน และจัดการข้อยกเว้นได้อย่างมีประสิทธิภาพ ด้วยการรวมฟังก์ชันเหล่านี้เข้ากับแอปพลิเคชันของคุณ คุณสามารถปรับปรุงกระบวนการจัดการโครงการและรับประกันการจัดกำหนดการที่แม่นยำ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันจำเป็นต้องมีใบอนุญาตเพื่อใช้ Aspose.Tasks สำหรับ .NET หรือไม่

 ตอบ 1: ใช่ คุณต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ Aspose.Tasks สำหรับ .NET ในแอปพลิเคชันของคุณ คุณสามารถซื้อใบอนุญาตแบบเต็มหรือรับใบอนุญาตชั่วคราว 30 วันได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 2: ฉันสามารถแก้ไขข้อยกเว้นของปฏิทินโดยทางโปรแกรมได้หรือไม่

ตอบ 2: ได้ คุณสามารถเพิ่ม อัปเดต หรือลบข้อยกเว้นปฏิทินโดยใช้โปรแกรม Aspose.Tasks สำหรับ .NET API ได้

### คำถามที่ 3: ฉันจะคำนวณวันที่เสร็จสิ้นงานด้วยระยะเวลาที่กำหนดเองได้อย่างไร

 A3: Aspose.Tasks สำหรับ .NET มีวิธีการดังนี้`GetTaskFinishDateFromDuration()` เพื่อคำนวณวันที่เสร็จสิ้นงานตามระยะเวลาที่กำหนดเอง

### คำถามที่ 4: สามารถสร้างปฏิทินแบบกำหนดเอง เช่น ปฏิทินกะกลางคืน ได้หรือไม่

ตอบ 4: ได้ คุณสามารถสร้างปฏิทินแบบกำหนดเองได้ เช่น ปฏิทินกะกลางคืนโดยใช้ Aspose.Tasks สำหรับ .NET API

### คำถามที่ 5: ฉันสามารถดึงข้อมูลเกี่ยวกับข้อยกเว้นของปฏิทินจากไฟล์โครงการได้หรือไม่

A5: ได้ คุณสามารถดึงข้อมูลเกี่ยวกับข้อยกเว้นของปฏิทินจากไฟล์โครงการโดยใช้ Aspose.Tasks สำหรับ .NET ได้อย่างง่ายดาย