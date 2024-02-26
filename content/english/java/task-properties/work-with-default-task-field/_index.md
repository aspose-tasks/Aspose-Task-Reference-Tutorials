---
title: Work with Default Task Field Title in Aspose.Tasks
linktitle: Work with Default Task Field Title in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 37
url: /java/task-properties/work-with-default-task-field/
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



import com.aspose.tasks.FieldHelper;
import com.aspose.tasks.Tsk;

public class WorkWithGetDefaultTaskFieldTitle {
    public static void main(String[] args) {
        // Shows how to get default field title for the specific task's field.

        System.out.println("Title for Tsk.ActualCost: " + FieldHelper.getDefaultTaskFieldTitle(Tsk.ACTUAL_COST.getKeyType()));
        System.out.println("Title for Tsk.PercentWorkComplete: " + FieldHelper.getDefaultTaskFieldTitle(Tsk.PERCENT_WORK_COMPLETE.getKeyType()));
    }
}
```
