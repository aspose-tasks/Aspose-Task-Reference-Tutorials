---
title: Handle Occurrences in Calendar Exceptions using Aspose.Tasks
linktitle: Handle Occurrences in Calendar Exceptions using Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/calendar-exceptions/handle-occurrences/
---

## Complete Source Code
```java
/*
 * Copyright 2001-2022 Aspose Pty Ltd. All Rights Reserved.
 *
 * This file is part of Aspose.Tasks. The source code in this file
 * is only intended as a supplement to the documentation, and is provided
 * "as is", without warranty of any kind, either expressed or implied.
 */



import com.aspose.tasks.*;

public class HandleOccurrences {
    public static void main(String[] args) {
        // ExStart: HandleOccurrences
        CalendarException except = new CalendarException();
        except.setEnteredByOccurrences(true);
        except.setOccurrences(5);
        except.setType(CalendarExceptionType.YearlyByDay);
        // ExEnd: HandleOccurrences
    }
}





```
